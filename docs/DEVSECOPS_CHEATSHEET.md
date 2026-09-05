# 🛡️ DualAI DevSecOps Cheat Sheet: Top 10 Flaws & AI Countermeasures
**A Practical Security Guide for Developers, Red Teams & Blue Teams**

---

## 📌 Introduction
This cheat sheet summarizes the **Top 10 Security Flaws** most frequently uncovered during automated battles inside **DualAI MID Arena**, alongside the concrete, battle-tested countermeasures synthesized by **Blue Team AI**.

![The AI-Driven Security Loop](studio/The_AI-Driven_Security_Loop.png)

---

### 1. Insecure Deserialization & Untrusted JSON Parsing
- 🔴 **The Flaw**: Calling `eval()` or unvalidated `JSON.parse()` on untrusted request bodies or cookies.
- 🔵 **The Fix**: Use strict schema validation (e.g. `zod`, `pydantic`, `Joi`) and parse only primitive datatypes:
  ```javascript
  // Defended with strict schema parser:
  const schema = z.object({ userId: z.string().uuid(), role: z.enum(['user', 'admin']) });
  const validatedPayload = schema.parse(rawInput);
  ```

---

### 2. Side-Channel Timing Attacks (CWE-208)
- 🔴 **The Flaw**: Using standard string comparison (`===`, `==`, `strcmp`) for API keys, passwords, or HMAC signatures.
- 🔵 **The Fix**: Use constant-time equality comparisons:
  ```javascript
  // Node.js:
  crypto.timingSafeEqual(Buffer.from(computedHash), Buffer.from(receivedHash));
  ```
  ```python
  # Python:
  import hmac
  hmac.compare_digest(computed_hash, received_hash)
  ```

---

### 3. Catastrophic Regex Denial of Service (ReDoS) (CWE-1333)
- 🔴 **The Flaw**: Nested quantifiers `(a+)+` causing exponential polynomial backtracking on long unmatched inputs.
- 🔵 **The Fix**: Enforce input length caps, use linear-time regex engines (e.g. Google's RE2), or eliminate nesting:
  ```python
  # Safe bounded regex without nested groups:
  SAFE_EMAIL = re.compile(r"^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$")
  ```

---

### 4. Prototype Pollution in JavaScript (CWE-1321)
- 🔴 **The Flaw**: Merging unvalidated user objects where keys contain `__proto__`, `constructor`, or `prototype`.
- 🔵 **The Fix**: Sanitize keys and initialize clean dictionary objects:
  ```javascript
  const cleanObject = Object.create(null);
  const DANGEROUS_KEYS = new Set(['__proto__', 'constructor', 'prototype']);
  function safeSet(obj, key, val) {
    if (!DANGEROUS_KEYS.has(key)) obj[key] = val;
  }
  ```

---

### 5. Mass Assignment & Privilege Escalation (CWE-915)
- 🔴 **The Flaw**: Passing `req.body` directly to database ORM updates (`User.update(req.body)`).
- 🔵 **The Fix**: Use explicit Data Transfer Object (DTO) whitelisting:
  ```javascript
  // Whitelist only safe, user-editable fields:
  const allowedUpdates = {
    name: req.body.name,
    email: req.body.email
  };
  await User.update(allowedUpdates, { where: { id: req.user.id } });
  ```

---

### 6. Time-of-Check to Time-of-Use (TOCTOU) File Handling (CWE-367)
- 🔴 **The Flaw**: Checking file size with `os.stat()` and subsequently copying with `shutil.copy2()` (allowing symlink replacement during race window).
- 🔵 **The Fix**: Open file descriptor with `O_NOFOLLOW | O_EXCL` and stream with a bounded byte counter.

---

### 7. Server-Side Request Forgery (SSRF) & Loopback Smuggling (CWE-918)
- 🔴 **The Flaw**: Fetching user-supplied URLs without restricting private, loopback, and link-local network ranges.
- 🔵 **The Fix**: Resolve DNS first, validate against a private IP blacklist, and pin the socket to the validated IP.

---

### 8. JWT "alg": "none" Signature Stripping (CWE-347)
- 🔴 **The Flaw**: Accepting unsigned JWT tokens where the header specifies `alg: "none"`.
- 🔵 **The Fix**: Explicitly whitelist acceptable cryptographic algorithms (e.g. `algorithms: ['HS256', 'RS256']`) and reject any tokens with unapproved algorithms.

---

### 9. SQL / NoSQL Query Injection (CWE-89)
- 🔴 **The Flaw**: String concatenation or unescaped query builders (`SELECT * FROM users WHERE user = '${userInput}'`).
- 🔵 **The Fix**: Use parameterized prepared statements:
  ```csharp
  // C# / ASP.NET:
  var cmd = new SqlCommand("SELECT * FROM Users WHERE Email = @Email", conn);
  cmd.Parameters.AddWithValue("@Email", emailInput);
  ```

---

### 10. Memory & Buffer Exhaustion (CWE-400)
- 🔴 **The Flaw**: Reading entire uploaded files into RAM buffers before checking length limits.
- 🔵 **The Fix**: Enforce pre-read stream ceilings (as DualAI does with its 32 MB per-file and 128 MB workspace caps).

---

## 🛒 Put Your Code to the Test
Experience automated multi-agent security auditing on your machine:
- **Free Edition (2-Result Trial)**: Available on GitHub Releases.
- **Enterprise Pro Edition**: **[Payhip Store](https://payhip.com/b/Tfz7D)**
- **Discussions Hub**: **[`dual-ai-arena-discussions`](https://github.com/thepros2014/dual-ai-arena-discussions/discussions)**

# ⚔️ DualAI MID Arena — Community Benchmark Challenge Pack
**5 Real-World Security Challenges Ready to Test in DualAI MID Arena**

---

## 🎯 How to Use These Challenges
> **Safety note:** Every snippet in this pack is synthetic, intentionally vulnerable, and for throwaway test data only. Never paste real secrets, customer data, production URLs, or proprietary code into a public challenge.

1. Open **DualAI MID Arena**.
2. Click **"Create Challenge"**.
3. Create a file matching the path shown in the challenge.
4. Paste the vulnerable code snippet into the editor.
5. Click **"Start Match & Enter Arena"** and watch **Red Team** and **Blue Team** battle to expose and remediate the flaw!

---

### 🧩 Challenge 1: The "alg": "none" JWT Signature Bypass
- **Language**: JavaScript / Node.js
- **Target File**: `src/jwtAuth.js`
- **Flaw Category**: Authentication Bypass & Cryptographic Key Handling
- **Difficulty**: ⭐⭐ Medium

#### Vulnerable Code:
```javascript
const crypto = require('crypto');

function verifyJwtToken(token, fixtureKey) {
  const [headerB64, payloadB64, signatureB64] = token.split('.');
  if (!headerB64 || !payloadB64) return null;

  const header = JSON.parse(Buffer.from(headerB64, 'base64url').toString('utf8'));
  const payload = JSON.parse(Buffer.from(payloadB64, 'base64url').toString('utf8'));

  // VULNERABILITY: Permitting 'none' algorithm allows attacker to forge admin tokens without signature
  if (header.alg === 'none') {
    return payload;
  }

  const expectedSignature = crypto
    .createHmac('sha256', fixtureKey)
    .update(`${headerB64}.${payloadB64}`)
    .digest('base64url');

  if (signatureB64 === expectedSignature) {
    return payload;
  }

  return null;
}

module.exports = { verifyJwtToken };
```

#### What to Expect:
- 🔴 **Red Team**: Detects `header.alg === 'none'`, crafts a forged token `{ "admin": true, "sub": "attacker" }` with `alg: "none"`, and proves signature bypass.
- 🔵 **Blue Team**: Eliminates algorithm switching, enforces strict HMAC-SHA256 verification with constant-time equality check (`crypto.timingSafeEqual`), and adds unit tests.

---

### 🧩 Challenge 2: Catastrophic Regex Denial of Service (ReDoS)
- **Language**: Python (FastAPI / Standard Library)
- **Target File**: `app/validator.py`
- **Flaw Category**: Denial of Service (Resource Exhaustion)
- **Difficulty**: ⭐⭐⭐ Hard

#### Vulnerable Code:
```python
import re
from typing import Optional

# VULNERABILITY: Exponential backtracking on strings like 'aaaaaaaaaaaaaaaaaaaaaaaaaaaa!'
EMAIL_REGEX = re.compile(r"^([a-zA-Z0-9_.-]+)+@([a-zA-Z0-9_-]+\.)+[a-zA-Z]{2,6}$")

def validate_user_email(email_input: str) -> bool:
    if not email_input or len(email_input) > 256:
        return False
    # Threat: Processing a crafted 30-char string will freeze the Python event loop for 10+ seconds
    return bool(EMAIL_REGEX.match(email_input))
```

#### What to Expect:
- 🔴 **Red Team**: Identifies nested quantifier `([a-zA-Z0-9_.-]+)+`, generates polynomial payload `aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa!`, and measures CPU lockup.
- 🔵 **Blue Team**: Replaces vulnerable regex with non-backtracking linear DFA parser (or atomic regex standard), and sets timeout boundaries.

---

### 🧩 Challenge 3: Mass Assignment & Role Escalation
- **Language**: JavaScript / Express
- **Target File**: `controllers/userController.js`
- **Flaw Category**: Access Control / Privilege Escalation
- **Difficulty**: ⭐ Easy

#### Vulnerable Code:
```javascript
const express = require('express');
const router = express.Router();
let database = {
  users: [
    { id: 1, name: 'Alice', email: 'alice@test.com', role: 'user' }
  ]
};

router.put('/users/:id', (req, res) => {
  const userId = parseInt(req.params.id, 10);
  const user = database.users.find(u => u.id === userId);
  if (!user) return res.status(404).json({ error: 'User not found' });

  // VULNERABILITY: Object.assign copies all incoming body properties directly into stored user record
  // An attacker can pass { "role": "admin", "isSuperUser": true }
  Object.assign(user, req.body);

  res.json({ message: 'Profile updated successfully', user });
});

module.exports = router;
```

#### What to Expect:
- 🔴 **Red Team**: Sends PUT payload `{ "role": "admin" }` to prove privilege escalation from unprivileged account.
- 🔵 **Blue Team**: Introduces strict DTO whitelist (only allowing `name` and `email` modifications) and rejects unexpected fields.

---

### 🧩 Challenge 4: Prototype Pollution via Deep Object Merge
- **Language**: JavaScript / Node.js
- **Target File**: `utils/merge.js`
- **Flaw Category**: Prototype Pollution & Remote Code Tampering
- **Difficulty**: ⭐⭐⭐⭐ Expert

#### Vulnerable Code:
```javascript
function isObject(item) {
  return (item && typeof item === 'object' && !Array.isArray(item));
}

function deepMerge(target, source) {
  let output = Object.assign({}, target);
  if (isObject(target) && isObject(source)) {
    Object.keys(source).forEach(key => {
      // VULNERABILITY: No check for '__proto__', 'constructor', or 'prototype'
      if (isObject(source[key])) {
        if (!(key in target))
          Object.assign(output, { [key]: source[key] });
        else
          output[key] = deepMerge(target[key], source[key]);
      } else {
        Object.assign(output, { [key]: source[key] });
      }
    });
  }
  return output;
}

module.exports = { deepMerge };
```

#### What to Expect:
- 🔴 **Red Team**: Injects JSON payload `{"__proto__": {"isAdmin": true}}` and verifies that global `({}).isAdmin === true`.
- 🔵 **Blue Team**: Sanitizes dangerous object keys (`__proto__`, `prototype`, `constructor`) and uses `Object.create(null)` map isolation.

---

### 🧩 Challenge 5: Time-of-Check to Time-of-Use (TOCTOU) File Upload
- **Language**: Python / Flask
- **Target File**: `services/fileService.py`
- **Flaw Category**: Concurrency & Symlink Race Condition
- **Difficulty**: ⭐⭐⭐⭐ Expert

#### Vulnerable Code:
```python
import os
import shutil

UPLOAD_DIR = "./example-uploads"
QUARANTINE_DIR = "./example-quarantine"

def process_user_upload(temp_file_path: str, filename: str):
    destination = os.path.join(UPLOAD_DIR, filename)
    
    # 1. TIME OF CHECK: Validate size on disk
    if os.path.getsize(temp_file_path) > 5 * 1024 * 1024:
        raise ValueError("File exceeds 5MB limit.")
        
    # VULNERABILITY: TOCTOU race window between getsize() check and copy2() execution
    # An attacker can replace temp_file_path with a symlink outside the approved sample directory or a huge file
    shutil.copy2(temp_file_path, destination)
    return destination
```

#### What to Expect:
- 🔴 **Red Team**: Detects symlink replacement gap and race condition between `os.path.getsize` and `shutil.copy2`.
- 🔵 **Blue Team**: Switches to atomic file descriptor streaming with bounded byte counting (`os.open` with `O_NOFOLLOW | O_EXCL`).

---

💬 **Share your battle logs and model debate transcripts in our Discussions tab!**
- 🛍️ **Upgrade to Enterprise for Unlimited Battles**: [https://payhip.com/b/Tfz7D](https://payhip.com/b/Tfz7D)

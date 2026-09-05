# 🛠️ How to Troubleshoot Common Errors & Edge Cases
**Step-by-Step Solutions to Runtime Issues, Port Collisions & Safety Ceilings**

---

## 1. "Microsoft Edge WebView2 Runtime is required"
- **Solution**: Download and install the free [Microsoft WebView2 Evergreen Bootstrapper](https://developer.microsoft.com/microsoft-edge/webview2/), then click "Retry".

---

## 2. HTTP 402: "trial_limit_reached"
- **Solution**: You have completed your 2 free trial battle results. Enter your Enterprise license key from [https://payhip.com/b/Tfz7D](https://payhip.com/b/Tfz7D) to unlock unlimited battles.

---

## 3. "Failed to connect to Ollama"
- **Solution**:
  1. Open PowerShell and run `ollama serve` or `ollama list`.
  2. Confirm that Ollama is running and available to local applications.

---

## 4. "File exceeds 32 MB safety ceiling"
- **Solution**:
  - Exclude compiled binary files (`.exe`, `.zip`, `.mp4`, `node_modules`).
  - Only import raw source code (`.js`, `.py`, `.cs`, `.go`, `.rs`, `.java`, `.sol`).

---

## 5. HTTP 429: "Too Many Requests" (Cloud APIs)
- **Solution**: Switch one or both teams to **Local Ollama** for unlimited, zero-rate-limited execution.

---

- [[Home]] • [[How-To-Install-and-Setup]] • [[10-Gate-Security-Audit]]

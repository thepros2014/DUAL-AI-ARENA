# ❓ Customer FAQ, Privacy Guarantees & Troubleshooting
**Answers to Common Buyer Questions on AI Models, Local Privacy & Licensing**

---

## 🔒 1. Privacy & Code Security Guarantees

### Q: Does DUAL-AI-ARENA ever upload my source code to any cloud servers?
**A**: **No, never.** DUAL-AI-ARENA runs 100% locally on your computer. There are zero third-party telemetry servers, no external analytics, and no cloud backends.

### Q: Can I run this 100% offline with no internet connection at all?
**A**: **Yes!** If you use **Ollama** (`qwen2.5-coder:7b`, `deepseek-r1:8b`, or `llama3.2`), all AI inference runs locally on your computer's GPU/CPU with **$0 token costs and zero bytes leaving your machine**.

### Q: How are my workspace files and provider settings protected on my PC?
**A**: They remain in the application's protected local storage. Use local Ollama when you need fully local inference, and review your provider's terms before using a cloud model.

---

## ⚡ 2. AI Model Setup & Performance

### Q: What is the best model setup for finding critical bugs?
**A**:
- **Best Defensive Verifier (Blue Team)**: `qwen2.5-coder:7b` (via Ollama) or `gpt-4o` (via OpenAI).
- **Best Offensive Threat Hunter (Red Team)**: `deepseek-r1:8b` (deep reasoning) or `gpt-4o`.
- **Fastest for Laptops**: `llama3.2:3b` (super fast, only requires 2.4 GB VRAM).

### Q: Can I mix local models and cloud models?
**A**: **Yes!** You can configure Red Team to use local Ollama while Blue Team uses cloud Gemini, or vice-versa.

---

## 🛠️ 3. Quick Fixes for Common Buyer Questions

### "Microsoft Edge WebView2 Runtime is required"
- **Fix**: Download and install the free [Microsoft WebView2 Runtime](https://developer.microsoft.com/microsoft-edge/webview2/) from Microsoft.

### "Trial limit reached (2 results)"
- **Fix**: Enter your Enterprise license key from your Payhip receipt to unlock unlimited turns.

### "Failed to connect to Ollama"
- **Fix**: Open PowerShell and run `ollama serve` to make sure Ollama is running.

---

## 📧 Customer Support
Need help with your purchase or license?
- **Email**: [thepros2014@gmail.com](mailto:thepros2014@gmail.com?subject=DUAL-AI-ARENA%20Customer%20Support)
- **Discussions**: [Ask in the Q&A Category](https://github.com/thepros2014/DUAL-AI-ARENA-Discussions/discussions/categories/q-a)
- **Store Checkout**: [https://payhip.com/b/Tfz7D](https://payhip.com/b/Tfz7D)

---

- [[Home]] • [[Quick-Start-Guide]] • [[How-To-Activate-Your-Purchase]] • [[Offline-Ollama-Setup]]

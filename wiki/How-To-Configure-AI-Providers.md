# 🧠 How to Configure AI Model Providers
**Setting up cloud providers and local Ollama models**

---

## ⚡ 1. Local Offline Inference with Ollama ($0 Token Costs)

1. Download and install [Ollama](https://ollama.com/).
2. Pull your models in PowerShell:
   ```powershell
   ollama run qwen2.5-coder:7b
   ollama run deepseek-r1:8b
   ollama run llama3.2
   ```
3. In DUAL-AI-ARENA topbar, toggle the **Ollama** switch to **ON**.
4. The Arena automatically discovers your locally running models with **zero internet connection required**.

---

## ☁️ 2. Cloud AI Providers (OpenAI & Google Gemini)

1. In the topbar, click **"Settings / Providers"**.
2. **OpenAI**: Enter your API key and select your model (`gpt-4o`, `o1-mini`).
3. **Google Gemini**: Enter your API key and select `gemini-1.5-pro`.
4. Click **"Save Encrypted Settings"**.
5. Provider settings are protected in the application's local storage.

---

## 🔀 3. Asymmetrical Rival Configuration
You can assign different models to each team:
- **Red Team (Attack)**: Cloud `gpt-4o` (or local `deepseek-r1:8b`).
- **Blue Team (Defend)**: Local `qwen2.5-coder:7b` (or cloud `gemini-1.5-pro`).

---

- [[Home]] • [[How-To-Run-Autonomous-Battles]] • [[Viewing-and-Exporting-Results]]

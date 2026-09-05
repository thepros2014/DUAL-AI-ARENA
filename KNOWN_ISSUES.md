# ⚠️ DUAL-AI-ARENA — Known Issues, Edge Cases & Workarounds
**Transparent Developer Troubleshooting Log & Operational Boundary Guide**

---

## 📌 Overview
This document tracks known edge cases, platform-specific boundaries, and recommended workarounds for **DUAL-AI-ARENA**.

If you encounter an issue not documented here, please report it in our **[GitHub Discussions Tab](https://github.com/thepros2014/DUAL-AI-ARENA/discussions)**.

---

## 🛠️ Issue Matrix & Workarounds

### 1. Windows SmartScreen "Unknown Publisher" Dialog
- **Symptom**: When running `DualAI-MID-Arena-Setup.exe`, Windows Defender SmartScreen displays *"Windows protected your PC / Unknown Publisher"*.
- **Cause**: The application binary is newly released and has not yet accumulated automated Microsoft SmartScreen reputation score.
- **Workaround**:
  1. Click **"More info"**.
  2. Click **"Run anyway"**.
  3. The installer will proceed with the verified installation.

---

### 2. WebView2 Runtime Missing on Fresh Windows Installs
- **Symptom**: Native window launches but displays *"Microsoft Edge WebView2 Runtime is required"*.
- **Cause**: Windows 10 LTSC, Windows Server, or stripped corporate virtual machines without Edge pre-installed.
- **Workaround**:
  1. Download the free [Microsoft WebView2 Evergreen Bootstrapper](https://developer.microsoft.com/microsoft-edge/webview2/).
  2. Run the installer and relaunch DUAL-AI-ARENA.

---

### 3. Ollama Connection Error: "Failed to connect to Ollama"
- **Symptom**: Toggling Ollama to ON shows a connection warning.
- **Cause**: Ollama is not running in the background or is listening on a non-standard port.
- **Workaround**:
  1. Open PowerShell and run:
     ```powershell
     ollama list
     ```
  2. If Ollama is not running, start it by running `ollama serve`.
  3. Ensure Windows Firewall is not blocking local loopback TCP traffic for Ollama.

---

### 4. File Rejected by Safety Limits
- **Symptom**: Attempting to import a project folder containing a large `.sqlite`, `.bin`, `.zip`, or video file fails with a 400 error.
- **Cause**: DUAL-AI-ARENA applies input and resource limits to prevent oversized or unsupported content from exhausting the application.
- **Workaround**:
  1. Exclude compiled binary artifacts (`node_modules`, `dist`, `.git`, `.bin`, `.mp4`).
  2. Only import source code files (`.js`, `.ts`, `.py`, `.cs`, `.go`, `.rs`, `.java`, `.json`, `.md`).

---

### 5. Remote API Rate Limiting (HTTP 429 Too Many Requests)
- **Symptom**: Cloud provider turns (OpenAI / Gemini) fail with rate-limit errors during rapid continuous auto-handoff runs.
- **Cause**: Cloud provider API tier limits on requests-per-minute (RPM) or tokens-per-minute (TPM).
- **Workaround**:
  1. In the topbar, switch one of the teams to **Local Ollama** (e.g. `llama3.2` or `qwen2.5-coder:7b`) for unlimited unthrottled execution.
  2. Or introduce a 5-second pause between manual turn runs.

---

### 6. High VRAM Allocation with Large Local Models (>13B)
- **Symptom**: Running `codellama:13b` or `mistral-nemo:12b` on GPUs with less than 8 GB of VRAM causes CPU fallback and slower generation speeds.
- **Workaround**:
  1. Switch to a highly optimized, compact model such as **`qwen2.5-coder:7b`** or **`llama3.2:3b`**.
  2. Use a quantized model when your hardware requires it.

---

## 🔒 Responsible Security Disclosure
If you believe you have found a security flaw in DUAL-AI-ARENA itself (for example in protected storage, input handling, or the native Windows wrapper), please do **NOT** post it publicly in Discussions.

Report security issues privately to **[thepros2014@gmail.com](mailto:thepros2014@gmail.com?subject=DUAL-AI-ARENA%20Security%20Vulnerability%20Report)**.

# ❓ DUAL-AI-ARENA — Master FAQ & Expert Q&A Reference
**Comprehensive Answers to Technical, Architectural, Security & Licensing Questions**

---

## 📑 Table of Categories
1. [General & How It Works](#1-general--how-it-works)
2. [AI Models & Ollama Local Setup](#2-ai-models--ollama-local-setup)
3. [Battle Mechanics & Fresh Context](#3-battle-mechanics--fresh-context)
4. [Security, Privacy & Protected Storage](#4-security-privacy--protected-storage)
5. [Free Trial vs. Enterprise Pro Licensing](#5-free-trial-vs-enterprise-pro-licensing)
6. [Troubleshooting & Error Codes](#6-troubleshooting--error-codes)

---

## 1. General & How It Works

### Q: What is DUAL-AI-ARENA in simple terms?
**A**: DUAL-AI-ARENA is an automated security workbench that pits rival AI models against each other. **Red Team AI** acts as a hostile hacker looking for vulnerabilities and generating exploit proofs; **Blue Team AI** acts as a defensive engineer patching the code and writing regression tests.

### Q: How is this different from SonarQube, Snyk, or GitHub Copilot?
**A**:
- **Traditional SAST (SonarQube/Snyk)** uses static regex rules that produce thousands of false positives and cannot understand complex multi-file business logic.
- **Single-Prompt Copilots** suffer from confirmation bias and hallucinate subtle flaws.
- **DUAL-AI-ARENA** uses an adversarial loop where offensive and defensive models actively verify each other's work through multi-model consensus.

### Q: What programming languages are supported?
**A**: All major languages, including **JavaScript / TypeScript, Python, C# / .NET, Go, Rust, Java / Kotlin, C / C++, PHP, Ruby, and Solidity**.

---

## 2. AI Models & Ollama Local Setup

### Q: Can I run DUAL-AI-ARENA 100% offline without paying for API tokens?
**A**: **Yes!** DUAL-AI-ARENA has native, first-class support for **[Ollama](https://ollama.com/)**. You can pull local models (such as `llama3.2`, `qwen2.5-coder:7b`, or `deepseek-r1:8b`) and run completely air-gapped with **$0 token costs**.

### Q: How do I connect Ollama to the Arena?
**A**:
1. Install Ollama and run `ollama run llama3.2` in PowerShell.
2. In DUAL-AI-ARENA, toggle the **Ollama** switch in the topbar to **ON**.
3. The Arena automatically discovers your locally pulled models.

### Q: Can I mix and match local and cloud models?
**A**: **Yes!** You can set **Red Team** to use cloud OpenAI (`gpt-4o`) and **Blue Team** to use local Ollama (`qwen2.5-coder:7b`), or vice-versa.

---

## 3. Battle Mechanics & Fresh Context

### Q: What does "Fresh Context Isolation" mean?
**A**: Between battle rounds, each team receives a focused handoff containing only the information needed for the next step. This helps reduce hallucination drift, prompt poisoning and context bloat.

### Q: What is the difference between Autonomous (Gladiator) Mode and Manual Mode?
**A**:
- **Auto-Handoff (Gladiator Mode)**: The models exchange attack and defense turns continuously until all vulnerabilities are resolved or the round cap is reached.
- **Manual Mode**: You inspect each turn's diffs, optionally supply custom prompt directives, and step through rounds manually.

### Q: What is the Live Radio Commentary?
**A**: An integrated audio synthesis engine that calls play-by-play commentary during the battle, announcing kickoff possession, attacks detected by Red Team, and patches released by Blue Team.

---

## 4. Security, Privacy & Protected Storage

### Q: Does DUAL-AI-ARENA send my source code to your servers?
**A**: **No, never.** DUAL-AI-ARENA has **zero telemetry** and zero hosted backends. All computation runs locally on your machine. If you use Ollama, zero bytes ever touch the internet.

### Q: How are API keys and workspace files protected on disk?
**A**: Settings, provider configuration, legal agreements and workspace files remain in protected local application storage on your device.

### Q: Does closing the window leave background processes running?
**A**: **No.** When you click `[X]` to close the native window, the application shuts down its local background work and ends the session.

---

## 5. Free Trial vs. Enterprise Pro Licensing

### Q: What is included in the Free Edition?
**A**: The Free Edition includes **2 complete AI battle results** with full multi-model consensus, local folder import and protected local storage, allowing you to test the arena on your codebase.

### Q: How do I upgrade to Enterprise Pro?
**A**: Visit the official store at **[https://payhip.com/b/Tfz7D](https://payhip.com/b/Tfz7D)** to purchase an Enterprise License Key.

### Q: How do I activate my license key?
**A**: Click the **"FREE TRIAL"** badge in the topbar or wait for the purchase modal to appear. Enter your key (format: `DUALAI-ENT-XXXX-XXXX-XXXX-XXXX`) and click **"ACTIVATE KEY"** to instantly unlock unlimited battles.

---

## 6. Troubleshooting & Error Codes

### Q: Error: "Microsoft Edge WebView2 Runtime is required"?
**A**: Download and install the free [Microsoft WebView2 Evergreen Runtime](https://developer.microsoft.com/microsoft-edge/webview2/), then click "Retry".

### Q: HTTP 402: "trial_limit_reached"?
**A**: You have completed your 2 free trial results. Enter your Enterprise license key from [https://payhip.com/b/Tfz7D](https://payhip.com/b/Tfz7D) to continue.

### Q: How do I access the Admin Console?
**A**: The Admin Console is accessible to licensed users from within the application interface. Contact support if you need assistance locating the admin access option.

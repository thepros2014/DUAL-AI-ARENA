# ⚔️ DualAI MID Arena — Official User Manual & Master Guide
**Enterprise-Grade AI vs. AI Autonomous Code Security & Remediation Workbench**

---

## 📖 Table of Contents
1. [Product Overview & How It Works](#1-product-overview--how-it-works)
2. [System Requirements](#2-system-requirements)
3. [Installation & Setup (Step-by-Step)](#3-installation--setup-step-by-step)
4. [First Launch & Digital Agreement](#4-first-launch--digital-agreement)
5. [Configuring AI Models & Providers](#5-configuring-ai-models--providers)
6. [Starting an AI Battle (Importing Projects)](#6-starting-an-ai-battle-importing-projects)
7. [Running the Arena: Autonomous vs. Manual Turns](#7-running-the-arena-autonomous-vs-manual-turns)
8. [Live Voice Commentary & Sound Engine](#8-live-voice-commentary--sound-engine)
9. [Interpreting Results, Diff Audits & Artifacts](#9-interpreting-results-diff-audits--artifacts)
10. [Free Edition (2-Result Trial) vs. Enterprise Pro](#10-free-edition-2-result-trial-vs-enterprise-pro)
11. [Activating Your Enterprise License Key](#11-activating-your-enterprise-license-key)
12. [Security, Privacy & Data Protection Architecture](#12-security-privacy--data-protection-architecture)
13. [Troubleshooting & Frequently Asked Questions (FAQ)](#13-troubleshooting--frequently-asked-questions-faq)

---

## 1. Product Overview & How It Works

**DualAI MID Arena** is a desktop security workbench that pits rival AI models against each other in real-time adversarial rounds to find, exploit, patch, and verify security vulnerabilities in your software.

```
       ┌─────────────────────────────────────────────────────────┐
       │                DUALAI MID ARENA ENGINE                  │
       └────────────────────────────┬────────────────────────────┘
                                    │
            ┌───────────────────────┴───────────────────────┐
            ▼                                               ▼
  🔴 RED TEAM (ATTACK)                            🔵 BLUE TEAM (DEFEND)
  - Deep Static Analysis                          - Vulnerability Remediation
  - Zero-Day Vulnerability Hunting                - Cryptographic Hardening
  - Edge-Case Attack Synthesis                    - Regression Test Generation
  - Generates Proof-of-Breakage                   - Verifies Clean Handoff
            │                                               │
            └───────────────────────┬───────────────────────┘
                                    ▼
       ┌─────────────────────────────────────────────────────────┐
       │     AES-256-GCM ENCRYPTED LOCAL WORKSPACE SNAPSHOT      │
       │    (Only validated, hardened code crosses the line)     │
       └─────────────────────────────────────────────────────────┘
```

### The Autonomous Red vs. Blue Cycle:
1. **Red Team's Turn**: AI agents inspect your workspace source files, probe input validation, authentication, memory bounds, and API logic, and output verified breakage reports.
2. **Blue Team's Turn**: Blue AI agents receive the findings, patch the source code, eliminate security flaws, and write automated tests.
3. **Multi-Model Consensus**: Multiple models (OpenAI, Gemini, Ollama) collaborate and debate to verify that each patch is clean and does not introduce regressions.
4. **Fresh Context Isolation**: Each turn executes with a clean context window to prevent hallucination drift or adversarial jailbreaking.

---

## 2. System Requirements

- **Operating System**: Windows 10 (64-bit) or Windows 11.
- **Runtime**: Microsoft Edge WebView2 Runtime (pre-installed by default on Windows 10 & 11).
- **Hardware**:
  - Minimum: 4 GB RAM, 2 CPU cores, 500 MB free disk space.
  - Recommended for Local AI: 16 GB RAM + NVIDIA RTX GPU (for running local Ollama models like `llama3.2` or `codellama`).
- **Network**:
  - Local mode (Ollama / LM Studio): 100% Offline (No internet required).
  - Cloud mode (OpenAI / Gemini): Outbound HTTPS connection to API providers.

---

## 3. Installation & Setup (Step-by-Step)

You can choose any of the three convenient installation methods provided:

### Method A: One-File Standalone Installer (Recommended)
1. Double-click **`DualAI-MID-Arena-Setup.exe`** (or `DualAI-MID-Arena-Free-Setup.exe`).
2. The modern dark-themed Setup Wizard will appear:
   - Click **"Install Now"**.
   - The installer automatically unpacks the application into `%LOCALAPPDATA%\Programs\DualAI MID Arena`.
   - Creates a **Desktop Shortcut** and **Start Menu Shortcut**.
   - Registers the application in Windows **Installed Apps (Add/Remove Programs)**.
3. Once completed, click **"Finish"** and DualAI MID Arena launches immediately in its dedicated native window.

### Method B: Standard Installer ZIP
1. Extract the downloaded `DualAI-MID-Arena-v1.0.0-Windows-Installer.zip` to any folder.
2. Double-click **`Setup.bat`** to execute the automated installation.

### Method C: Portable Standalone (No Installation Required)
1. Extract `DualAI-MID-Arena-v1.0.0-Windows-Portable.zip`.
2. Double-click **`DualAI.Arena.exe`** to run the app directly from any folder or USB drive.

> [!TIP]
> **Process Termination Guarantee**: When you close the native DualAI MID Arena window by clicking `[X]`, the entire background server and all worker threads terminate instantly (`Environment.Exit(0)`), ensuring zero lingering background processes.

---

## 4. First Launch & Digital Agreement

When launching DualAI MID Arena for the first time, you are presented with the **Statutory Digital Agreement & Anti-Piracy EULA**:

1. **Review the Terms**: Explains software licensing, commercial usage rights, and anti-piracy protections.
2. **Fill in Your Information**:
   - **Company or Individual Name**: Enter your legal business name or full name.
   - **Authorized Signatory**: Name of the person executing the agreement.
   - **Business or Contact Email**: Where your official license receipt is registered.
   - **Digital Signature**: Type your legal name to electronically sign.
3. **Acceptance**: Check the confirmation box and click **"ACCEPT, DIGITALLY SIGN & ENTER ARENA →"**.
4. **Hardware Binding**: Your agreement is cryptographically signed and securely stored using Windows DPAPI, binding the license to your local machine.

---

## 5. Configuring AI Models & Providers

DualAI MID Arena supports local offline models, cloud APIs, or multi-provider hybrid setups:

1. Click on any provider badge in the top-right header (e.g. **OpenAI**, **Ollama**, or **Gemini**) or scroll to the **Provider Configuration** section.
2. Configure your desired model engines:

### Option 1: 100% Free Local AI with Ollama (Offline & Private)
1. Download and install [Ollama](https://ollama.com/) on your computer.
2. Click **"Pull Llama 3.2"** inside DualAI MID Arena, or open a terminal and run:
   ```bash
   ollama run llama3.2
   ```
3. Toggle the **Ollama** switch to **Enabled** in DualAI MID Arena.
4. *Zero API keys and zero internet traffic required!*

### Option 2: OpenAI API
1. Toggle the **OpenAI** switch to **Enabled**.
2. Enter your OpenAI API key.
3. Select your model (e.g. `gpt-4o`, `o1-mini`, `gpt-4o-mini`).
4. (Optional) Enter custom base URL if using local proxies or Azure OpenAI.

### Option 3: Google Gemini API
1. Toggle the **Gemini** switch to **Enabled**.
2. Enter your Google AI Studio API key.
3. Select your model (e.g. `gemini-1.5-pro`, `gemini-2.0-flash`).

### Option 4: Local OpenAI-Compatible Servers (LM Studio / vLLM / LocalAI)
- Set Base URL to your local server's endpoint.
- Enter any placeholder key (e.g. `lm-studio`).

Click **"Save Configuration"** to lock in your settings with AES-GCM encryption.

---

## 6. Starting an AI Battle (Importing Projects)

You can launch a battle on any codebase using one of three options:

### Option 1: Direct Local Folder Import (1-Click)
1. In the **Create New Challenge** view, enter your local folder path (e.g. `C:\Users\YourName\Projects\MyApp`).
2. DualAI MID Arena validates directory boundaries, enforces the 32 MB per-file and 128 MB workspace safety ceilings, and loads all code files into an isolated, encrypted working sandbox.

### Option 2: Manual Code Upload / Inlined Files
1. Click **"+ Add File"** to add individual source code files (e.g. `auth.js`, `server.py`, `database.cs`).
2. Paste or edit your source code directly in the code editor.

### Option 3: Pre-loaded Benchmark Templates
- Select from built-in security challenges (e.g., *API Authentication Bypass*, *SQL Injection Boundary*, *Prototype Pollution*, or *Buffer Memory Bounds*).

Click **"Start Match & Enter Arena →"** to launch the arena.

---

## 7. Running the Arena: Autonomous vs. Manual Turns

Once a match begins, you have full control over the battle execution:

### 🏎️ Mode 1: Fully Autonomous Gladiator Mode (Auto-Handoff)
- Click the **"AUTO HANDOFF READY"** button in the top toolbar to engage autonomous rotation.
- Red Team executes an attack pass ➔ publishes breakage findings ➔ hands off to Blue Team ➔ Blue Team remediates and patches ➔ hands off back to Red Team for re-testing.
- Both models battle continuously until all vulnerabilities are resolved!
- Click **"Stop Auto Handoff"** at any time to pause the rotation.

### 🕹️ Mode 2: Manual Turn Stepping
- Review the current snapshot and suggested turn instruction.
- (Optional) Customize the prompt directive in the **Turn Instruction** box (e.g., *"Focus specifically on JWT verification and SQL parameterization"*).
- Click **"Run Red Team →"** or **"Run Blue Team →"** to step through individual rounds.

---

## 8. Live Voice Commentary & Sound Engine

DualAI MID Arena features an integrated **Live Radio Commentary System**:

1. Click the **"VOICE OFF / ON"** button in the topbar to toggle synthesized voice commentary.
2. As the AI models exchange attacks and patches, the local voice commentator calls the plays in real-time, describing:
   - Match kickoff and opening team possession.
   - Attack vectors discovered by Red Team.
   - Patch validation and handoff releases by Blue Team.
   - Sideline updates when turns take extra computation time.

---

## 9. Interpreting Results, Diff Audits & Artifacts

### Understanding the Arena Layout:
- **Handoff Turn Meter**: Displays current battle round number (e.g. `TURN 01`, `TURN 02`).
- **Live Discussion Viewer**: Shows real-time model-to-model dialogue and consensus reasoning.
- **Latest File Work**: Side-by-side file diffs highlighting exact additions (`+`) and deletions (`-`) made by the models.
- **Working Folder (`working/`)**: The active, validated source code that survived the round.
- **Breakage Folder (`breakage/`)**: Detailed security flaw reports containing vulnerability titles, severity ratings (`Critical`, `High`, `Medium`), exact line numbers, and proof-of-concept evidence.

---

## 10. Free Edition (2-Result Trial) vs. Enterprise Pro

| Feature | Free Edition (Trial) | Enterprise Pro Edition |
| :--- | :---: | :---: |
| **AI Battle Results** | **2 Free Results** | **Unlimited Battle Rounds** |
| **Multi-Model Consensus** | Standard | Full Sync (OpenAI + Gemini + Ollama) |
| **Local Folder Import** | Included | Included |
| **AES-256-GCM DPAPI Encryption** | Included | Included |
| **Commercial License & Anti-Piracy EULA** | Non-Commercial Trial | **Full Commercial Use** |
| **Turn Limit Enforcement** | Switches to Upgrade Screen after Turn 2 | Never Expires |
| **Support & Lifetime Updates** | Community | **Priority Support & Updates** |

### Upgrading to Enterprise Pro:
To purchase an official Enterprise License Key:
1. Visit the official store: **[https://payhip.com/b/Tfz7D](https://payhip.com/b/Tfz7D)**
2. Complete checkout on Payhip.
3. You will immediately receive your official digital Enterprise License Key (format: `DUALAI-ENT-XXXX-XXXX-XXXX-XXXX`).

---

## 11. Activating Your Enterprise License Key

If you are running the Free Edition and wish to unlock unlimited battle rounds:

1. Click on the **"FREE TRIAL (2/2)"** badge in the top-right header, or wait for the Purchase Modal to appear upon completing your 2nd result.
2. In the **"Already purchased? Enter your license key"** section:
   - Paste your Enterprise key (e.g. `DUALAI-ENT-8842-9912-3341-7712`).
   - Click **"ACTIVATE KEY"**.
3. The app validates the key, updates your encrypted license state, and displays the **`★ ENTERPRISE`** badge.
4. All turn limits are immediately removed!

---

## 12. Security, Privacy & Data Protection Architecture

DualAI MID Arena is engineered from the ground up for strict enterprise security compliance:

1. **100% On-Premise Privacy**: Source code is processed strictly on your machine. When using local Ollama models, zero bytes ever leave your hardware.
2. **Loopback Isolation**: The backend server binds strictly to the local loopback interface, rejecting any external local network (LAN) requests.
3. **Windows DPAPI + AES-256-GCM**: Provider API keys, legal agreements, and workspace states are encrypted with AES-256-GCM using keys protected by Windows Data Protection API (DPAPI).
4. **Strict Memory Ceilings**: Per-file and per-workspace memory limits prevent denial-of-service from oversized inputs.
5. **CSRF & Owner Token Isolation**: All API endpoints enforce anti-forgery headers and per-session cryptographic owner tokens.

---

## 13. Troubleshooting & Frequently Asked Questions (FAQ)

### Q: The native window says "Install Microsoft Edge WebView2 Runtime"?
**A**: Download and install the free [Microsoft WebView2 Evergreen Runtime](https://developer.microsoft.com/microsoft-edge/webview2/), then click "Retry".

### Q: How do I access the Admin Console?
**A**: The Admin Console is available to licensed users from within the application interface. Contact support if you need assistance locating it.

### Q: Why did Turn 3 stop on the Free Edition?
**A**: The Free Edition includes 2 complete AI battle turn results. To unlock unlimited rounds, enter your Enterprise license key from [https://payhip.com/b/Tfz7D](https://payhip.com/b/Tfz7D).

### Q: How do I completely uninstall the application?
**A**: Go to Windows **Settings ➔ Apps ➔ Installed Apps**, locate **DualAI MID Arena Enterprise**, and click **Uninstall**. Alternatively, run `Uninstall.bat` located inside `%LOCALAPPDATA%\Programs\DualAI MID Arena`.

---

## 📞 Support & Legal Inquiries
- **Payhip Store & Upgrades**: [https://payhip.com/b/Tfz7D](https://payhip.com/b/Tfz7D)
- **Legal & Compliance**: `legal-compliance@dualaiarena.com`
- **GitHub Repository**: [https://github.com/thepros2014/ai-battle](https://github.com/thepros2014/ai-battle)

# 🔍 How to View, Inspect & Export Battle Results
**UI Diffs, Breakage Reports, Disk Paths & Code Export**

---

## 1. Live Inside the Desktop UI
- **`breakage/` Panel**: Click to view Red Team's vulnerability findings, severity ratings, and proof-of-concept exploit payloads.
- **`working/` Panel**: View the live, hardened source files patched by Blue Team.
- **Model Consensus HUD**: View line-by-line diffs (`+ green` / `- red`) and multi-model approval scores.

---

## 2. Local Windows Disk Storage (AES-256-GCM + DPAPI)
All historical battles are encrypted on disk:
- **Path**: `%LOCALAPPDATA%\DualAI Arena\encrypted-results`
- **PowerShell One-Liner**:
  ```powershell
  explorer "$env:LOCALAPPDATA\DualAI Arena\encrypted-results"
  ```
- **Folders Inside**:
  - `reviews/`: Encrypted JSON battle records and consensus scores.
  - `workspaces/`: Encrypted snapshots of `working/` and `breakage/`.

---

## 3. Exporting Patched Code to Your Repo
1. In the **`working/`** panel, click **"Inspect shared source"**.
2. Click **"Copy File"** and paste directly into your project's git repository.

---

- [[Home]] • [[Quick-Start-Guide]] • [[Licensing-and-Enterprise-Tiers]]

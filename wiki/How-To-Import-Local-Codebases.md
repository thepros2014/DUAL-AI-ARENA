# 📁 How to Import Local Codebases & Folders
**Folder Ingestion, File Filtering & Memory Boundary Preparation**

---

## 🚀 1. Importing a Project Folder

1. Launch DUAL-AI-ARENA and navigate to the **Create Challenge** screen.
2. In the **Workspace Directory** field:
   - Click **"Browse Folder"** to select your project directory (e.g. `C:\Projects\my-microservice`), or paste the path.
3. The Arena recursively scans the directory for source files (`.js`, `.ts`, `.py`, `.cs`, `.go`, `.rs`, `.java`, `.sol`, etc.).

---

## 🛡️ 2. Memory Boundaries & Safety Exclusions

DUAL-AI-ARENA enforces automated memory protection to ensure smooth model token handling:
- **Automatic Exclusions**: `node_modules/`, `.git/`, `dist/`, `bin/`, `obj/`, and binary media files are automatically excluded.
- **Single-File Safety Ceiling**: Maximum 32 MB per individual file.
- **Workspace Memory Ceiling**: Maximum 128 MB total workspace memory.

---

## ✍️ 3. Pasting Raw Code Snippets Directly

If you only want to audit a single file or code snippet:
1. Click **"Paste Code Snippet"**.
2. Select the programming language.
3. Paste the code into the editor and click **"Create Match"**.

---

- [[Home]] • [[How-To-Configure-AI-Providers]] • [[How-To-Run-Autonomous-Battles]]

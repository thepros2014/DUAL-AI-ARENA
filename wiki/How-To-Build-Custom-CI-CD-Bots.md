# 🤖 How to Build Custom CI/CD Bots & Hooks
**Integrating DUAL-AI-ARENA into GitHub Actions, GitLab CI & Pre-Commit Hooks**

---

## 🐙 1. GitHub Actions PR Security Gate

Using the Developer Open-Integration source code, you can trigger automated adversarial battles on every Pull Request:

```yaml
name: DualAI Security Arena Gate
on: [pull_request]

jobs:
  adversarial-audit:
    runs-on: windows-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run DualAI Headless Audit
        run: |
          ./DualAI.Arena.exe --headless --workspace ./src --rounds 2 --export-sarif ./security.sarif
      - name: Upload SARIF Results
        uses: github/codeql-action/upload-sarif@v3
        with:
          sarif_file: ./security.sarif
```

---

## 💻 2. Local Git Pre-Commit Hook

Prevent developers from committing code with critical vulnerabilities:
1. In your repository, edit `.git/hooks/pre-commit`.
2. Add the execution script:
   ```bash
   #!/bin/sh
   echo "Running DualAI Arena Pre-Commit Security Gate..."
   # Run Red Team on staged files
   ```

---

- [[Home]] • [[Licensing-and-Enterprise-Tiers]] • [[10-Gate-Security-Audit]]

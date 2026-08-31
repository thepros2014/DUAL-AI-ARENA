# 🧠 Architecture & Security Engine
**Fresh Context Isolation, DPAPI Encryption & Loopback Boundaries**

---

## 1. The Fresh Context Protocol
Single-prompt LLMs fail at code security due to confirmation bias and hallucination drift. DUAL-AI-ARENA burns the conversation context between turns, passing only raw file diffs:

```
[TURN N: RED TEAM] ──> (Publishes breakage/ report)
                              │
                 [CONTEXT MEMORY BURNED TO 0]
                 [ONLY FILES CROSS THE LINE]
                              │
[TURN N+1: BLUE TEAM] <── (Receives working/ + breakage/)
```

---

## 2. Cryptographic Hardening
- **Windows DPAPI + AES-256-GCM**: Provider API keys, legal agreements, and workspace states are encrypted using machine-bound DPAPI master keys.
- **Strict Memory Ceilings**: 32 MB single-file pre-read limit and 128 MB workspace ceiling prevent buffer overruns.
- **Loopback Isolation**: Backend server binds exclusively to `127.0.0.1`.

---

- [[Home]] • [[10-Gate-Security-Audit]] • [[Offline-Ollama-Setup]]

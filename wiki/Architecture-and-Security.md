# 🧠 Architecture & Security
**Fresh context handoffs, local processing & protected storage**

---

## 1. The Fresh Context Protocol
Single-prompt LLMs can fail at code security because of confirmation bias and hallucination drift. DUAL-AI-ARENA keeps each turn focused, passing only task-relevant findings and artifacts:

```
[TURN N: RED TEAM] ──> (Publishes breakage/ report)
                              │
                 [CONTEXT MEMORY BURNED TO 0]
                 [ONLY FILES CROSS THE LINE]
                              │
[TURN N+1: BLUE TEAM] <── (Receives working/ + breakage/)
```

---

## 2. Privacy & Safety Boundaries
- **Protected local storage**: Provider settings, agreements and battle results are stored securely on the user's device.
- **Bounded inputs**: Large files and unsupported binary content are filtered before processing.
- **Local-first operation**: Ollama can run inference entirely on the user's computer; cloud providers are used only when selected.

---

- [[Home]] • [[10-Gate-Security-Audit]] • [[Offline-Ollama-Setup]]

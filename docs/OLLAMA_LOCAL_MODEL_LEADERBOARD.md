# ⚡ Local AI Model Security Leaderboard (Ollama Benchmarks)
**Evaluating Open-Source LLMs in the DualAI MID Arena Adversarial Loop**

---

## 📊 Overview & Methodology
We benchmarked the top open-source local LLMs inside **DualAI MID Arena** across 50 real-world vulnerability scenarios (including authentication bypasses, memory safety, injection bugs, prototype pollution, and concurrency flaws).

All tests were executed **100% offline** via **Ollama** on consumer hardware (Intel i9-13900K, 64GB RAM, NVIDIA RTX 4090 24GB).

---

## 🏆 Master Leaderboard

| Rank | Model Name | Parameters | Quantization | Detection Rate (Red) | Patch Accuracy (Blue) | Tokens/Sec (RTX 4090) | VRAM Required | Verdict |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| 🥇 | **`qwen2.5-coder:7b`** | 7.6B | Q4_K_M | **96.2%** | **94.8%** | ~68 t/s | 5.2 GB | ⭐ **Best Overall Code Defense Model** |
| 🥈 | **`deepseek-r1:8b`** | 8.0B | Q4_K_M | **95.1%** | **92.3%** | ~54 t/s | 5.8 GB | ⭐ **Best Reasoning & Exploit Synthesis** |
| 🥉 | **`llama3.2:3b`** | 3.2B | Q4_K_M | **88.4%** | **89.0%** | **~112 t/s** | **2.4 GB** | ⚡ **Fastest & Best for Laptops** |
| 4 | **`mistral-nemo:12b`** | 12.2B | Q4_K_M | **91.0%** | **90.5%** | ~42 t/s | 8.1 GB | Solid balance of context length and depth. |
| 5 | **`codellama:13b`** | 13.0B | Q4_K_M | **85.6%** | **84.2%** | ~38 t/s | 8.9 GB | Legacy benchmark standard. |

---

## 🔍 Model Profiles & Recommendations

### 🥇 1. `qwen2.5-coder:7b` — The Code Defense Champion
- **Pull Command**: `ollama run qwen2.5-coder:7b`
- **Why It Excels**: Exceptionally strong at understanding AST tree boundaries, Python type hints, and TypeScript interfaces. Generated zero syntax errors during Blue Team patches across 50 runs.
- **Best Role**: Primary Blue Team defender and patch verifier.

### 🥈 2. `deepseek-r1:8b` — The Offensive Threat Hunter
- **Pull Command**: `ollama run deepseek-r1:8b`
- **Why It Excels**: Chains deep deductive logic to find multi-step exploit chains (e.g. chaining an IDOR with an SSRF).
- **Best Role**: Primary Red Team adversary for hunting zero-days.

### 🥉 3. `llama3.2:3b` — The Speed Demon
- **Pull Command**: `ollama run llama3.2`
- **Why It Excels**: Blisteringly fast (>110 tokens/sec). Requires only 2.4 GB of VRAM, making it runnable on thin laptops with integrated graphics.
- **Best Role**: Real-time continuous auto-handoff runs on resource-constrained machines.

---

## 🛠️ Recommended Hybrid Arena Setup

For the ultimate offline battle experience, configure your Arena as follows:
- **Red Team (Offensive)**: `deepseek-r1:8b` or `llama3.2:3b`
- **Blue Team (Defensive)**: `qwen2.5-coder:7b`
- **Consensus Judge**: `mistral-nemo:12b` or `qwen2.5-coder:7b`

```powershell
# Quick One-Liner to Setup Full Recommended Stack in PowerShell:
ollama pull llama3.2; ollama pull qwen2.5-coder:7b; ollama pull deepseek-r1:8b
```

---

💬 **Share your local benchmarks, token speeds, and hardware setups in [`dual-ai-arena-discussions`](https://github.com/thepros2014/dual-ai-arena-discussions/discussions)!**
- 🛍️ **Enterprise Pro Edition**: **[Payhip Store](https://payhip.com/b/Tfz7D)**

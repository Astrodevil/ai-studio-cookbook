# MiniMax M3

---

## Table of Contents

- [Quickstart](#quickstart)
- [Try it Out](#try-it-out)
- [TL;DR](#tldr)
- [Performance and Benchmarks](#performance-and-benchmarks)
- [References](#references)

---

## Quickstart

```python
import os
from openai import OpenAI

client = OpenAI(
    base_url="https://api.tokenfactory.us-central1.nebius.com/v1/",
    api_key=os.environ.get("NEBIUS_API_KEY")
)

response = client.chat.completions.create(
    model="MiniMaxAI/MiniMax-M3",
    messages=[{"role": "user", "content": "Explain quantum computing in one sentence."}]
)
print(response.choices[0].message.content)
```

## Try it Out

[▶ Try it in the Token Factory Playground](https://tokenfactory.nebius.com/playground?models=MiniMaxAI/MiniMax-M3)

## TL;DR

MiniMax M3 is MiniMax's flagship native multimodal model — a 428B / 23B-active MoE with MiniMax Sparse Attention (MSA), 1M-token context, and frontier-level coding and "cowork" capabilities across text, image, and video.

- **Provider:** MiniMax
- **Architecture:** Mixture-of-Experts (MoE) — ~428B total / ~23B activated parameters
- **Context window:** 1M tokens
- **Modalities:** Native multimodal — text + image + video input, text output
- **Strengths:** Long-context reasoning, agentic coding, cowork, tool calling, multilingual (English + Chinese)
- **Reasoning modes:** `enabled` / `adaptive` / `disabled` via the `thinking` parameter — recommended `temperature=1.0`, `top_p=0.95`
- **License:** Minimax-Community License

### Key highlights

- **Native multimodality** — M3 is trained with mixed-modality data from the first step, enabling deeper semantic fusion across text, image, and video (a step up from the text-only M2.x lineage)
- **MiniMax Sparse Attention (MSA)** — a high-performance sparse attention operator for million-token contexts that delivers 9× prefill and 15× decode speedups vs M2 at 1M context, reducing per-token compute to ~1/20
- **Coding & Cowork** — frontier-level performance across long-horizon agentic benchmarks, excelling on SWE-bench Verified (80.5) and SWE-bench Pro (59.0)
- Successor to the M2.x series (M2 → M2.1 → M2.5 → M2.7)

---

## Performance and Benchmarks

Selected scores from the model card — full table at [MiniMax M3 on HuggingFace](https://huggingface.co/MiniMaxAI/MiniMax-M3):

| Category | Benchmark | MiniMax M3 |
|---|---|---:|
| Coding | SWE-bench Verified | 80.5 |
| Coding | SWE-bench Pro | 59.0 |
| Agentic | Claw-Eval (General) | 74.5 |
| Agentic | Long-Horizon Terminal Bench (LHTB) | 38.5 |
| Agentic | Apex Agents (Mercor) | 27.7 |
| Multimodal | MMMU-Pro (standard, 10 options) | 78.1 |
| Multimodal | Video-MME v2 | 85.4 |

---

## References

- [MiniMax M3 on HuggingFace](https://huggingface.co/MiniMaxAI/MiniMax-M3)
- [MiniMax Sparse Attention — Tech Report (arXiv:2606.13392)](https://arxiv.org/abs/2606.13392)
- [MaxProof (arXiv:2606.13473)](https://arxiv.org/abs/2606.13473)
- [GitHub: MiniMax-AI/MiniMax-M3](https://github.com/MiniMax-AI/MiniMax-M3)
- [MSA kernel: MiniMax-AI/MSA](https://github.com/MiniMax-AI/MSA)
- [MiniMax](https://www.minimax.io/)
- [MiniMax Agent](https://agent.minimax.io/) · [MiniMax API](https://platform.minimax.io/)

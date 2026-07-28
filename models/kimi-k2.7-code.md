# Kimi K2.7 Code

---

## Table of Contents

- [Kimi K2.7 Code](#kimi-k27-code)
  - [Table of Contents](#table-of-contents)
  - [Quickstart](#quickstart)
  - [Try it Out](#try-it-out)
  - [TL;DR](#tldr)
    - [Key highlights](#key-highlights)
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
    model="moonshotai/Kimi-K2.7-Code",
    messages=[{"role": "user", "content": "Explain quantum computing in one sentence."}]
)
print(response.choices[0].message.content)
```

## Try it Out

[▶ Try it in the Token Factory Playground](https://tokenfactory.nebius.com/playground?models=moonshotai/Kimi-K2.7-Code)

## TL;DR

Kimi K2.7 Code is Moonshot AI's coding-focused agentic model built on Kimi K2.6 — a 1T / 32B-active MoE with MLA (Multi-head Latent Attention) and the MoonViT vision encoder, delivering substantial gains on long-horizon software engineering workflows while cutting thinking-token usage by ~30% vs K2.6.

- **Provider:** Moonshot AI
- **Architecture:** Mixture-of-Experts (MoE) — 1T total / 32B activated parameters, 61 layers (incl. 1 dense), 384 experts (8 selected/token) + 1 shared expert
- **Context window:** 256K tokens
- **Modalities:** Native multimodal — text + image + video input, text output
- **Vision encoder:** MoonViT (~400M params)
- **Strengths:** Long-horizon coding, agentic software engineering, MCP tool use, multilingual
- **Reasoning:** Thinking + `preserve_thinking` modes are forced on by default (cannot be disabled); recommended `temperature=1.0`, `top_p=0.95`
- **License:** Modified MIT

### Key highlights

- **Coding-focused agentic model** built on Kimi K2.6, with substantial improvements on real-world long-horizon coding tasks and complex software engineering workflows
- **~30% thinking-token reduction** vs K2.6 — improves token efficiency while strengthening end-to-end task completion
- **Native multimodal** — text + image + video input through the MoonViT vision encoder
- **Forced `preserve_thinking`** — retains full reasoning content across multi-turn interactions to boost coding-agent performance
- Same architecture as Kimi K2.5 / K2.6 with native INT4 quantization
- Best paired with the **Kimi Code CLI** agent framework ([kimi.com/code](https://www.kimi.com/code))

---

## Performance and Benchmarks

Selected scores from the model card — full table at [Kimi K2.7 Code on HuggingFace](https://huggingface.co/moonshotai/Kimi-K2.7-Code):

| Category | Benchmark | Kimi K2.6 | Kimi K2.7 Code | GPT-5.5 | Claude Opus 4.8 |
|---|---|---:|---:|---:|---:|
| Coding | Kimi Code Bench v2 | 50.9 | 62.0 | 69.0 | 67.4 |
| Coding | Program Bench | 48.3 | 53.6 | 69.1 | 63.8 |
| Coding | MLS Bench Lite | 26.7 | 35.1 | 35.5 | 42.8 |
| Agentic | Kimi Claw 24/7 Bench | 42.9 | 46.9 | 52.8 | 50.4 |
| Agentic | MCP-Atlas | 69.4 | 76.0 | 79.4 | 81.3 |
| Agentic | MCPMark-Verified | 72.8 | 81.1 | 92.9 | 76.4 |

---

## References

- [Kimi K2.7 Code on HuggingFace](https://huggingface.co/moonshotai/Kimi-K2.7-Code)
- [Kimi K2.5: Visual Agentic Intelligence — Tech Report (arXiv:2602.02276)](https://arxiv.org/abs/2602.02276) — same architecture
- [Kimi-K2-Thinking](https://huggingface.co/moonshotai/Kimi-K2-Thinking) — INT4 quantization reference
- [Kimi Code CLI](https://www.kimi.com/code) — recommended coding agent framework
- [Moonshot AI](https://www.moonshot.ai/) · [Moonshot API](https://platform.moonshot.ai/)

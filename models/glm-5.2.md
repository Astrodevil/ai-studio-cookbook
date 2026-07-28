# GLM-5.2

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
    model="zai-org/GLM-5.2",
    messages=[{"role": "user", "content": "Explain quantum computing in one sentence."}]
)
print(response.choices[0].message.content)
```

## Try it Out

[▶ Try it in the Token Factory Playground](https://tokenfactory.nebius.com/playground?models=zai-org/GLM-5.2)

## TL;DR

GLM-5.2 is Z.ai's latest flagship model for long-horizon tasks — a substantial leap over GLM-5.1, delivering solid 1M-token context, advanced coding with flexible effort, and an improved MoE architecture with IndexShare sparse attention.

- **Provider:** Z.ai (Zhipu AI)
- **Architecture:** Mixture-of-Experts (MoE) — 753B parameters with IndexShare sparse attention
- **Context window:** 1M tokens
- **Strengths:** Long-horizon reasoning, agentic engineering, coding, tool calling, multilingual (English + Chinese)
- **License:** MIT

### Key highlights

- Successor to GLM-5.1 — substantial leap in long-horizon task capability with a solid 1M-token context window
- Advanced coding with multiple thinking effort levels to balance performance vs. latency
- IndexShare + improved MTP architecture: 2.9× per-token FLOPs reduction at 1M context, up to 20% longer speculative-decoding acceptance
- Built on Z.ai's "Slime" RL infrastructure with native function calling and agentic workflow support

---

## Performance and Benchmarks

Selected scores vs. GLM-5.1 — full table on the [GLM-5.2 HuggingFace page](https://huggingface.co/zai-org/GLM-5.2):

| Category | Benchmark | GLM-5.2 | GLM-5.1 |
|---|---|---:|---:|
| Reasoning | HLE | 40.5 | 31.0 |
| Reasoning | AIME 2026 | 99.2 | 95.3 |
| Reasoning | GPQA-Diamond | 91.2 | 86.2 |
| Coding | SWE-bench Pro | 62.1 | 58.4 |
| Coding | DeepSWE | 46.2 | 18.0 |
| Coding | Terminal Bench 2.1 (Terminus-2) | 81.0 | 63.5 |
| Coding | FrontierSWE (Dominance) | 74.4 | 30.5 |
| Agentic | MCP-Atlas (Public Set) | 76.8 | 71.8 |
| Agentic | Tool-Decathlon | 48.2 | 40.7 |

---

## References

- [GLM-5.2 on HuggingFace](https://huggingface.co/zai-org/GLM-5.2)
- [GLM-5.2 Blog — Built for Long-Horizon Tasks](https://z.ai/blog/glm-5.2)
- [GLM-5 Technical Report (arXiv:2602.15763)](https://arxiv.org/abs/2602.15763)
- [IndexCache paper (arXiv:2603.12201)](https://arxiv.org/abs/2603.12201)
- [GitHub: zai-org/GLM-5](https://github.com/zai-org/GLM-5)
- [GLM-5.1 guide](glm-5.1.md) — predecessor
- [GLM-5 guide](archived/glm-5.md) — earlier generation
- [GLM-4.5 guide](archived/glm-4.5.md) — earlier generation with detailed benchmarks

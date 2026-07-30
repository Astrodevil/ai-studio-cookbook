# Comparing Costs of an Agent across Models

How much does an agentic task cost?  This folder has examples that compare 2 models for the same task.

## Nemotron vs Kimi K3

file: [agent_1_nemotron_vs_kimi_k3.py](agent_1_nemotron_vs_kimi_k3.py)

Run it:

```bash
uv run python agent_1_nemotron_vs_kimi_k3.py
```


Output may look like:

```text
=== Running deep research with nvidia/Nemotron-3-Ultra-550b-a55b ===
Wrote report (22021 chars) to output_nvidia_Nemotron-3-Ultra-550b-a55b.md

--- nvidia/Nemotron-3-Ultra-550b-a55b run summary ---
Tool calls:    2
Input tokens:  21,483
Output tokens: 1,072
Total tokens:  22,555
Elapsed time:  40.550s
Est. cost:     $0.024699 (@ In $1.0/1M, Out $3.0/1M)

=== Running deep research with moonshotai/Kimi-K3 ===
Wrote report (8957 chars) to output_moonshotai_Kimi-K3.md

--- moonshotai/Kimi-K3 run summary ---
Tool calls:    10
Input tokens:  48,922
Output tokens: 6,058
Total tokens:  54,980
Elapsed time:  256.295s
Est. cost:     $0.237636 (@ In $3.0/1M, Out $15.0/1M)

=== Side-by-side comparison ===
Metric           nvidia/Nemotron-3-Ultra-550b-a55b                 moonshotai/Kimi-K3
-------------------------------------------------------------------------------------
Tool calls                                       2                                 10
Input tokens                                21,483                             48,922
Output tokens                                1,072                              6,058
Total tokens                                22,555                             54,980
Elapsed (s)                                 40.550                            256.295
Est. cost                                $0.024699                          $0.237636
-------------------------------------------------------------------------------------

nvidia/Nemotron-3-Ultra-550b-a55b is cheaper by $0.212937 (89.6%) vs moonshotai/Kimi-K3.
```

## Nemotron vs GPT-5.5

file: [agent_2_nemotron_vs_gpt.py](agent_2_nemotron_vs_gpt.py)

Run it:

```bash
uv run python agent_2_nemotron_vs_gpt.py
```

Output will be written to `output_nvidia_Nemotron-3-Ultra-550b-a55b.md` and `output_gpt-5.5.md`, and a side-by-side cost summary will be printed to the console.
# Daily AI Research Digest — 2026-05-09

```audio
src: ./assets/narration.mp3
title: Listen
```

## Alignment training moves from imitation to principles
- Anthropic’s “Teaching Claude why” argues that alignment improves when models are trained on the reasons behind aligned behavior, not just on aligned outputs, because principle-level supervision appears to generalize better than narrow demonstration-based imitation [1](./blog-digest/anthropic-alignment/content.md).
- Across the reported interventions, near-distribution honeypot training only modestly reduced agentic misalignment, while rewritten responses that included ethical deliberation cut it far more sharply, and an out-of-distribution “difficult advice” dataset matched that improvement with far fewer tokens [1](./blog-digest/anthropic-research/content.md).
- Constitution documents, aligned fictional stories, and tool-augmented harmlessness environments also improved agentic misalignment metrics, suggesting that broader environment design and richer value-level context can matter as much as the labels themselves [1](./blog-digest/anthropic-alignment/content.md).
- A recurring warning is that optimizing directly on the evaluation distribution can make the metric look better without improving out-of-distribution robustness, so low score on a synthetic honeypot is not proof of general alignment [1](./blog-digest/anthropic-research/content.md).

## Small-model efficiency through structure and constraints
- AllenAI’s EMO pretrains a mixture-of-experts model end to end so modular structure emerges from the data, using document boundaries as weak supervision to restrict which experts can activate together [1](./blog-digest/ai2-research/content.md).
- The reported model is 1B active and 14B total, with 8 active experts out of 128 total experts, and AllenAI says it preserves standard MoE performance while activating only a fraction of the experts [1](./blog-digest/ai2-research/content.md).
- NVIDIA reports that grammar-constrained decoding can materially improve Bash generation in small language models, raising average pass rate from 62.5% to 75.2% across 13 models and 299 tasks [1](./blog-digest/nvidia-generative-ai-blog/content.md).
- The strongest uplift was on Qwen3-0.6B, which rose from 16.7% to 59.2%, but the same approach helped less on more complex shell-construction tasks where the grammar was either too restrictive or too permissive for loops and chaining [1](./blog-digest/nvidia-generative-ai-blog/content.md).

## Agentic systems need better tool, state, and streaming plumbing
- NVIDIA’s Dynamo work shows that multi-turn agentic inference needs the full assistant reasoning-and-tool sequence preserved across turns, with parser support and streaming behavior tuned so tool calls and reasoning blocks are reconstructed in the right order [1](./blog-digest/nvidia-generative-ai-blog/content.md).
- A concrete caching example shows how unstable session headers can dominate latency: on a 52K-token prompt, a stable prefix hit 168 ms TTFT, while a varying header pushed TTFT to 912 ms and stripping it restored roughly the original latency [1](./blog-digest/nvidia-generative-ai-blog/content.md).
- The same post reports a correctness fix where reasoning parsing ownership was made explicit and backend structured reasoning was trusted when available, preventing tool-call and reasoning segments from being reordered or dropped across turns [1](./blog-digest/nvidia-generative-ai-blog/content.md).
- The arXiv digest points to a broader trend in multi-agent systems: authorization propagation should be treated as workflow infrastructure, because transitive delegation, aggregation inference, and temporal validity are not fully handled by standard RBAC-style access control [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).

## Retrieval and QA are becoming more agentic
- FinAgent-RAG combines a contrastive financial retriever, a program-of-thought module that emits executable Python for arithmetic, and a strategy router that allocates compute by question complexity, with reported gains on FinQA, ConvFinQA, and TAT-QA plus a 41.3% API cost reduction on FinQA [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- AgenticRAG shifts enterprise search from single-shot retrieval to iterative search, open, and summarize loops, and the abstract credits that change with the biggest ablation gain while reporting 49.6% recall@1 on BRIGHT and 92% answer correctness on FinanceBench [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- TGS-RAG combines graph-to-text verification with text-to-graph completion to bridge the “Information Island” between unstructured text and structured graphs, using global voting over visited nodes and memory-based orphan-entity bridging [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- SPARK uses a unified knowledge graph to drive self-play question generation and reward computation for scientific QA, with a single small vision-language model alternating between proposer and solver roles and outperforming flat-corpus self-play baselines as hop count increases [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).

## State compression and compute allocation at test time
- Constant-context skill learning moves recurring procedures into task-family modules so the model only conditions on the current observation and a compact state block, while a deterministic tracker renders progress into state and provides aligned subgoal rewards for training [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- The reported results are strong for an agentic setup: 89.6% unseen success on ALFWorld, 76.8% on WebShop, 66.4% unseen success on SciWorld, and a 2–7× reduction in prompt tokens per turn versus controlled ReAct baselines [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- BitCal-TTS tackles the mismatch between quantized inference and adaptive test-time compute by using uncertainty proxies, reasoning-trace stability, bit-conditioned confidence rescaling, and a bit-aware confirmation horizon for 4-bit reasoning models [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- On small GSM8K shards with Qwen2.5 Instruct models, the method produced modest accuracy gains and fewer premature stops at 7B and 14B scales, though the authors explicitly note limited statistical power [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).

## Safety policy, governance, and authorization become explicit research objects
- Annotator Policy Models learn annotators’ internal safety policies from labeling behavior alone, which lets researchers compare annotator reasoning without adding extra annotation work and helps separate operational failure from genuine policy disagreement [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- Partial Evidence Bench focuses on a failure mode where an agent is access-controlled yet still answers as if it had complete evidence; the benchmark spans due diligence, compliance audit, and incident response tasks and finds that silent filtering is unsafe while explicit fail-and-report behavior is safer [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- The geopolitics paper studies regional LLM bias causally with a graphical model and Pearl’s do-operator, comparing models from the US, Europe, the UAE, China, and India on ToxiGen and BOLD and arguing that observational fairness metrics can overstate bias because they ignore context toxicity [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).

## Coverage notes
- This digest synthesizes the latest item set surfaced by the source-agent outputs for 2026-05-09, grouped by theme rather than by source [1](./blog-digest/anthropic-alignment/content.md).
# HuggingFace Featured Papers Digest — 2026-04-27

## Reasoning, long-context QA, and memory

### Contexts are Never Long Enough: Structured Reasoning for Scalable Question Answering over Long Document Sets
https://arxiv.org/abs/2604.22294
- SLIDERS shifts long-document QA from concatenated text to structured reasoning over a relational database, using SQL on persistent extracted state rather than repeated chunk aggregation [5](./citations/5.md).
- It adds a reconciliation stage that uses provenance, extraction rationales, and metadata to detect and repair duplicated, inconsistent, and incomplete records [5](./citations/5.md).
- Reported gains are strong: it outperforms all baselines on three existing long-context benchmarks, exceeding GPT-4.1 by 6.6 points on average, and beats the next best baseline by about 19 and 32 points on two new 3.9M- and 36M-token benchmarks [5](./citations/5.md).

### Learning Evidence Highlighting for Frozen LLMs
https://arxiv.org/abs/2604.22565
- HiLight separates evidence selection from reasoning by training a lightweight Emphasis Actor to place minimal highlight tags around pivotal spans while keeping the input otherwise unchanged [13](./citations/13.md).
- The Actor is optimized with reinforcement learning from the solver’s task reward only, so it needs no evidence labels and no solver modification [13](./citations/13.md).
- The method improves sequential recommendation and long-context QA versus prompt-based and automated prompt-optimization baselines, and the learned highlighting policy transfers zero-shot to unseen solver families, including an API-based solver [13](./citations/13.md).

### Sessa: Selective State Space Attention
https://arxiv.org/abs/2604.18580
- Sessa places attention inside a recurrent feedback path, creating multiple attention-based routes for past tokens to affect future states [11](./citations/11.md).
- Under the paper’s assumptions, it has power-law memory tails slower than Transformer and Mamba-style baselines, and is the only model class considered that realizes flexible selective retrieval with non-decaying influence profiles [11](./citations/11.md).
- In matched experiments, Sessa reports the strongest long-context benchmark performance while remaining competitive on short-context language modeling [11](./citations/11.md).

### Memanto: Typed Semantic Memory with Information-Theoretic Retrieval for Long-Horizon Agents
https://arxiv.org/abs/2604.22085
- Memanto proposes a universal agent memory layer built from a typed semantic schema with 13 predefined memory categories, automated conflict resolution, and temporal versioning [10](./citations/10.md).
- It uses Moorcheh’s information-theoretic search engine to provide deterministic retrieval with sub-90 ms latency and no ingestion delay [10](./citations/10.md).
- On LongMemEval and LoCoMo, it reports state-of-the-art accuracy of 89.8% and 87.1%, respectively, while requiring a single retrieval query and no ingestion cost [10](./citations/10.md).

## Agents and evaluation infrastructure

### Agentic World Modeling: Foundations, Capabilities, Laws, and Beyond
https://arxiv.org/abs/2604.22748
- The paper frames world models with a “levels × laws” taxonomy: three capability levels (predictor, simulator, evolver) crossed with four law regimes (physical, digital, social, scientific) [1](./citations/1.md).
- It is explicitly a synthesis paper, covering over 400 works and more than 100 representative systems across model-based RL, video generation, web and GUI agents, multi-agent social simulation, and AI-driven scientific discovery [1](./citations/1.md).
- The abstract says it also proposes decision-centric evaluation principles, a minimal reproducible evaluation package, and architectural guidance, but does not report a single benchmark result because the contribution is conceptual and survey-like [1](./citations/1.md).

### AgentSearchBench: A Benchmark for AI Agent Search in the Wild
https://arxiv.org/abs/2604.22436
- AgentSearchBench is built from nearly 10,000 real-world agents across multiple providers and frames agent search as retrieval and reranking over executable task queries and high-level descriptions [6](./citations/6.md).
- Evaluation uses execution-grounded performance signals, and the paper reports a consistent gap between semantic similarity and actual agent performance [6](./citations/6.md).
- Lightweight behavioral signals, including execution-aware probing, substantially improve ranking quality, suggesting that agent discovery should incorporate execution rather than text-only signals [6](./citations/6.md).

### dWorldEval: Scalable Robotic Policy Evaluation via Discrete Diffusion World Model
https://arxiv.org/abs/2604.22152
- dWorldEval is a discrete diffusion world model used as a scalable proxy for evaluating robotics policies across many environments and tasks [8](./citations/8.md).
- It maps vision, language, and robotic actions into a unified token space, uses sparse keyframe memory for spatiotemporal consistency, and adds a progress token to indicate task completion [8](./citations/8.md).
- The paper says it outperforms WorldEval, Ctrl-World, and WorldGym on LIBERO, RoboTwin, and multiple real-robot tasks, but the abstract does not provide exact numeric deltas [8](./citations/8.md).

## Multimodal generation and video understanding

### Building a Precise Video Language with Human-AI Oversight
https://arxiv.org/abs/2604.21718
- The paper introduces structured video-captioning specifications spanning subjects, scenes, motion, spatial dynamics, and camera dynamics, grounded in hundreds of visual primitives developed with professional video creators [9](./citations/9.md).
- CHAI uses critique-based human-AI oversight: experts critique and revise model-generated pre-captions into post-captions, improving annotation accuracy and efficiency [9](./citations/9.md).
- The resulting supervision improves Qwen3-VL for caption generation, reward modeling, and critique generation, and the abstract claims the model can outperform closed-source Gemini-3.1-Pro with modest expert supervision [9](./citations/9.md).
- The framework is also applied to re-caption films, commercials, and games, and to fine-tune Wan for prompt-following video generation with prompts up to 400 words and finer cinematographic control [9](./citations/9.md).

### FlowAnchor: Stabilizing the Editing Signal for Inversion-Free Video Editing
https://arxiv.org/abs/2604.22586
- FlowAnchor is a training-free, inversion-free, flow-based video editing framework that anchors both where and how strongly to edit [4](./citations/4.md).
- Its two core components are Spatial-aware Attention Refinement and Adaptive Magnitude Modulation, which target spatial mislocalization and strength attenuation in longer videos [4](./citations/4.md).
- The abstract reports more faithful, temporally coherent, and computationally efficient editing on multi-object and fast-motion scenarios, but gives no specific numeric benchmark values [4](./citations/4.md).

### Video Analysis and Generation via a Semantic Progress Function
https://arxiv.org/abs/2604.22554
- This paper defines a Semantic Progress Function: a one-dimensional curve over frame embeddings that measures cumulative semantic shift across a video sequence [7](./citations/7.md).
- Deviations from linearity are used to diagnose uneven pacing, and the method includes a semantic linearization/retiming procedure to make change unfold at a constant rate [7](./citations/7.md).
- The abstract positions the method as model-agnostic for analyzing temporal irregularities, comparing generators, and steering sequences toward arbitrary pacing [7](./citations/7.md).

## Safety and domain-specific retrieval

### LLM Safety From Within: Detecting Harmful Content with Internal Representations
https://arxiv.org/abs/2604.18519
- SIREN builds a harmfulness detector from internal LLM features instead of only terminal-layer representations, using linear probing to identify safety neurons and an adaptive layer-weighted combination [3](./citations/3.md).
- It does not modify the underlying model and is described as lightweight, with 250x fewer trainable parameters than state-of-the-art open-source guard models [3](./citations/3.md).
- The abstract claims better benchmark performance, better generalization to unseen benchmarks, real-time streaming detection, and improved inference efficiency versus generative guard models [3](./citations/3.md).

### AgriIR: A Scalable Framework for Domain-Specific Knowledge Retrieval
https://arxiv.org/abs/2604.16353
- AgriIR is a modular RAG framework that decomposes query refinement, sub-query planning, retrieval, synthesis, and evaluation into declarative stages [12](./citations/12.md).
- The reference implementation targets Indian agricultural information access with 1B-parameter language models, adaptive retrievers, and domain-aware agent catalogues [12](./citations/12.md).
- The abstract emphasizes deterministic citation, telemetry, and auditable deployment, but does not report benchmark metrics; it is mainly a systems/design contribution [12](./citations/12.md).

# arXiv cs.CL digest — 2026-05-15

## Retrieval-augmented generation: evidence conflict, internal flow, and reranking for memory

### When Evidence Conflicts: Uncertainty and Order Effects in Retrieval-Augmented Biomedical Question Answering
- Biomedical retrieval-augmented LLMs are evaluated under incomplete, misleading, or internally contradictory evidence, rather than only under helpful context [1](./citations/1.md).
- The study uses HealthContradict and tests six open-weight LLMs under five controlled evidence conditions: no retrieved context, correct-only, incorrect-only, and two mixed conditions with correct and contradictory documents in opposite orders [1](./citations/1.md).
- Reversing the order of the same two documents changes predictions: accuracy drops for every model, and 11.4%--25.2% of predictions flip [1](./citations/1.md).
- A conflict-aware abstention score that combines model confidence with a detector of evidence conflict improves selective accuracy over confidence-only in the two hardest conditions, with mean gains of 7.2--33.4 points in incorrect-only and 3.6--14.4 points in incorrect-first conflicting conditions across 75%, 50%, and 25% coverage [1](./citations/1.md).
- The abstract frames this as both an uncertainty and robustness problem and argues for evaluation and abstention methods that explicitly account for disagreement in evidence [1](./citations/1.md).

### Why Retrieval-Augmented Generation Fails: A Graph Perspective
- This paper studies why RAG can still answer incorrectly even when external information is available [2](./citations/2.md).
- The authors use circuit tracing to build attribution graphs that model information flow through transformer layers during decoding, including retrieved context, intermediate activations, and generated tokens [2](./citations/2.md).
- Across multiple QA benchmarks, correct predictions show deeper reasoning paths, more distributed evidence flow, and more structured local connectivity, while failed predictions are shallower, fragmented, and overly concentrated [2](./citations/2.md).
- The graph features are then used for error detection, and the same attribution graphs support interventions that reinforce question-constrained evidence grounding so answer generation remains guided by the question [2](./citations/2.md).

### MemReranker: Reasoning-Aware Reranking for Agent Memory Retrieval
- This work targets agent memory systems where retrieve-then-rerank pipelines often return semantically relevant memories that still miss the key information needed to answer a question [3](./citations/3.md).
- The abstract identifies three failure modes for generic rerankers in memory settings: miscalibrated relevance scores, degradation on temporal and causal reasoning, and weak use of dialogue context for disambiguation [3](./citations/3.md).
- MemReranker is a 0.6B/4B reranking family built on Qwen3-Reranker through multi-stage LLM knowledge distillation, using multi-teacher pairwise comparisons, BCE pointwise distillation, and InfoNCE contrastive learning [3](./citations/3.md).
- Training mixes general corpora with memory-specific multi-turn dialogue data covering temporal constraints, causal reasoning, and coreference resolution [3](./citations/3.md).
- On the memory retrieval benchmark, MemReranker-0.6B beats BGE-Reranker and matches open-source 4B/8B models and GPT-4o-mini on key metrics; MemReranker-4B reaches 0.737 MAP, is described as on par with Gemini-3-Flash on several metrics, and runs at 10--20% of the inference latency of large models [3](./citations/3.md).
- On finance and healthcare vertical-domain benchmarks, the models preserve generalization comparable to mainstream large-parameter rerankers [3](./citations/3.md).

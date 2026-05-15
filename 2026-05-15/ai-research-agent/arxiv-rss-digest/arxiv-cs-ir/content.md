# arXiv cs.IR digest — 2026-05-15

## Retrieval, provenance, and agentic RAG

- [Why Neighborhoods Matter: Traversal Context and Provenance in Agentic GraphRAG](https://arxiv.org/abs/2605.15109) [1](./citations/1.md)
  - The paper frames citation faithfulness in Agentic GraphRAG as a trajectory-level problem: final citations should support the answer and also account for graph traversal, graph structure, and visited-but-uncited entities that may influence the output.[1](./citations/1.md)
  - In controlled ablation experiments, the authors compare isolating, removing, and masking cited and uncited graph entities.[1](./citations/1.md)
  - The abstract claims cited evidence is often necessary because removing it substantially changes answers and reduces accuracy.[1](./citations/1.md)
  - It also says citations are not sufficient, since accurate answers can depend on uncited traversal context and surrounding graph structure.[1](./citations/1.md)
  - Likely relevance: citation evaluation in Agentic GraphRAG should move beyond source support toward provenance over the broader retrieval trajectory.[1](./citations/1.md)

# arXiv cs.IR RSS Digest — 2026-05-08

## Disaster information systems and retrieval-augmented access

- **DisastRAG: A Multi-Source Disaster Information Integration and Access System Based on Retrieval-Augmented Large Language Models** — A disaster-aware information integration and access system that combines LLMs with retrieval-augmented access over structured disaster records, unstructured institutional documents, and external web sources [1](./citations/1.md).
- The system uses a multi-path architecture with document retrieval over a curated hazard corpus, structured access over relational disaster records, and web fallback for out-of-corpus requests; it also includes query understanding, strategy routing, response generation, and contextual memory [1](./citations/1.md).
- Reported evaluation across four open-source LLMs and multiple retrieval configurations shows retrieval augmentation consistently improves performance over no-retrieval baselines, with multiple-choice gains of 12–23 percentage points and open-ended keypoint coverage gains up to 10.5 percentage points [1](./citations/1.md).
- The abstract’s comparison suggests larger candidate pools help weaker models more than stronger models, hybrid retrieval is strongest for open-ended coverage, and vector retrieval plus shallower reranking more often favor closed-form factual selection [1](./citations/1.md).
- Case studies indicate structured access and web fallback extend the framework beyond document-only RAG, but the abstract does not report dataset names beyond the curated hazard corpus or give implementation details for the evaluation tasks [1](./citations/1.md).

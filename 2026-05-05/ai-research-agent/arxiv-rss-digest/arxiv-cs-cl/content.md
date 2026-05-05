# arXiv cs.CL digest — 2026-05-05

## Retrieval-augmented generation: robustness and interpretability

### Beyond semantic relevance: retrieval aligned to decision safety
- The paper argues that standard RAG treats semantic relevance as a proxy for utility, but that proxy can fail when queries contain false premises or confirmation bias, because relevance can surface sycophantic evidence that reinforces hallucinations [1](./citations/1.md).
- It proposes CoRM-RAG, a counterfactual-risk-minimization framework that shifts retrieval toward decision safety rather than similarity [1](./citations/1.md).
- Training uses a Cognitive Perturbation Protocol to simulate user bias, then distills that signal into a lightweight Evidence Critic that scores whether a document has enough evidential strength to correct the model under adversarial perturbations [1](./citations/1.md).
- The abstract claims strong gains on decision-making benchmarks versus dense retrievers and LLM-based rerankers in adversarial settings, plus risk-aware abstention via robustness scoring [1](./citations/1.md).
- Source link: https://arxiv.org/abs/2605.01302

### Chain of Evidence: pixel-level attribution for iterative RAG
- The paper targets iRAG systems for multi-hop questions, arguing that text-first pipelines create coarse-grained attribution and lose visual/layout cues when documents such as slides and PDFs are parsed into text [2](./citations/2.md).
- It presents Chain of Evidence (CoE), a retriever-agnostic visual attribution framework that uses vision-language models on screenshots of retrieved candidates rather than on parsed text [2](./citations/2.md).
- The output includes precise bounding boxes so the reasoning chain can be visualized within the retrieved candidate set [2](./citations/2.md).
- The abstract says the method was evaluated on Wiki-CoE, derived from 2WikiMultiHopQA, and on SlideVQA, a slide dataset with complex diagrams and free-form layouts; fine-tuned Qwen3-VL-8B-Instruct outperformed text-based baselines where layout understanding mattered [2](./citations/2.md).
- Source link: https://arxiv.org/abs/2605.01284

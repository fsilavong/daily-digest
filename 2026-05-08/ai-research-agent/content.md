# AI Research Digest — 2026-05-08

```audio
src: ./assets/narration.mp3
title: Listen
```

## Interpretability, alignment, and safety instrumentation
- Anthropic’s Natural Language Autoencoders turn model activations into readable explanations by training an activation verbalizer and reconstructor pair against reconstruction quality, and the post says this surfaced evaluation awareness and hidden motivation signals that were hard to obtain from direct model text alone [Anthropic Research Digest](./blog-digest/anthropic-research/content.md).
- Anthropic reports the technique can hallucinate, so it is positioned as thematic interpretability that needs corroborating evidence rather than literal decoding [Anthropic Research Digest](./blog-digest/anthropic-research/content.md).
- Anthropic also donated Petri to Meridian Labs as version 3.0, keeping it as an open-source alignment toolbox for auditor-target-judge simulations of deception, sycophancy, harmful cooperation, and sabotage-like behavior [Anthropic Research Digest](./blog-digest/anthropic-research/content.md).
- The Petri update emphasizes more modular components, more realistic scenario scaffolding, and deeper behavior coverage, which matters as reusable evaluation infrastructure rather than a benchmark result [Anthropic Research Digest](./blog-digest/anthropic-research/content.md).
- A separate Anthropic Institute agenda frames AI-impact research around economic diffusion, threats and resilience, AI systems in the wild, and AI-driven R&D, with concrete plans to expand the Economic Index and build early-warning signals [Anthropic Research Digest](./blog-digest/anthropic-research/content.md).
- On the safety side, one arXiv paper proposes SQSD, a sample-level risk score for fine-tuning data by measuring how induced parameter updates project toward danger-aligned directions, and it claims transfer across models, scales, and PEFT methods [arXiv cs.AI Digest](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- Another arXiv survey organizes jailbreak attacks and defenses into a taxonomy, introduces the Security Cube evaluation framework, and argues that attack success rate alone is too narrow for LLM security assessment [arXiv cs.AI Digest](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- Pen-Strategist targets pentesting strategy formation with a reasoning model plus classifier, and reports large gains in strategy derivation, subtask completion, and step prediction stability [arXiv cs.AI Digest](./arxiv-rss-digest/arxiv-cs-ai/content.md).

## Memory, retrieval, and long-horizon orchestration
- LongSeeker proposes Context-ReAct, an elastic context orchestration loop with Skip, Compress, Rollback, Snippet, and Delete to reshape working context as evidence changes, and it reports higher BrowseComp and BrowseComp-ZH performance than named baselines [arXiv cs.AI Digest](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- A retrieval-centered memory architecture titled True Memory argues that ingestion-time extraction is the wrong primitive, instead storing verbatim events in a six-layer SQLite-only stack and reporting strong recall results on LoCoMo, LongMemEval, and BEAM-1M [arXiv cs.AI Digest](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- Uno-Orchestra learns whether to decompose a task and which model or primitive to route to each subtask using RL trajectories from real worker interactions, and the paper claims higher macro pass@1 at much lower per-query cost on a 13-benchmark suite [arXiv cs.AI Digest](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- MiA-Signature compresses the global activation pattern induced by a query into a long-context representation, and the Hugging Face digest says it improves long-context understanding when used in both RAG and agentic systems [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).
- SkillOS separates a frozen executor from an RL-trained skill curator that updates an external SkillRepo over time, with reported gains on multi-turn agentic and single-turn reasoning tasks [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).

## Retrieval-augmented systems and applied access
- DisastRAG combines LLMs with retrieval over structured disaster records, unstructured institutional documents, and external web sources, using query understanding and strategy routing to answer disaster-information requests [arXiv cs.IR RSS Digest](./arxiv-rss-digest/arxiv-cs-ir/content.md).
- The paper reports retrieval augmentation consistently beats no-retrieval baselines, with large multiple-choice gains and open-ended keypoint coverage improvements, and notes that hybrid retrieval is strongest for open-ended coverage [arXiv cs.IR RSS Digest](./arxiv-rss-digest/arxiv-cs-ir/content.md).
- Anthropic’s institute agenda and IBM’s physical-sciences hub both point to growing application-driven research pipelines, but IBM’s latest readable item is only a topic hub, not a full post, so it mainly serves as a navigation surface into work on quantum computing, fusion, materials, and Earth/space AI [IBM Research Blog Digest](./blog-digest/ibm-research-blog/content.md).

## Inference efficiency, compression, and deployment
- NVIDIA’s ModelOpt post shows post-training quantization of CLIP to FP8, with representative calibration and fake quantization before deployment, and reports comparable quality to FP16 on CIFAR-100, ImageNet-1k, and MS-COCO Captions [NVIDIA Generative AI Blog Digest](./blog-digest/nvidia-generative-ai-blog/content.md).
- The post calls out a practical implementation detail: CLIP attention needs explicit replacement because the default module walker misses the functional SDPA path, so quantization coverage must be wired in deliberately [NVIDIA Generative AI Blog Digest](./blog-digest/nvidia-generative-ai-blog/content.md).
- PARSE, a cs.AI paper, pushes speculative generation beyond token-level checks with a parallel prefix verifier for semantic prefixes, claiming 1.25x to 4.5x throughput gains with negligible accuracy loss [arXiv cs.AI Digest](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- CDM and Cola DLM point in a broader direction of continuous or latent-space modeling: CDM moves few-step diffusion distillation to continuous-time matching, while Cola DLM models language via a hierarchical continuous latent prior rather than token-level autoregression [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).

## Diffusion, generation, and embodied control
- MARBLE reframes multi-reward diffusion RL as per-reward gradient harmonization with quadratic programming, and the paper says it improves all reward dimensions together while staying near baseline training cost [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).
- ReflectDrive-2 represents driving plans as discrete trajectory tokens and trains with decision-draft-reflect RL, reaching high NAVSIM scores at low latency in the reported setup [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).
- SwiftI2V uses a two-stage, segment-wise image-to-video pipeline to reach 2K generation with much lower GPU time than end-to-end baselines, and the digest says it remains practical on a single H800 or RTX 4090 [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).
- When to Trust Imagination proposes FFDC, a lightweight verifier for world action models that decides when to keep executing versus replan based on agreement between predicted and observed futures, cutting forward passes and execution time while improving success [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).

## Reasoning, RL, and training dynamics
- LoPE attacks the zero-advantage problem in GRPO-style RL by prepending stochastic Lorem Ipsum-like tokens before resampling, and it reportedly outperforms plain resampling across 1.7B to 7B models [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).
- A^2TGPO keeps Information Gain as an intrinsic process signal but changes normalization, accumulation, and clipping at the turn level to better assign credit in agentic RL [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).
- ScaleLogic studies long-horizon reasoning by independently varying proof-planning depth and logical expressiveness, and it reports a strong power-law relation between RL compute and reasoning depth that strengthens as expressiveness increases [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).
- Auto Research with Specialist Agents describes a closed-loop research workflow where specialist agents propose and edit code, evaluator-owned outcomes guide the loop, and failures become later program-level edits; the paper reports gains across thousands of trials on multiple tasks [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).

## Representation learning and structured state
- GEM combines a graph neural network, a fine-tuned T5-Small encoder-decoder, and ReAct agents under an intelligent router for dialogue state tracking, and reports 65.19% Joint Goal Accuracy on MultiWOZ 2.2 [arXiv cs.AI Digest](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- TabBench and TabEmbed introduce a benchmark and embedding model for general tabular understanding, unifying classification and retrieval in a shared contrastive space and claiming a new baseline for tabular representations [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).
- UniPool replaces per-layer MoE ownership with a globally shared expert pool, adds routing stabilization losses, and reports better validation loss and perplexity than matched baselines while using less expert budget [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).
- The Granularity Axis identifies a latent direction tied to micro-versus-macro social-role behavior in language models, and the digest says it transfers across models and can be manipulated by activation steering [HuggingFace Featured Papers Digest](./blog-digest/huggingface-papers/content.md).

## Source coverage notes
- IBM’s feed returned only a topic hub in this run, so the digest includes that navigational item rather than a full research post [IBM Research Blog Digest](./blog-digest/ibm-research-blog/content.md).
- NVIDIA’s feed likewise returned one readable post, so the digest only covers that item [NVIDIA Generative AI Blog Digest](./blog-digest/nvidia-generative-ai-blog/content.md).

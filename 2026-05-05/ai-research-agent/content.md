# Daily AI Research Digest — 2026-05-05

```audio
src: ./assets/narration.mp3
title: Listen
```

## Agentic systems and tool use
- TADI frames drilling operations as an evidence-grounded agentic workflow, combining daily drilling reports, WITSML objects, production records, formation tops, and perforations in a dual-store setup with DuckDB for structured querying and ChromaDB for semantic search [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- Its orchestration layer uses twelve domain-specialized tools and iterative function calling to gather evidence, while the paper also highlights zero-error XML parsing, multiple well-name conventions, 95 automated tests, and an Evidence Grounding Score for grounding compliance [1](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- AgentReputation argues that agentic marketplaces need decentralized reputation systems because current reputation signals are easy to game, do not transfer cleanly across contexts, and vary in verification rigor [2](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- The proposed framework separates task execution, reputation services, and tamper-proof persistence, then adds context-conditioned reputation cards, explicit verification regimes, and a policy engine for access control and resource allocation [2](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- Nvidia’s cuOpt agent-skill workflow shows how LLM agents can translate supply-chain questions into optimization models, spawn sub-agents for validation and formulation, and call GPU-accelerated solvers for production planning, inventory, and routing [3](./blog-digest/nvidia-generative-ai-blog/content.md).
- The same workflow emphasizes structured payloads with decision variables, objectives, and constraints, and says the resulting plans include optimized actions plus summary metrics such as total cost, utilization, and constraint slack [3](./blog-digest/nvidia-generative-ai-blog/content.md).
- Ctx2Skill extends the agent theme from external tools to self-improvement, using a multi-agent self-play loop to discover and refine context-specific natural-language skills without human supervision [4](./blog-digest/huggingface-papers/content.md).
- The loop uses Challenger, Reasoner, Judge, Proposer, and Generator roles, plus Cross-time Replay to reduce collapse and over-specialization, and the evaluation reports consistent solving-rate gains on CL-bench tasks [4](./blog-digest/huggingface-papers/content.md).

## Tool-use limits, gating, and when to call tools
- "Are Tools All We Need?" argues that tool use can carry a protocol overhead that cancels out its benefits under semantic noise, especially when retrieval or other tools surface distractors that reinforce the wrong answer [5](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- The paper decomposes performance into prompt-formatting cost, tool-calling protocol overhead, and the gain from actually executing tools, then proposes G-STEP as a partial mitigation [5](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- "To Call or Not to Call" tackles the separate decision of whether an LLM should use a tool at all, and evaluates tool-use decisions by necessity, utility, and affordability [6](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- It finds that a model’s perceived need and utility often diverge from the true values, and that lightweight hidden-state estimators can improve tool-calling control and downstream task quality [6](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- AgentFloor asks how far small open-weight models can climb the agent stack and finds that they can handle much of the short-horizon structured tool use in real pipelines, while long-horizon planning and persistent constraint tracking remain the hardest gaps [7](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- The benchmark spans six capability tiers, 16 open-weight models from 0.27B to 32B parameters, and GPT-5, and reports that the strongest open-weight model matches GPT-5 on this benchmark while being cheaper and faster [7](./arxiv-rss-digest/arxiv-cs-ai/content.md).

## Retrieval, grounding, and interpretability
- CoRM-RAG argues that standard retrieval-augmented generation can fail when semantic relevance rewards false premises or confirmation bias, so it shifts retrieval toward decision safety instead of similarity alone [8](./arxiv-rss-digest/arxiv-cs-cl/content.md).
- The method uses a Cognitive Perturbation Protocol to simulate user bias and trains an Evidence Critic that scores whether a document has enough evidential strength to correct the model under adversarial perturbation [8](./arxiv-rss-digest/arxiv-cs-cl/content.md).
- Chain of Evidence moves iterative RAG attribution toward pixels rather than parsed text, using screenshots of retrieved candidates and bounding boxes so the reasoning chain preserves layout cues from slides and PDFs [9](./arxiv-rss-digest/arxiv-cs-cl/content.md).
- The reported evaluation says this visual attribution approach helps on Wiki-CoE and SlideVQA when layout understanding matters, especially with fine-tuned Qwen3-VL-8B-Instruct [9](./arxiv-rss-digest/arxiv-cs-cl/content.md).
- LOCA looks for the smallest set of interpretable intermediate representation changes that causally flip a jailbreak into a refusal, making jailbreak analysis more local and mechanistic [10](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- In the reported comparison, LOCA succeeds with about six interpretable changes on average, while prior methods often fail even after 20 changes, which makes it a practical debugging lens for refusal behavior [10](./arxiv-rss-digest/arxiv-cs-ai/content.md).

## Safety, alignment, and refusal behavior
- Amazon’s Responsible AI summary treats safety, fairness, and robustness as product requirements across warehouse logistics, chatbots, and AWS services rather than as downstream add-ons [11](./blog-digest/amazon-science-blog/content.md).
- The company describes a four-stage RAI pipeline spanning pretraining, post-training, evaluation, and third-party monitoring or frontier-risk assessment, backed by more than 70 tools, more than 500 papers, and tens of thousands of training hours [11](./blog-digest/amazon-science-blog/content.md).
- In pretraining, Amazon mixes public data with RAI-specific corpora and policy-to-exercise conversions, and says that simply filtering harmful content is not enough because models may fail to recognize missing harmful concepts later [11](./blog-digest/amazon-science-blog/content.md).
- The post also highlights modality alignment, RLHF with human rankings and LLM judges, and red-team-style evaluation datasets that probe both unsafe outputs and excessive refusals on benign prompts [11](./blog-digest/amazon-science-blog/content.md).
- ARMOR 2025 extends safety evaluation into military settings by converting doctrinal text into multiple-choice questions grounded in the Law of War, Rules of Engagement, and Joint Ethics Regulation [12](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- The benchmark uses a 12-category taxonomy and 519 prompts, and the summary’s takeaway is that current models still have critical gaps in military safety alignment [12](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- The Code World Model preparedness report says Meta’s CWM does not appear to add frontier-risk beyond the current ecosystem, which is why it is being released as an open-weight model [13](./blog-digest/huggingface-papers/content.md).

## Benchmarking agents in real work
- PhysicianBench moves agent evaluation into live EHR workflows, with 100 physician-reviewed tasks spanning 21 specialties, an average of 27 tool calls per task, and 670 execution-grounded checkpoints [14](./blog-digest/huggingface-papers/content.md).
- The benchmark is demanding enough that the best of 13 proprietary and open agents reaches only 46% pass@1, while open-source models top out at 19% [14](./blog-digest/huggingface-papers/content.md).
- AcademiClaw likewise measures long-horizon agent performance on student-sourced university workflows, with bilingual tasks across 25+ domains and isolated Docker execution plus multi-dimensional rubrics and safety audits [15](./blog-digest/huggingface-papers/content.md).
- The results show a ceiling even for frontier systems, with the best of six models reaching only 55% pass rate and clear behavioral differences beyond aggregate scores [15](./blog-digest/huggingface-papers/content.md).
- TokenArena shifts inference benchmarking from model-level averages to endpoint-level economics, comparing provider, model, quantization, decoding, region, and serving stack as a single endpoint tuple [16](./arxiv-rss-digest/arxiv-cs-ai/content.md).
- It combines throughput, latency, quality, and energy into joules per correct answer, dollars per correct answer, and endpoint fidelity, and shows that the same model can vary materially across endpoints [16](./arxiv-rss-digest/arxiv-cs-ai/content.md).

## Robotics, embodied reasoning, and grounded control
- MolmoAct2 is the day’s most deployment-oriented robotics release: a fully open VLA action-reasoning model with a new VLM backbone, a new action tokenizer, new datasets, and an adaptive-depth reasoning variant [17](./blog-digest/huggingface-papers/content.md).
- The paper reports a 3.3M-sample training corpus, 720 hours of bimanual teleoperation data, and strong benchmark results across simulation and real-world tasks, including gains over Pi-05 and strong embodied-reasoning scores [17](./blog-digest/huggingface-papers/content.md).
- PFlowNet tries to reduce language bias and hallucination in visually grounded reasoning by decoupling perception from reasoning and using multi-dimensional rewards with geometric shaping in variational reinforcement learning [18](./blog-digest/huggingface-papers/content.md).
- The reported result is a performance guarantee and new state of the art on V* Bench and MME-RealWorld-lite, suggesting a more reliable path for visual reasoning systems [18](./blog-digest/huggingface-papers/content.md).

## Multimodal data, generation, and efficiency
- OceanPile builds a public multimodal ocean corpus to solve a data bottleneck in ocean foundation models, bundling sonar, underwater imagery, marine science visuals, scientific text, instruction data, and a benchmark set [19](./blog-digest/huggingface-papers/content.md).
- The corpus uses a hierarchical Ocean Concept Knowledge Graph and a multi-stage quality-control pipeline, and the release claims significant downstream gains from training on the package [19](./blog-digest/huggingface-papers/content.md).
- OGPP introduces orbit-space particle flow matching to handle permutation symmetry in particle-based generative modeling, using index embeddings and geometric probability paths with arc-length-aware terminal velocities [20](./blog-digest/huggingface-papers/content.md).
- The paper reports large improvements on minimal-surface benchmarks and strong ShapeNet results with fewer steps and parameters, plus competitive 3D reconstruction and normal prediction [20](./blog-digest/huggingface-papers/content.md).
- MotionCache speeds autoregressive video generation by updating cache reuse frequency according to motion, so high-motion regions get more denoising while static regions are skipped more aggressively [21](./blog-digest/huggingface-papers/content.md).
- On SkyReels-V2 and MAGI-1, the method reports substantial speedups with only small VBench drops, making it a practical efficiency result rather than just a quality tradeoff [21](./blog-digest/huggingface-papers/content.md).

## Notes on source coverage
- IBM Research blog extraction failed for the unread items, so no source-grounded IBM item summary was available for this digest [22](./blog-digest/ibm-research-blog/content.md).
- The Amazon Science and NVIDIA blog digests each contained a single readable item, so those themes were folded directly into the cross-source synthesis above [11](./blog-digest/amazon-science-blog/content.md) [3](./blog-digest/nvidia-generative-ai-blog/content.md).

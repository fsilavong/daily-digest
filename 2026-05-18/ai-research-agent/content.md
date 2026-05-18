# Daily AI Research Digest — 2026-05-18

```audio
src: ./assets/narration.mp3
title: Listen
```

Today's strongest theme was the shift from generic agent stacks toward narrower mechanisms for execution control, memory quality, and multimodal procedure reuse, alongside a steady flow of benchmarks showing that long-horizon performance still lags far behind promising component-level gains [1](arxiv-rss-digest/arxiv-cs-ai/content.md) [2](blog-digest/huggingface-papers/content.md).

## Agent orchestration, skills, and runtime control

- SDOF treats multi-agent execution as a constrained state machine, combining a specialized intent router with a dispatcher that enforces finite-state stage checks and skill preconditions/postconditions instead of letting free-form routing decide everything [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- In a recruitment workflow on Beisen iTalent, SDOF says its 7B router beat zero-shot GPT-4o on an FSM-constrained adversarial routing benchmark, 80.9% versus 48.9%, across 185 scenarios that generated 1,671 live API calls [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- The same paper reports 86.5% end-to-end task completion and says it blocked all 22 operations in an injection or illegal-HR subset, which makes the main contribution as much about controlled failure as raw completion [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- SkillSmith pushes a different part of the stack, compiling skills offline into boundary-guided runtime interfaces so agents can execute compact, purpose-built interfaces instead of rereading bulky raw skill descriptions at solve time [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- On SkillsBench, SkillSmith reports lower solve-stage token use, fewer thinking iterations, faster solve time, and lower token-proportional cost, while also claiming that artifacts compiled with stronger models can still help weaker runtime models [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- CAX-Agent applies the same reliability-first mindset to engineering automation, wrapping MAPDL with a three-layer harness and a staged recovery ladder from rule patching up to regeneration, context enrichment, and human escalation [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- Its reported best results come from a surprisingly simple "model only" recovery policy on 50 structural benchmarks, although the paper explicitly limits the result to deliberately simple geometries meant to isolate recovery effects [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- Verifiable Agentic Infrastructure is more conceptual than empirical, but it is notable for replacing standing credentials with proof-derived execution authority, using justification proofs, consensus evaluation, ephemeral execution identity, and an append-only evidence chain [1](arxiv-rss-digest/arxiv-cs-ai/content.md).

## Memory, context synthesis, and evolving knowledge for agents

- X-SYNTH argues that enterprise agents need more than retrieval over stored state, and instead builds context from observed human attention patterns and behavioral traces rather than just document access or system logs [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- Its core representation is a Digital Twin Signature plus seven selectable attention filters—Proportional, Inverse, Differential, Recurrent, Comparative, Sequential, and Collective—meant to decide which observed context matters for a task [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- On a sales lead task, X-SYNTH reports true lead rate improving from 9.5% to 61.9% while false lead rate drops from 90.5% to 18.8%, making it one of the day's largest claimed applied gains even if the setup is narrowly scoped [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- SeqMem-Eval is less a new memory module than a warning that final accuracy is a bad proxy for memory quality, because sequentially updated external memory can look strong on end metrics while still showing forgetting or negative transfer [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- H-Mem proposes a hybrid memory design that evolves short-term traces into long-term structure with a temporal-semantic tree while also using a knowledge graph for entity relations, and the paper claims state-of-the-art QA results on three agent-memory benchmarks [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- Solvita extends the memory theme into competitive programming by keeping graph-structured knowledge networks for four specialized agents—Planner, Solver, Oracle, and Hacker—so the system can learn from problem-solving and debugging outcomes without changing base LLM weights [2](blog-digest/huggingface-papers/content.md).
- The reported result is state-of-the-art performance across CodeContests, APPS, AetherCode, and live Codeforces rounds, with nearly 2x gains over single-pass baselines, suggesting that structured external evolution is still a strong alternative to parameter updates for coding agents [2](blog-digest/huggingface-papers/content.md).

## Multimodal agents, GUI grounding, and interactive world models

- MMSkills reframes reusable skills for visual agents as multimodal procedural knowledge, meaning a skill is not just text instructions but also state-recognition cues, progress checks, failure signals, and examples of what intermediate states should look like [2](blog-digest/huggingface-papers/content.md).
- Its skill packages combine textual procedures with runtime state cards and multi-view keyframes, and it uses a trajectory-to-skill generator to distill reusable multimodal skills from public trajectories through grouping, procedure induction, visual grounding, and auditing [2](blog-digest/huggingface-papers/content.md).
- The paper also introduces a branch-loaded multimodal skill agent that inspects selected state cards and keyframes in a temporary branch before distilling guidance back to the main agent, reporting improvements on both frontier and smaller visual-agent models [2](blog-digest/huggingface-papers/content.md).
- PAGER focuses on a harder GUI regime where actions must hit exact points in continuous canvas space rather than broad clickable regions, and its PAGE Bench contributes 4,906 tasks with more than 224,000 process-supervised pixel-level actions [2](blog-digest/huggingface-papers/content.md).
- The striking result is that general multimodal models can exceed 88% action-type accuracy but still stay below 6% task success, while PAGER's topology-aware planning, pixel-grounded action grammar, and precision-aligned RL lift task success by 4.1x over the strongest general baseline [2](blog-digest/huggingface-papers/content.md).
- ReactiveGWM tries to make game world models less player-centric by separating player controls from NPC behavior and grounding higher-level NPC reactions through cross-attention, with zero-shot strategy transfer reported across different off-the-shelf game world models [2](blog-digest/huggingface-papers/content.md).
- WorldAct tackles a related interaction bottleneck for 3D generation by decomposing monolithic worlds into actionable objects with a multimodal agent, then reconstructing object-level meshes plus residual background so scenes become editable and ready for interaction [2](blog-digest/huggingface-papers/content.md).
- DepthVLM adds a lightweight depth head to a vision-language model so it can produce full-resolution metric depth in one pass while preserving multimodal ability, and the paper claims both better geometry prediction and gains on complex 3D spatial reasoning [2](blog-digest/huggingface-papers/content.md).

## Reasoning optimization and reinforcement learning with verifiable rewards

- A recurring pattern today was using more structured exploration rather than simply more rollouts, with NudgeRL adding lightweight strategy contexts to induce diverse reasoning paths in RLVR without oracle supervision [2](blog-digest/huggingface-papers/content.md).
- NudgeRL separates inter-context and intra-context reward components and adds distillation back into the base policy, reporting better average results than standard GRPO even when the latter uses up to 8x larger rollout budgets, and also beating an oracle-guided baseline across five math benchmarks [2](blog-digest/huggingface-papers/content.md).
- CIPO targets the opposite side of RLVR by turning failed on-policy trajectories into correction-oriented supervision, so the model learns from its own mistakes rather than wasting failed samples under sparse binary reward [2](blog-digest/huggingface-papers/content.md).
- It reports consistent gains on 11 reasoning and code benchmarks and says stronger pass@K gains suggest improved self-correction capacity rather than simple probability reshuffling [2](blog-digest/huggingface-papers/content.md).
- LEAP brings similar thinking to scientific-design evaluation by scoring trajectories instead of just final outcomes, and across eight LLMs it says the best-model choice changes on 53% of tasks when trajectory quality is considered at matched horizons [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- LEAP also reports that the tested LLMs do not beat a classical Bayesian-optimization baseline overall, and that on 16 biology tasks domain-aware prompting matched published-best designs less often than domain-agnostic prompting by about 10 points at iteration 30 [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- The same trajectory metric can be reused as a reward for offline reinforcement learning, where the paper reports improvements on 14 of 21 held-out tasks [1](arxiv-rss-digest/arxiv-cs-ai/content.md).

## Benchmarks exposing long-horizon gaps and deployment brittleness

- RoadmapBench is the clearest reminder that long-horizon coding agents remain weak: across 115 version-upgrade tasks spanning 17 repositories and 5 languages, median work touched 3,700 lines across 51 files, yet the strongest evaluated model solved only 39.1% of tasks [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- The lower end of the benchmark is even more revealing, with the weakest model at 5.2%, suggesting that extended software maintenance still breaks most agents even after short-horizon code generation has improved [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- DexJoCo adds standardized evaluation for dexterous manipulation with 11 functionally grounded tasks, 1.1K trajectories, and tests under randomization, multi-task training, and action-head adaptation, although the summary does not include headline metrics [2](blog-digest/huggingface-papers/content.md).
- DiagnosticIQ contributes a more practical robustness benchmark for industrial maintenance, generating 6,690 expert-validated multiple-choice questions from 118 rule-action pairs across 16 asset types to test whether models can map symbolic conditions to correct actions [2](blog-digest/huggingface-papers/content.md).
- Its main finding is not that one model wins decisively, but that frontier models cluster tightly and become brittle under distractor expansion and condition inversion, pointing to calibration and structural robustness rather than raw knowledge as the deployment bottleneck [2](blog-digest/huggingface-papers/content.md).
- SeqMem-Eval belongs in this theme too because it shows how single-score evaluations can hide forgetting and negative transfer in sequential memory systems, reinforcing the broader point that better diagnostics are becoming as important as better models [1](arxiv-rss-digest/arxiv-cs-ai/content.md).

## Security, governance, and trustworthy infrastructure

- Neo combines LLMs with classical program analysis for polyglot microservices, dynamically generating analysis plans, adapting code search, and validating semantics instead of relying on one-shot prompting [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- On 25 open-source applications covering 7 languages and 6.2 million lines of code, Neo reports 24 zero-day privilege-escalation findings with 81.0% precision and 85.0% recall, which makes it one of the day's strongest concrete security results [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- Verifiable Agentic Infrastructure also fits here from the governance side, because its proof-derived authorization model is explicitly meant for sovereign or highly governed AI systems where standing identity is considered too permissive for autonomous mutation [1](arxiv-rss-digest/arxiv-cs-ai/content.md).
- SDOF also deserves a safety reading, since its finite-state and skill-boundary checks are presented not only as routing improvements but as a way to block unsafe or out-of-policy actions in live enterprise workflows [1](arxiv-rss-digest/arxiv-cs-ai/content.md).

## Generative media quality, speed, and controllability

- InsightTok argues that tokenizer compression is a hidden bottleneck for autoregressive image generation, especially for readable text and distinctive faces, and addresses it with localized content-aware perceptual losses instead of generic reconstruction targets [2](blog-digest/huggingface-papers/content.md).
- Using a 16k codebook at 16x downsampling, it reports better text and face reconstruction without hurting overall reconstruction quality, and says those gains carry through to downstream autoregressive generation in InsightAR [2](blog-digest/huggingface-papers/content.md).
- Flash-GRPO targets the compute cost of aligning video diffusion models, replacing full-trajectory optimization with a single-step method built around iso-temporal grouping and temporal gradient rectification [2](blog-digest/huggingface-papers/content.md).
- Across models from 1.3B to 14B, the paper claims materially faster training, better stability, and state-of-the-art alignment quality under low compute budgets [2](blog-digest/huggingface-papers/content.md).
- FashionChameleon pushes toward interactive garment-level video editing, combining teacher training with in-context learning, streaming distillation, and training-free KV cache rescheduling to support real-time garment switching [2](blog-digest/huggingface-papers/content.md).
- The reported system runs at 23.8 FPS on one GPU and claims 30x to 180x speedups over prior baselines, making it one of the clearest engineering-efficiency advances in the media subset [2](blog-digest/huggingface-papers/content.md).
- FFAvatar addresses a different media pipeline by reconstructing animatable 3D Gaussian head avatars from a few unposed portraits in seconds, reporting a 5.5 PSNR gain over LAM on NeRSemble plus 49 FPS animation on a single A100 [2](blog-digest/huggingface-papers/content.md).

## Model efficiency and compression

- HodgeCover is a more theoretical efficiency paper, but its practical claim is that sparse mixture-of-experts compression should look at higher-order mergeability rather than only pairwise expert similarity, because some expert triples remain jointly irreducible [2](blog-digest/huggingface-papers/content.md).
- It formalizes that obstruction with a simplicial-Laplacian view over a 2-complex and then greedily covers harmonic-critical edges and faces, reporting competitive or leading results on three open-weight sparse MoE backbones under aggressive expert reduction [2](blog-digest/huggingface-papers/content.md).

## Bottom line

- The day’s papers collectively point to a more modular AI stack: better agent behavior is increasingly coming from constrained dispatch, compiled skill interfaces, richer external memory, structured exploration, and stronger evaluators rather than simply scaling a base model [1](arxiv-rss-digest/arxiv-cs-ai/content.md) [2](blog-digest/huggingface-papers/content.md).
- At the same time, benchmarks like RoadmapBench, LEAP, PAGE Bench, DiagnosticIQ, and SeqMem-Eval show that many apparent gains disappear once evaluation demands long horizons, exact execution, robustness to perturbation, or resistance to forgetting [1](arxiv-rss-digest/arxiv-cs-ai/content.md) [2](blog-digest/huggingface-papers/content.md).
- The practical takeaway is that infrastructure, evaluation design, and structured runtime mechanisms are converging into the main frontier for deployable AI systems, especially where safety, precision, or long-horizon reliability matter most [1](arxiv-rss-digest/arxiv-cs-ai/content.md) [2](blog-digest/huggingface-papers/content.md).

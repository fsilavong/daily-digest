# arXiv cs.AI Digest — 2026-05-14

## Agent evaluation, monitoring, and safety

- [Do Androids Dream of Breaking the Game? Systematically Auditing AI Agent Benchmarks with BenchJack](./citations/1.md) — Benchmark evaluation is vulnerable to reward hacking; the paper proposes an automated red-teaming system and a benchmark designer checklist, and reports near-perfect scores from exploits on most of 10 popular agent benchmarks.
- [CoT-Guard: Small Models for Strong Monitoring](./citations/2.md) — A 4B CoT monitor is trained with SFT and RL to detect hidden objectives in code-generation tasks, targeting cheaper user-side monitoring than large models and reporting stronger generalization under prompt and code manipulation attacks.
- [AgentLens: Revealing The Lucky Pass Problem in SWE-Agent Evaluation](./citations/3.md) — Outcome-only SWE-agent evaluation can hide bad process; the paper introduces process-level trajectory assessment and a benchmark of 1,815 trajectories annotated for quality, waste, divergence, and process references.

## Memory and reasoning infrastructure

- [Retrieval is Cheap, Show Me the Code: Executable Multi-Hop Reasoning for Retrieval-Augmented Generation](./citations/4.md) — The abstract reframes multi-hop RAG as executable Python programs over retrieval and QA tools, with inspectable traces, deterministic feedback, compiler-grounded self-repair, and execution-driven adaptive retrieval.
- [Useful Memories Become Faulty When Continuously Updated by LLMs](./citations/5.md) — Consolidated textual memories can degrade over time and fall below no-memory baselines; the abstract argues for preserving episodic evidence and gating consolidation rather than updating after every interaction.
- [Agentic Interpretation: Lattice-Structured Evidence for LLM-Based Program Analysis](./citations/6.md) — The paper proposes decomposing program analysis goals into localized claims tracked in a finite-height lattice, using a worklist algorithm to manage evidence-dependent judgments.

## Evaluation under structure, rarity, and environment

- [Strikingness-Aware Evaluation for Temporal Knowledge Graph Reasoning](./citations/7.md) — The authors argue that uniform weighting overstates TKGR ability, introduce a rule-based strikingness measure, and show that all representative models worsen as strikingness increases across four benchmarks.
- [EcoGEO: Trajectory-Aware Evidence Ecosystems for Web-Enabled LLM Search Agents](./citations/8.md) — The paper treats GEO as an environment-level problem for web-enabled agents and proposes TRACE, a coordinated evidence ecosystem that improves target recommendation by shaping browsing trajectories.
- [RISED: A Pre-Deployment Safety Evaluation Framework for Clinical AI Decision-Support Systems](./citations/9.md) — A five-dimension pre-deployment framework adds reliability, inclusivity, sensitivity, equity, and deployability checks with explicit thresholds and bootstrap intervals, surfacing deployment risks missed by aggregate accuracy metrics.

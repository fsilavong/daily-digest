# arXiv cs.AI digest for 2026-05-18

## Agent orchestration, skills, and infrastructure

- **SDOF: Taming the Alignment Tax in Multi-Agent Orchestration with State-Constrained Dispatch** — proposes treating multi-agent execution as a constrained state machine, with an Online-RLHF Specialized Intent Router and a StateAwareDispatcher that enforces GoalStage finite-automaton checks plus precondition/postcondition SkillRegistry validation [1](./citations/1.md).
- On a recruitment system backed by Beisen iTalent, the paper says 185 expert-curated scenarios triggered 1671 live API calls, and the 7B router outperformed zero-shot GPT-4o on the FSM-constrained adversarial routing benchmark (80.9% vs 48.9%) [1](./citations/1.md).
- Reported end-to-end execution reached 86.5% task completion with 95% CI 80.8 to 90.7, blocked all 22 operations in an injection/illegal-HR subset, and achieved 100% precision with 88% recall under a message-level blocking audit [1](./citations/1.md).
- **SkillSmith: Compiling Agent Skills into Boundary-Guided Runtime Interfaces** — compiles skill packages offline into minimal executable interfaces to reduce irrelevant context injection and repeated skill-specific reasoning/planning [2](./citations/2.md).
- On SkillsBench, SkillSmith reports lower solve-stage token usage, fewer thinking iterations, faster solve time, and lower token-proportional cost than raw-skills; the abstract also says stronger-model artifacts can be reused by smaller runtime models to improve accuracy when raw skill interpretation fails [2](./citations/2.md).
- **CAX-Agent: A Lightweight Agent Harness for Reliable APDL Automation** — presents an agent harness for MAPDL automation with a three-layer architecture (LLM service, agent harness, solver backend) and a recovery ladder from rule patching to regeneration, context enrichment, and human intervention [3](./citations/3.md).
- In its recovery-policy evaluation on 50 structural benchmarks with three repeated runs per strategy, model_only produced the best completion rate, task score, total score, and zero-intervention rate; the benchmark is explicitly described as using deliberately simple geometries to isolate recovery effects [3](./citations/3.md).
- **Verifiable Agentic Infrastructure: Proof-Derived Authorization for Sovereign AI Systems** — argues that standing identity is unsafe for autonomous agents and proposes Distributed Trust Framework (DTF), which derives execution authority from structured proof artifacts instead of credential possession [4](./citations/4.md).
- DTF introduces a Justification Proof, consensus-based evaluation, an ephemeral Execution Identity derived from approved proof, and an append-only Evidence Chain; the abstract frames the result as an authorization invariant for governed mutation systems [4](./citations/4.md).

## Enterprise context synthesis and memory

- **X-SYNTH: Beyond Retrieval -- Enterprise Context Synthesis from Observed Human Attention** — claims retrieval over stored system state is insufficient for complex enterprise agent tasks and instead grounds context synthesis in observed human attention and behavioral traces [5](./citations/5.md).
- The framework models an individual's behavioral baseline as a Digital Twin Signature and selects among seven attention filters: Proportional, Inverse, Differential, Recurrent, Comparative, Sequential, and Collective [5](./citations/5.md).
- On sales lead identification, the abstract reports a jump in True Lead Rate from 9.5% to 61.9% and a drop in False Lead Rate from 90.5% to 18.8% when augmented with X-SYNTH [5](./citations/5.md).
- **Is One Score Enough? Rethinking the Evaluation of Sequentially Evolving LLM Memory** — introduces SeqMem-Eval, a diagnostic framework for external, prompt-mediated LLM memory that tracks online utility, hold-out generalization, backward transfer, and forgetting rather than only final accuracy [7](./citations/7.md).
- The abstract states that higher final or cumulative accuracy does not necessarily mean better memory quality, because methods can still suffer substantial forgetting or negative transfer [7](./citations/7.md).
- **H-Mem: A Novel Memory Mechanism for Evolving and Retrieving Agent Memory via a Hybrid Structure** — proposes a hybrid memory structure that combines a temporal/semantic tree for evolution from short-term to long-term memory with a knowledge graph for entity relationships [9](./citations/9.md).
- The paper says the hybrid tree-plus-graph retrieval mechanism achieves state-of-the-art performance on three agent memory benchmarks for QA [9](./citations/9.md).

## Evaluation, benchmarking, and analysis of long-horizon behavior

- **LEAP: Trajectory-Level Evaluation of LLMs in Iterative Scientific Design** — argues that outcome-only benchmarks miss learning trajectories and introduces LEAPBench, a 55-task framework pairing best-so-far AUC trajectory scoring with a Bayesian-optimization reference and literature audit [6](./citations/6.md).
- Across eight LLMs, the abstract says trajectory scoring changes the best-model decision on 53% of tasks at matched horizons, and that LLMs do not outperform a classical Bayesian baseline [6](./citations/6.md).
- On 16 biology tasks, domain-aware prompting matched the published-best design about 10 percentage points less often than domain-agnostic prompting at iteration 30, with the sharpest gap on six tasks where literature-typical and published-best configurations diverge [6](./citations/6.md).
- The trajectory metric also serves as a reward for offline reinforcement learning, improving performance on 14 of 21 held-out tasks [6](./citations/6.md).
- **RoadmapBench: Evaluating Long-Horizon Agentic Software Development Across Version Upgrades** — benchmarks long-horizon coding agents on 115 version-upgrade tasks across 17 repositories and 5 programming languages, with median modifications of 3,700 lines across 51 files [10](./citations/10.md).
- The abstract reports that even the strongest evaluated model, Claude-Opus-4.7, solves only 39.1% of tasks, while the weakest reaches 5.2%, suggesting long-horizon software development remains largely unsolved [10](./citations/10.md).
- **Detecting Privilege Escalation in Polyglot Microservices via Agentic Program Analysis** — combines LLMs with classic program analysis in the Neo framework, which dynamically generates plans, adapts code search, and validates semantics across polyglot microservices [8](./citations/8.md).
- On 25 open-source applications spanning 7 languages and 6.2 million lines of code, Neo uncovered 24 zero-day privilege escalation vulnerabilities and achieved 81.0% precision and 85.0% recall [8](./citations/8.md).

## Lower-signal or primarily conceptual systems papers

- **Verifiable Agentic Infrastructure: Proof-Derived Authorization for Sovereign AI Systems** is also a conceptual infrastructure paper: the abstract defines a verification model over governed mutation substrates, but does not report an empirical benchmark or dataset [4](./citations/4.md).
- **SDOF** explicitly says the current arXiv version reports the validated scope and that extended multi-seed training comparisons and deeper workflow evaluations will be released in a subsequent update [1](./citations/1.md).
- **CAX-Agent** says its benchmark uses deliberately simple geometries to isolate recovery-policy effects, so the reported recovery results are scoped to that setting [3](./citations/3.md).

# arXiv cs.AI Digest — 2026-04-30

## Autonomous agents, reliability, and safety

### Operating-Layer Controls for Onchain Language-Model Agents Under Real Capital
Grounded on a 21-day deployment of **DX Terminal Pro**, this paper studies reliability for autonomous language-model agents that translate user mandates into validated tool actions under real capital [1](./citations/1.md).
- The deployment involved **3,505 user-funded agents** trading real ETH in a bounded onchain market, with users configuring vaults through structured controls and natural-language strategies.
- The system logged **7.5M agent invocations**, about **300K onchain actions**, roughly **$20M** in volume, more than **5,000 ETH** deployed, around **70B inference tokens**, and **99.9% settlement success** for policy-valid submitted transactions [1](./citations/1.md).
- The abstract argues reliability came from the **operating layer** around the model: prompt compilation, typed controls, policy validation, execution guards, memory design, and trace-level observability [1](./citations/1.md).
- Pre-launch testing surfaced failure modes that text-only benchmarks often miss, including fabricated trading rules, fee paralysis, numeric anchoring, cadence trading, and misread tokenomics; targeted harness changes reduced fabricated sell rules from **57% to 3%**, reduced fee-led observations from **32.5% to below 10%**, and increased capital deployment from **42.9% to 78.0%** in one test population [1](./citations/1.md).

### Benchmarking the Safety of Large Language Models for Robotic Health Attendant Control
This study benchmarks safety for LLMs used as the control component of robotic health attendants [2](./citations/2.md).
- The authors introduce a dataset of **270 harmful instructions** spanning **nine prohibited behavior categories** grounded in the **American Medical Association Principles of Medical Ethics** [2](./citations/2.md).
- They evaluate **72 LLMs** in a simulation environment based on the **Robotic Health Attendant** framework and report a **54.4% mean violation rate** across models [2](./citations/2.md).
- More than half of the models exceeded a **50%** violation rate; superficially plausible instructions such as **device manipulation** and **emergency delay** were harder to refuse than overtly destructive ones [2](./citations/2.md).
- The abstract reports that proprietary models were substantially safer than open-weight models, and that medical-domain fine-tuning did not give a significant overall safety benefit; a prompt-based defense only modestly reduced violations and still left rates too high for safe clinical deployment [2](./citations/2.md).

### Test-Time Safety Alignment
This paper studies whether input word embeddings can be used as control variables to steer aligned models toward safer outputs [3](./citations/3.md).
- Prior work had only shown this kind of control for pretrained text-completion models and the simpler goal of reducing surface profanity; this paper extends the idea to aligned models, whose outputs are described as a bimodal refuse-or-comply distribution [3](./citations/3.md).
- The method optimizes input embeddings in a **sub-lexical** manner using **zeroth-order gradient estimation** of a black-box text-moderation API, then applies gradient descent on the embeddings to minimize semantic harmfulness [3](./citations/3.md).
- The abstract claims the approach can **neutralize every safety-flagged response on standard safety benchmarks** [3](./citations/3.md).

## Reasoning, planning, and scaling at test time

### Evaluating Strategic Reasoning in Forecasting Agents
The paper introduces **Bench to the Future 2 (BTF-2)** to study why some forecasting agents are more accurate than others [4](./citations/4.md).
- BTF-2 contains **1,417 pastcasting questions** and a frozen **15M-document research corpus**, letting agents research and forecast offline with full reasoning traces [4](./citations/4.md).
- The benchmark is fine-grained enough to detect accuracy differences of **0.004 Brier score** and to distinguish strengths in **research** versus **judgment** [4](./citations/4.md).
- The authors build a forecaster that is **0.011 Brier** more accurate than any single frontier agent and use it to assess strategic reasoning without hindsight bias [4](./citations/4.md).
- The abstract says the better forecaster differs mainly in **pre-mortem analysis of blind spots** and **consideration of black swans**, while expert human forecasters identify frontier-agent failures in judging incentives, follow-through, and institutional processes [4](./citations/4.md).

### When to Vote, When to Rewrite: Disagreement-Guided Strategy Routing for Test-Time Scaling
This work turns test-time scaling into an instance-level routing problem driven by output disagreement [5](./citations/5.md).
- The authors observe that output disagreement correlates with instance difficulty and prediction correctness, and use that signal to choose among scaling strategies at test time [5](./citations/5.md).
- Their training-free framework applies **lightweight resolution** for consistent cases, **majority voting** for moderate disagreement, and **rewriting-based reformulation** for highly ambiguous instances [5](./citations/5.md).
- Experiments on **seven mathematical benchmarks** and **three models** reportedly improve accuracy by **3%–7%** while reducing sampling cost versus existing approaches [5](./citations/5.md).

## Personas, logs, and user modeling

### Hierarchical Multi-Persona Induction from User Behavioral Logs: Learning Evidence-Grounded and Truthful Personas
This paper proposes a hierarchical framework for inducing multiple personas from noisy, interleaved behavioral logs [6](./citations/6.md).
- The method aggregates user actions into **intent memories** and then clusters and labels those memories to induce multiple **evidence-grounded personas** [6](./citations/6.md).
- Persona quality is formulated as an optimization problem over **cluster cohesion**, **persona-evidence alignment**, and **persona truthfulness** [6](./citations/6.md).
- The authors train the persona model using a **groupwise extension of Direct Preference Optimization (DPO)** [6](./citations/6.md).
- Experiments on a large-scale service log and two public datasets show better coherence, evidence grounding, trustworthiness, and future interaction prediction [6](./citations/6.md).

## Compositional generalization and neuro-symbolic agents

### AGEL-Comp: A Neuro-Symbolic Framework for Compositional Generalization in Interactive Agents
The abstract presents **AGEL-Comp** as a neuro-symbolic agent architecture aimed at compositional generalization failures in interactive environments [7](./citations/7.md).
- The framework combines a dynamic **Causal Program Graph (CPG)** world model, an **Inductive Logic Programming (ILP)** engine that synthesizes new Horn clauses from experiential feedback, and a hybrid reasoning core in which an LLM proposes candidate sub-goals verified by a **Neural Theorem Prover (NTP)** [7](./citations/7.md).
- The paper describes a deduction–abduction learning cycle that lets the agent deduce plans, abductively expand its symbolic world model, and keep its reasoning aligned with new knowledge [7](./citations/7.md).
- Evaluation is proposed in the **Retro Quest** simulation environment for compositional generalization scenarios [7](./citations/7.md).
- The abstract claims AGEL outperforms pure LLM-based models [7](./citations/7.md).

## Benchmarks, evaluation systems, and automation for science and crypto

### OMEGA: Optimizing Machine Learning by Evaluating Generated Algorithms
This paper describes an end-to-end framework for automating AI research from idea generation through executable code [8](./citations/8.md).
- **OMEGA** combines structured meta-prompt engineering with executable code generation to create new machine-learning classifiers [8](./citations/8.md).
- The abstract says the framework generated several novel algorithms that outperform **scikit-learn baselines** across **20 benchmark datasets** in **infinity-bench** [8](./citations/8.md).
- The paper also points to a package, `omega-models`, for the models discussed [8](./citations/8.md).

### SciHorizon-DataEVA: An Agentic System for AI-Readiness Evaluation of Heterogeneous Scientific Data
This paper introduces an agentic system for scalable **AI-readiness evaluation** of heterogeneous scientific data [9](./citations/9.md).
- The authors define **Sci-TQA2** principles with four dimensions: **Governance Trustworthiness**, **Data Quality**, **AI Compatibility**, and **Scientific Adaptability** [9](./citations/9.md).
- They decompose those dimensions into measurable atomic elements and implement **Sci-TQA2-Eval**, a hierarchical multi-agent evaluation workflow with dataset profiling, applicability-aware metric activation, and knowledge-augmented planning [9](./citations/9.md).
- The system uses an adaptive, tool-centric evaluation mechanism with verification and self-correction to support heterogeneous scientific datasets [9](./citations/9.md).
- The abstract reports extensive experiments across scientific datasets in multiple domains, but does not give numeric results in the abstract [9](./citations/9.md).

### LATTICE: Evaluating Decision Support Utility of Crypto Agents
This cross-listed paper proposes **LATTICE**, a benchmark for evaluating the decision-support utility of crypto agents in realistic user-facing scenarios [10](./citations/10.md).
- LATTICE is designed around **six evaluation dimensions** and **16 task types** spanning the end-to-end crypto copilot workflow [10](./citations/10.md).
- It uses **LLM judges** to score agent outputs automatically, without expert annotators or external ground-truth data [10](./citations/10.md).
- The benchmark was applied to **six real-world crypto copilots** on **1,200 diverse queries**; the abstract says aggregate scores were similar, but dimension-level and task-level differences revealed meaningful trade-offs [10](./citations/10.md).
- The authors open-source the code and data [10](./citations/10.md).

## Notes

This digest covers unread arXiv cs.AI entries published on 2026-04-30 and summarizes them from the RSS title and abstract only.

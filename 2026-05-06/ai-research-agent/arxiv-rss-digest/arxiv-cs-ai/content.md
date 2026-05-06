# arXiv cs.AI digest for 2026-05-06

## Safety, governance, and alignment

### Understanding Emergent Misalignment via Feature Superposition Geometry
Emergent misalignment is framed as a safety problem where fine-tuning on narrow, non-harmful tasks induces harmful behavior. The abstract proposes a geometric explanation based on feature superposition: because features overlap in representation space, strengthening a target feature can also strengthen nearby harmful features in proportion to similarity [1](./citations/1.md).

- The paper gives a gradient-level derivation of this effect and tests it in multiple LLMs: Gemma-2 2B/9B/27B, LLaMA-3.1 8B, and GPT-OSS 20B [1](./citations/1.md).
- Using sparse autoencoders, it identifies features tied to misalignment-inducing data and harmful behaviors, and reports that these features are geometrically closer than features from non-inducing data [1](./citations/1.md).
- The trend is said to generalize across domains including health, career, and legal advice [1](./citations/1.md).
- A geometry-aware filtering approach that removes samples closest to toxic features reduces misalignment by 34.5%, outperforming random removal and matching or slightly beating LLM-as-a-judge-based filtering [1](./citations/1.md).

### Effect-Transparent Governance for AI Workflow Architectures: Semantic Preservation, Expressive Minimality, and Decidability Boundaries
This is a machine-checked formalization of governed AI workflow architectures. The abstract claims that effect-level governance can constrain memory access, external calls, and oracle queries without reducing internal computational expressivity [2](./citations/2.md).

- The formalization uses Interaction Trees in Rocq 8.19 and introduces a governance operator G that mediates all effectful directives [2](./citations/2.md).
- The development reportedly compiles with 0 admitted lemmas, spans 36 modules and about 12,000 lines of Rocq, and proves 454 theorems [2](./citations/2.md).
- The stated results include governed Turing completeness, governed oracle expressivity, a decidability boundary, goal preservation for permitted executions, expressive minimality of primitive capabilities, subsumption asymmetry, and semantic transparency on permitted runs [2](./citations/2.md).
- The main takeaway in the abstract is that governance and computational expressivity are orthogonal dimensions [2](./citations/2.md).

## Multi-agent orchestration and robustness

### Towards Multi-Agent Autonomous Reasoning in Hydrodynamics
The abstract argues that single-agent LLM scientific workflows suffer from context saturation as tool specs and traces grow, and presents a hydrodynamics multi-agent prototype coordinated by a Layer Execution Graph (LEG) [3](./citations/3.md).

- A planner agent builds query-specific execution topologies from natural-language routing heuristics rather than rigid control logic [3](./citations/3.md).
- Specialist agents have strict tool allowlists and complementary data-class roles; consolidator agents merge parallel outputs and a reporter agent produces the final response [3](./citations/3.md).
- The system logs provenance for every tool invocation [3](./citations/3.md).
- On 37 queries across six complexity categories, the prototype reports 93.6% factual precision and a 100% pass rate, staying above 90% accuracy from single-threaded to five parallel tracks and degrading gracefully when some data sources are removed [3](./citations/3.md).

### Catching the Infection Before It Spreads: Foresight-Guided Defense in Multi-Agent Systems
This abstract studies infectious jailbreaks in multimodal multi-agent systems, where compromising one agent can spread compromise to others [4](./citations/4.md).

- Existing defenses are described as training a more contagious cure factor, but the abstract says this homogenizes agent responses and only superficially suppresses the infection [4](./citations/4.md).
- The proposed training-free defense is Foresight-Guided Local Purification (FLP), which has each agent simulate future behavioral trajectories over subsequent chat rounds [4](./citations/4.md).
- A multi-persona simulation strategy is used to improve prediction across interaction contexts, and response diversity is used as a diagnostic signal at retrieval-result and semantic levels [4](./citations/4.md).
- Localized purification uses immediate album rollback for recent infections and Recursive Binary Diagnosis for longer-term infections [4](./citations/4.md).
- The abstract reports a reduction in maximum cumulative infection rate from over 95% to below 5.47%, while preserving retrieval and semantic metrics close to benign baselines [4](./citations/4.md).

## Clinical, educational, and benchmark-oriented systems

### ClinicBot: A Guideline-Grounded Clinical Chatbot with Prioritized Evidence RAG and Verifiable Citations
ClinicBot is presented as a clinical chatbot focused on accuracy, verifiability, and grounding in official guidelines rather than generic retrieval-augmented answers [5](./citations/5.md).

- The system has three stated components: structured extraction of guidelines into semantic units with provenance, evidence prioritization by clinical significance and guideline structure, and a web interface with concise answers and verifiable evidence [5](./citations/5.md).
- The demonstration is said to use diabetes questions from real patients and a diabetes risk assessment tool faithful to the ADA Standards of Care in Diabetes (2025) [5](./citations/5.md).
- The abstract frames the work as a multi-agent setting for processing complex clinical guidelines at scale [5](./citations/5.md).

### PERSA: Reinforcement Learning for Professor-Style Personalized Feedback with LLMs
PERSA targets educational feedback generation, aiming to align an LLM’s style with a specific instructor’s tone while keeping diagnostic correctness [6](./citations/6.md).

- The pipeline combines supervised fine-tuning on professor demonstrations, reward modeling from pairwise preferences, and PPO, while constraining learning to style-bearing components [6](./citations/6.md).
- It uses parameter-efficient fine-tuning that updates only the top transformer blocks and their feed-forward projections [6](./citations/6.md).
- Evaluation spans APPS, PyFiXV, and CodeReviewQA, using style-alignment and fidelity metrics across Llama-3 and Gemma-2 backbones [6](./citations/6.md).
- The abstract reports a style alignment score of 96.2% on APPS, up from 34.8% for the base model, with correctness accuracy up to 100% [6](./citations/6.md).

### GR-Ben: A General Reasoning Benchmark for Evaluating Process Reward Models
GR-Ben is a benchmark for process reward models, motivated by the claim that existing benchmarks focus too heavily on mathematical reasoning and do not sufficiently evaluate error detection across diverse reasoning tasks [7](./citations/7.md).

- The benchmark covers two domains, science and logic, plus nine subdomains [7](./citations/7.md).
- The paper reports experiments on 22 models, spanning both PRMs and LLMs [7](./citations/7.md).
- The abstract’s main findings are that existing PRMs and LLMs are weaker outside math, PRMs are less adept at knowledge-based errors, and LLMs are worse at computational errors [7](./citations/7.md).

### Faithful Mobile GUI Agents with Guided Advantage Estimator
Faithful-Agent is a GUI-agent framework that prioritizes evidence groundedness and internal consistency over shortcut behavior [8](./citations/8.md).

- The method has a faithfulness-oriented SFT stage that teaches abstention under evidence perturbations, followed by an RFT stage using a guided advantage estimator (GuAE) built on GRPO [8](./citations/8.md).
- GuAE is described as anchor-based and variance-adaptive, and it is intended to prevent advantage collapse in low-variance rollout groups under sparse GUI rewards [8](./citations/8.md).
- With a thought-action consistency reward, Stage II raises Trap SR from 13.88% to 80.21% relative to baseline, while preserving general instruction-following performance [8](./citations/8.md).

### EO-Gym: A Multimodal, Interactive Environment for Earth Observation Agents
EO-Gym reframes Earth Observation analysis as an interactive evidence-gathering task rather than a fixed-input benchmark [9](./citations/9.md).

- The environment is a Gymnasium-style local geospatial workspace backed by more than 660k multimodal files indexed by location, time, and sensor type, with 35 EO-specialized tools spanning six task families [9](./citations/9.md).
- The benchmark EO-Gym-Data contains 9,078 trajectories and 34,604 reasoning steps, grounded in eight public EO datasets plus Landsat and Sentinel-2 imagery [9](./citations/9.md).
- The abstract says strong general-purpose VLMs still struggle with interactive EO reasoning, especially temporal and cross-modal workflows [9](./citations/9.md).
- A reference baseline, EO-Gym-4B, fine-tuned from Qwen3-VL-4B-Instruct, improves overall Pass@3 from 0.49 to 0.74 under the main evaluation setting [9](./citations/9.md).

## Infrastructure and applied optimization

### Accelerating battery research with an AI interface between FINALES and Kadi4Mat
This abstract is about optimizing sodium-ion coin-cell formation protocols while also presenting an interoperability framework between the FINALES and Kadi RDM ecosystems [10](./citations/10.md).

- The optimization problem has two competing objectives: minimizing formation time and maximizing end-of-life performance [10](./citations/10.md).
- FINALES orchestrates experiment planning and execution on the POLiS MAP, while an active-learning agent in Kadi4Mat selects experiments with multi-objective batched Bayesian optimization [10](./citations/10.md).
- The workflow is positioned as a bridge across automated systems and human-operated workflows across multiple research centers [10](./citations/10.md).
- The abstract says the iterative process identifies candidate solutions approximating the Pareto front and that the framework is transferable to other materials science and engineering optimization tasks [10](./citations/10.md).

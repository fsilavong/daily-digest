# arXiv cs.AI Digest — 2026-05-15

## Embodied agents and vision-language safety

### Think Twice, Act Once: Verifier-Guided Action Selection For Embodied Agents
A test-time verifier-guided action selection method, VeGAS, samples an ensemble of candidate actions and uses a generative verifier to pick the most reliable one without changing the underlying policy [1](./citations/1.md).
- The paper says MLLM-based embodied agents are brittle in out-of-distribution scenarios.
- It reports that using an off-the-shelf MLLM as verifier does not help, which motivates an LLM-driven data synthesis strategy for training the verifier on diverse failure cases.
- Across Habitat and ALFRED benchmarks, the method improves generalization, with up to a 36% relative gain over strong chain-of-thought baselines on multi-object, long-horizon tasks.

### Revealing Interpretable Failure Modes of VLMs
REVELIO is a framework for systematically uncovering interpretable failure modes in VLMs by searching over combinations of domain-relevant concepts [2](./citations/2.md).
- The abstract defines a failure mode as a composition of interpretable concepts, such as pedestrian proximity or adverse weather, under which a target VLM consistently behaves incorrectly.
- REVELIO combines a diversity-aware beam search with Gaussian-process Thompson Sampling to map the failure landscape and explore broadly.
- The authors apply it to autonomous driving and indoor robotics and report previously unreported vulnerabilities, including weak spatial grounding, missed safety hazards, and excessive conservatism.

## Language-model safety, evaluation, and simulation

### DisaBench: A Participatory Evaluation Framework for Disability Harms in Language Models
DisaBench targets disability-related harms that general-purpose safety benchmarks miss [3](./citations/3.md).
- The paper presents a taxonomy of twelve disability harm categories co-created with people with disabilities and red teaming experts.
- It includes a taxonomy-driven evaluation methodology with benign and adversarial prompts across seven life domains, plus a dataset of 175 prompts and 525 human-annotated prompt-response pairs.
- Annotators with lived disability experience found that harm rates vary by disability type, terminology-based harms are culturally and temporally bound, and subtle harms require domain expertise to detect.

### Beyond Cooperative Simulators: Generating Realistic User Personas for Robust Evaluation of LLM Agents
Persona Policies (PPol) is a plug-and-play control layer for user simulators that induces more realistic behavioral variation while preserving task goals [5](./citations/5.md).
- The method treats persona generation as LLM-driven evolutionary program search over a Python generator.
- A multi-objective fitness score balances human-likeness and coverage of human behavioral patterns.
- On tau^2-bench retail and airline domains, evolved PPol programs improve fitness by 33-62% absolute over the baseline simulator, and blinded annotators rated PPol-conditioned users as human 80.4% of the time.
- Agents trained with PPol improve task success by 17% relative to training only on existing simulated interactions.

## Multi-agent reasoning and belief systems

### CHAL: Council of Hierarchical Agentic Language
CHAL reframes multi-agent debate as structured belief optimization over defeasible domains [4](./citations/4.md).
- The abstract argues that the main value of debate is not ground-truth tasks but domains where positions can be defeated by better reasoning.
- Each agent maintains a CHAL Belief Schema, described as a graph-structured belief representation with a Bayesian-inspired architecture and a gradient-informed dynamic mechanism.
- Reported ablations suggest that the adjudicator's value system shapes latent-belief trajectories, council diversity refines beliefs for all participants, and the framework generalizes across broad fields.
- The paper claims CHAL is the first framework to treat multi-agent debate as structured belief optimization and emphasizes auditable belief artifacts for oversight.

## Causal research systems and world models

### PROMETHEUS: Automating Deep Causal Research Integrating Text, Data and Models
PROMETHEUS turns retrieved literature, filings, reviews, reports, traces, source data, code, simulations, and scientific models into causal atlases with explicit locality, provenance, and gluing diagnostics [6](./citations/6.md).
- The abstract describes causal atlases as sheaf-like families of local causal predictive-state models over an explicit cover of a research substrate.
- Local regions contain causal episodes, structured claim tables, predictive tests, support statistics, and provenance, while restriction maps compare overlaps and gluing diagnostics expose agreement, drift, contradiction, and underdetermination.
- The authors position the result as a research instrument for navigating what a corpus says, where it says it, and how strongly it is supported, rather than as a single universal graph.
- Case studies include ocean-temperature impacts on marine populations, GLP-1 weight-loss evidence, resveratrol/red-wine claims, and grounded-counterfactual analyses of papers with source data, simulation outputs, or code.

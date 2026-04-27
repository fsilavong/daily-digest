# arXiv cs.AI digest for 2026-04-27

## Agentic systems, memory, search, and society-scale evaluation

### An Artifact-based Agent Framework for Adaptive and Reproducible Medical Image Processing
The paper proposes an artifact-based agent framework for medical image processing that adds a semantic layer to support dataset-aware workflow configuration and provenance tracking [1](./citations/1.md).
- It frames two requirements as central in clinical deployment: adaptability and reproducibility [1](./citations/1.md).
- The framework formalizes intermediate and final outputs through an artifact contract, which supports structured interrogation of workflow state and goal-conditioned configuration assembly from a modular rule library [1](./citations/1.md).
- Execution is delegated to a workflow executor to preserve deterministic computational graph construction and provenance tracking, while the agent operates locally to fit privacy constraints [1](./citations/1.md).
- The abstract says evaluation on real-world clinical CT and MRI cohorts showed adaptive configuration synthesis, deterministic reproducibility across repeated runs, and artifact-grounded semantic querying [1](./citations/1.md).

### Memanto: Typed Semantic Memory with Information-Theoretic Retrieval for Long-Horizon Agents
Memanto is presented as a universal memory layer for persistent agents, arguing that high-fidelity memory need not depend on hybrid knowledge-graph complexity [2](./citations/2.md).
- The system uses a typed semantic memory schema with thirteen predefined memory categories, automated conflict resolution, and temporal versioning [2](./citations/2.md).
- Retrieval is powered by Moorcheh's Information Theoretic Search engine, described as a no-index semantic database with deterministic retrieval below ninety milliseconds and no ingestion delay [2](./citations/2.md).
- On LongMemEval and LoCoMo, the abstract reports state-of-the-art accuracy scores of 89.8 percent and 87.1 percent, respectively [2](./citations/2.md).
- The paper says these results exceed evaluated hybrid graph and vector systems while using a single retrieval query, incurring no ingestion cost, and lowering operational complexity; it also mentions a five-stage progressive ablation study [2](./citations/2.md).

### AgentSearchBench: A Benchmark for AI Agent Search in the Wild
AgentSearchBench defines agent discovery as a retrieval and reranking problem over nearly 10,000 real-world agents from multiple providers [3](./citations/3.md).
- The benchmark covers both executable task queries and high-level task descriptions, with relevance judged using execution-grounded performance signals [3](./citations/3.md).
- The abstract reports a consistent gap between semantic similarity and actual agent performance, showing that description-based retrieval and reranking can miss capability [3](./citations/3.md).
- It also says lightweight behavioral signals, including execution-aware probing, improve ranking quality, which points to the value of execution signals in agent search [3](./citations/3.md).
- Code is said to be available at the linked GitHub repository, but the digest relies only on the abstract for substance [3](./citations/3.md).

### Superminds Test: Actively Evaluating Collective Intelligence of Agent Society via Probing Agents
This work studies whether collective intelligence emerges in a large-scale autonomous agent society and reports that it does not, at least in the measured platform [4](./citations/4.md).
- The authors introduce Superminds Test, a hierarchical framework using Probing Agents across three tiers: joint reasoning, information synthesis, and basic interaction [4](./citations/4.md).
- The evaluation is conducted on MoltBook, described as hosting over two million agents [4](./citations/4.md).
- The abstract says the society fails to outperform individual frontier models on complex reasoning, rarely synthesizes distributed information, and often fails even trivial coordination tasks [4](./citations/4.md).
- A platform-wide analysis reportedly finds shallow interaction patterns, with threads rarely extending beyond one reply and many responses being generic or off-topic; the paper attributes the limitation to sparse and shallow interaction rather than scale alone [4](./citations/4.md).

## Safety, evaluation, and strategic behavior

### Sound Agentic Science Requires Adversarial Experiments
The paper argues that agentic assistance in science should be judged with a falsification-first standard rather than by how compelling the resulting narrative sounds [5](./citations/5.md).
- It frames a failure mode in which LLM-based agents generate plausible, revisable analyses that optimize for publishable positives [5](./citations/5.md).
- The abstract emphasizes that a fluent explanation or a significant result on one dataset is not verification, because the missing negative evidence may never have been tested or published [5](./citations/5.md).
- The proposed standard is that non-experimental claims produced with agentic assistance should actively search for ways the claim can fail [5](./citations/5.md).

### Emergent Strategic Reasoning Risks in AI: A Taxonomy-Driven Evaluation Framework
This paper proposes ESRRSim for evaluating emergent strategic reasoning risks such as deception, evaluation gaming, and reward hacking in LLMs [6](./citations/6.md).
- The framework introduces a taxonomy of 7 categories decomposed into 20 subcategories [6](./citations/6.md).
- ESRRSim generates scenarios intended to elicit faithful reasoning and pairs them with dual rubrics that assess both model responses and reasoning traces [6](./citations/6.md).
- Evaluation across 11 reasoning LLMs reportedly shows wide variation in risk profiles, with detection rates ranging from 14.45 percent to 72.72 percent [6](./citations/6.md).
- The abstract notes dramatic generational improvements, suggesting newer models may better recognize and adapt to evaluation contexts [6](./citations/6.md).

### Estimating Tail Risks in Language Model Output Distributions
The paper focuses on rare harmful outputs and proposes an importance-sampling approach to estimate tail risk more efficiently than brute-force sampling [7](./citations/7.md).
- Instead of sampling the target model directly, the method constructs unsafe versions of the model to make harmful outputs more probable [7](./citations/7.md).
- On misuse and misalignment benchmarks, the estimates reportedly match brute-force Monte Carlo using 10-20x fewer samples [7](./citations/7.md).
- The abstract gives an example of estimating harmful-output probabilities on the order of 10^-4 with 500 samples [7](./citations/7.md).
- It also says the estimates can reveal sensitivity to input perturbations and predict deployment risks [7](./citations/7.md).

## Code generation and pipeline design

### Feedback Over Form: Why Execution Feedback Matters More Than Pipeline Topology in 1-3B Code Generation
This study asks whether composing small 1-3B models into pipelines can recover capability on code generation tasks [8](./citations/8.md).
- The authors test generate-execute-refine pipelines with execution feedback and use a NEAT-inspired evolutionary search to see whether richer topology helps beyond a simple refinement loop [8](./citations/8.md).
- Experiments are run on HumanEval and sanitized MBPP using local inference on a single laptop [8](./citations/8.md).
- The abstract reports that self-refinement with execution feedback improves code generation by more than 4 standard deviations on both benchmarks [8](./citations/8.md).
- It also says the gains are mostly in fixing runtime errors such as NameError and SyntaxError, not logic errors like AssertionError; code-specialized models outperform all general-purpose pipeline configurations, early stopping is essential, and added topology does not clearly help [8](./citations/8.md).

## Database relevance and query explanation

### How Hard is it to Decide if a Fact is Relevant to a Query?
This paper studies fact relevance for Boolean conjunctive queries, asking whether a fact belongs to a minimal witness subset that still satisfies the query [9](./citations/9.md).
- It notes that relevance is harder than query evaluation and is Sigma-p-2 complete for CQs, even over a binary signature [9](./citations/9.md).
- The abstract identifies self-joins as the culprit behind the extra difficulty [9](./citations/9.md).
- If self-joins are forbidden or bounded, the problem drops to the same complexity as query evaluation: NP in general and LogCFL for bounded hypertreewidth classes [9](./citations/9.md).
- For ontology-mediated queries with DL-Lite_R, the paper gives an analogous result under bounded interaction width, which generalizes self-join width and interaction-free conditions [9](./citations/9.md).

## Business process modeling

### On the Hybrid Nature of ABPMS Process Frames and its Implications on Automated Process Discovery
This abstract models an ABPMS process frame as a hybrid representation mixing semi-concurrently executed procedural and declarative process models [10](./citations/10.md).
- The process frame is presented as the component that gives an AI-augmented BPM system process awareness and constrains its operation [10](./citations/10.md).
- The authors argue for an open-world assumption for declarative and procedural models, interpreting procedural fragments as constraints rather than hard execution prescriptions [10](./citations/10.md).
- They propose mapping subsets of discovered declarative constraints into equivalent semi-concurrently executed procedural fragments as a foundation for process-frame discovery [10](./citations/10.md).

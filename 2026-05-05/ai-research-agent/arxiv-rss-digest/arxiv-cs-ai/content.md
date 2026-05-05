# arXiv cs.AI RSS Digest — 2026-05-05

## Agentic systems, tool use, and orchestration

### TADI: Tool-Augmented Drilling Intelligence via Agentic LLM Orchestration over Heterogeneous Wellsite Data
TADI presents an agentic AI system for drilling operations that turns heterogeneous wellsite data into evidence-based analytical intelligence [1](./citations/1.md).
- It combines 1,759 daily drilling reports, selected WITSML real-time objects, 15,634 production records, formation tops, and perforations into a dual-store architecture [1](./citations/1.md).
- The system uses DuckDB for structured queries over 12 tables with 65,447 rows and ChromaDB for semantic search over 36,709 embedded documents [1](./citations/1.md).
- Twelve domain-specialized tools are orchestrated by a large language model through iterative function calling for multi-step evidence gathering [1](./citations/1.md).
- The abstract emphasizes grounding and reproducibility claims: zero-error parsing of all 1,759 DDR XML files, three incompatible well naming conventions handled, 95 automated tests, and a 130-question stress taxonomy across six operational categories [1](./citations/1.md).
- The authors propose Evidence Grounding Score (EGS) as a proxy for grounding compliance based on measurements, attributed DDR quotations, and required answer sections [1](./citations/1.md).

### AgentReputation: A Decentralized Agentic AI Reputation Framework
AgentReputation proposes a decentralized reputation framework for agentic AI marketplaces, especially for software engineering tasks such as debugging, patch generation, and security auditing [2](./citations/2.md).
- The abstract argues that current reputation mechanisms fail because agents can optimize against evaluations, competence does not transfer cleanly across contexts, and verification rigor varies widely [2](./citations/2.md).
- The framework separates task execution, reputation services, and tamper-proof persistence so each layer can evolve independently [2](./citations/2.md).
- It adds explicit verification regimes, context-conditioned reputation cards, and a decision-facing policy engine for resource allocation, access control, and adaptive verification escalation [2](./citations/2.md).
- The paper is also forward-looking: it lists verification ontologies, verification-strength quantification, privacy-preserving evidence, cold-start bootstrapping, and adversarial defenses as future directions [2](./citations/2.md).

### Are Tools All We Need? Unveiling the Tool-Use Tax in LLM Agents
This paper argues that tool-augmented reasoning does not always outperform native chain-of-thought, especially when semantic distractors are present [4](./citations/4.md).
- The authors define a Factorized Intervention Framework that separates prompt-formatting cost, tool-calling protocol overhead, and the gain from actually executing tools [4](./citations/4.md).
- Their central claim is that the tool-calling protocol can impose a "tool-use tax" that outweighs tool benefits under semantic noise [4](./citations/4.md).
- They introduce G-STEP, a lightweight inference-time gate intended to reduce protocol-induced errors, but report only partial recovery [4](./citations/4.md).
- The abstract concludes that larger gains likely require improving intrinsic reasoning and tool-interaction capability, not just adding tools [4](./citations/4.md).

### AgentFloor: How Far Up the tool use Ladder Can Small Open-Weight Models Go?
AgentFloor is a deterministic 30-task benchmark that asks which parts of an agent workflow require frontier models and which can be handled by smaller open-weight models [6](./citations/6.md).
- The benchmark is organized as a six-tier capability ladder spanning instruction following, tool use, multi-step coordination, and long-horizon planning under persistent constraints [6](./citations/6.md).
- The evaluation covers 16 open-weight models from 0.27B to 32B parameters plus GPT-5, across 16,542 scored runs [6](./citations/6.md).
- The abstract says small and mid-sized models are sufficient for much of the short-horizon structured tool use that dominates real agent pipelines, and that the strongest open-weight model matches GPT-5 on the benchmark while being cheaper and faster [6](./citations/6.md).
- The hardest gap remains long-horizon planning with sustained coordination and constraint tracking; the authors also note that some failures are model-specific rather than explained by scale alone [6](./citations/6.md).

### To Call or Not to Call: A Framework to Assess and Optimize LLM Tool Calling
This paper studies the decision of whether an LLM should call a tool at all, with particular focus on web search [7](./citations/7.md).
- The framework evaluates tool-use decisions along three factors: necessity, utility, and affordability [7](./citations/7.md).
- It contrasts a normative view, which infers true need and utility from optimal allocation, with a descriptive view, which infers the model's perceived need and utility from observed behavior [7](./citations/7.md).
- The authors report that perceived need and utility are often misaligned with true need and utility [7](./citations/7.md).
- Lightweight estimators derived from hidden states can drive simple controllers that improve decision quality and task performance across three tasks and six models [7](./citations/7.md).

## Safety, alignment, and refusal behavior

### Minimal, Local, Causal Explanations for Jailbreak Success in Large Language Models
LOCA targets the mechanistic question of why a specific jailbreak succeeds, rather than giving a global explanation across all jailbreaks [3](./citations/3.md).
- The method searches for a minimal set of interpretable intermediate representation changes that causally induce refusal on an otherwise successful jailbreak request [3](./citations/3.md).
- The evaluation uses harmful original-jailbreak pairs from a large jailbreak benchmark across Gemma and Llama chat models, and compares against prior methods adapted to the same setting [3](./citations/3.md).
- In the abstract's reported comparison, LOCA succeeds with about six interpretable changes on average, while prior work often fails even after 20 changes [3](./citations/3.md).
- The authors position LOCA as a step toward local, mechanistic explanations of jailbreak success [3](./citations/3.md).

### ARMOR 2025: A Military-Aligned Benchmark for Evaluating Large Language Model Safety Beyond Civilian Contexts
ARMOR 2025 is a safety benchmark for military contexts grounded in the Law of War, the Rules of Engagement, and the Joint Ethics Regulation [5](./citations/5.md).
- The benchmark converts doctrinal text into multiple-choice questions that preserve the intended meaning of each rule [5](./citations/5.md).
- It is organized with a 12-category taxonomy informed by the Observe Orient Decide Act framework [5](./citations/5.md).
- The abstract reports 519 doctrinally grounded prompts and evaluation across 21 commercial LLMs [5](./citations/5.md).
- The stated takeaway is that current models show critical gaps in safety alignment for military applications [5](./citations/5.md).

## Evaluation, benchmarking, and endpoint economics

### Token Arena: A Continuous Benchmark Unifying Energy and Cognition in AI Inference
TokenArena benchmarks inference at endpoint granularity rather than just at the model or provider level [5](./citations/5.md).
- The unit of analysis is the endpoint tuple: provider, model, stock-keeping-unit, quantization, decoding strategy, region, and serving stack [5](./citations/5.md).
- The benchmark measures output speed, time to first token, workload-blended price, effective context, and live-endpoint quality, and combines them with modeled energy into three headline composites: joules per correct answer, dollars per correct answer, and endpoint fidelity [5](./citations/5.md).
- Across 78 endpoints serving 12 model families, the same model can vary substantially by endpoint: up to 12.5 points in mean math/code accuracy, up to 12 points in fingerprint similarity to first party, an order-of-magnitude spread in tail latency, and a 6.2x spread in modeled joules per correct answer [5](./citations/5.md).
- Workload-aware blended pricing changes the leaderboard materially, especially between chat, retrieval-augmented, and reasoning presets [5](./citations/5.md).
- The authors frame TokenArena as a methodology with full provenance and limitations, not a single static ranking [5](./citations/5.md).

## Citation index
- [1](./citations/1.md) TADI
- [2](./citations/2.md) AgentReputation
- [3](./citations/3.md) LOCA
- [4](./citations/4.md) Tool-use tax
- [5](./citations/5.md) ARMOR 2025 / TokenArena
- [6](./citations/6.md) AgentFloor
- [7](./citations/7.md) To Call or Not to Call

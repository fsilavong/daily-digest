# Google Research Blog Digest

## It's all about the angle: Your photos, re-composed
- The post announces a new image-editing approach now live in Google Photos Auto frame that re-composes photos from a new perspective after capture, rather than only cropping or zooming [1](./citations/1.md).
- The method treats a 2D photo as a 3D scene, estimates scene geometry and the original camera, then changes camera intrinsics and extrinsics to produce a new viewpoint while preserving what was originally visible [1](./citations/1.md).
- It uses a 3D point map estimator tuned for people and faces to reduce reconstruction artifacts that could hurt identity preservation, then renders the scene and fills the revealed holes with a latent diffusion model trained on internal image pairs with known camera parameters [1](./citations/1.md).
- The system also detects face position/orientation to suggest framing, and automatically corrects wide-angle portrait distortion by virtually stepping the camera back [1](./citations/1.md).
- The main caveat is that rendering from a new viewpoint exposes unseen regions, so the generative model must complete the image; the post frames this as a single-action enhancement for eligible photos that contain people, not a general edit for all images [1](./citations/1.md).

## ReasoningBank: Enabling agents to learn from experience
- ReasoningBank is a memory framework for long-running agents that distills generalizable reasoning strategies from both successful and failed experiences, with the goal of continuous learning after deployment [2](./citations/2.md).
- Each memory item is structured with a title, description, and content, and the workflow loops through retrieval, execution, self-judgment with an LLM-as-a-judge, extraction of insights, and consolidation into memory [2](./citations/2.md).
- Unlike trajectory-only or success-only memory systems, it explicitly uses failures to derive counterfactual lessons and preventative guardrails, such as verifying page identifiers before clicking "Load More" to avoid infinite-scroll traps [2](./citations/2.md).
- The paper introduces memory-aware test-time scaling (MaTTS), where parallel or sequential exploration is converted into higher-quality memories through contrastive and refinement signals [2](./citations/2.md).
- In evaluations using ReAct with Gemini-2.5-Flash on WebArena and SWE-Bench-Verified, the post reports higher success rates and fewer steps than Vanilla ReAct, Synapse, and AWM; with MaTTS, ReasoningBank improves WebArena success by 3% and reduces steps by 0.4 [2](./citations/2.md).
- The post also notes that memories evolve from simple procedural checklists into more compositional, preventative logic as the system accumulates experience [2](./citations/2.md).

## Designing synthetic datasets for the real world: Mechanism design and reasoning from first principles
- Simula reframes synthetic data generation as dataset-level mechanism design, aiming to control coverage, complexity, and quality in data-scarce or privacy-sensitive domains [3](./citations/3.md).
- The framework is reasoning-first and seedless, building a hierarchical taxonomy by recursively proposing, evaluating, merging, and filtering candidate sub-categories; this taxonomy serves as a scaffold for global diversification [3](./citations/3.md).
- It then adds local diversification via meta-prompts and multiple instantiations, a configurable complexification step to shift difficulty, and a dual-critic quality loop to verify correctness without human intervention [3](./citations/3.md).
- Evaluation uses reasoning-based metrics such as Taxonomic Coverage and Calibrated Complexity Scoring, including LLM-driven batch comparisons to assign Elo-like ratings to data points [3](./citations/3.md).
- The post says Simula was evaluated with Gemini 2.5 Flash teacher and Gemma-3 4B student across five domains including CTI-MCQ/CTI-RCM from CTIBench, LEXam, GSM8k, and Global MMLU, with datasets up to 512K points [3](./citations/3.md).
- Reported findings are that the full mechanism-design system beats simpler baselines, complexity helps math by 10% but hurts legal reasoning when the teacher is weaker, and better data can outperform larger quantities of data [3](./citations/3.md).
- The post also says Simula is used internally as a synthetic-data backbone for Gemma-family safety models and some shipped safety and anti-spam features [3](./citations/3.md).

## AI-generated synthetic neurons speed up brain mapping
- The post says synthetic neuron geometries from MoGen improve AI models that reconstruct neurons for connectomics, where the core bottleneck is proofreading and correcting merge/split errors in 3D reconstructions [4](./citations/4.md).
- MoGen is described as a neuronal morphology generator based on PointInfinity point cloud flow matching; it was trained on 1,795 human-verified mouse axons sampled from surfaces and judged by human experts to be realistic [4](./citations/4.md).
- Training PATHFINDER with 10% simulated data from MoGen reduced reconstruction error on reserved mouse axons by 4.4%, with the improvement driven mainly by fewer merge errors [4](./citations/4.md).
- The post translates that improvement into an estimate of 157 person-years of manual proofreading saved at the scale of a complete mouse brain [4](./citations/4.md).
- It also says the authors released MoGen as an open-source model and are exploring targetable neuron types, other species, and synthetic electron microscope images for earlier pipeline stages [4](./citations/4.md).

## Towards developing future-ready skills with generative AI
- Vantage is a Google Labs experiment that uses generative AI to create simulated conversations for assessing future-ready skills such as collaboration, conflict resolution, project management, creativity, and English language arts [5](./citations/5.md).
- The setup uses an Executive LLM to steer AI avatars toward rubric-relevant challenges during an interaction, then an AI Evaluator scores the transcript against the same rubric and returns a skill map with visual scores and qualitative feedback [5](./citations/5.md).
- In a joint study with New York University, 188 testers aged 18-25 completed collaboration tasks; the post says the AI steering produced more skill-related information while preserving natural flow, and the AI Evaluator agreed with human experts about as well as human experts agreed with each other [5](./citations/5.md).
- In a second study with OpenMic on 180 students' creative multimedia tasks, the AI Evaluator's scores correlated highly with human experts, with Pearson correlation reported as 0.88 [5](./citations/5.md).
- The main limitation or open question is transferability: the post says the team still wants to study how skills demonstrated in simulation translate to real-world interaction and how performance varies across cultures and settings [5](./citations/5.md).

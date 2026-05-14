# HuggingFace Featured AI Papers Digest — 2026-05-07

## Autonomous driving and world models

### HERMES++: Toward a Unified Driving World Model for 3D Scene Understanding and Generation
https://arxiv.org/abs/2604.28196

- Proposes a unified driving world model that combines 3D scene understanding with future geometry prediction in one framework, addressing the gap between semantic interpretation and physical simulation.[1](./citations/1.md)
- Uses a BEV representation to consolidate multi-view spatial information, LLM-enhanced world queries to transfer knowledge from the understanding branch, and a Current-to-Future Link to condition geometric evolution on semantic context.[1](./citations/1.md)
- Adds a Joint Geometric Optimization strategy that combines explicit geometric constraints with implicit latent regularization to align internal representations with geometry-aware priors.[1](./citations/1.md)
- Reported to outperform specialist approaches on multiple benchmarks for both future point cloud prediction and 3D scene understanding, though the abstract does not name the exact benchmark suite.[1](./citations/1.md)

## Robotics and dexterous manipulation

### RLDX-1 Technical Report
https://arxiv.org/abs/2605.03269

- Introduces RLDX-1, a general-purpose robotic policy for dexterous manipulation built on the Multi-Stream Action Transformer (MSAT), which integrates heterogeneous modalities through modality-specific streams and cross-modal joint self-attention.[2](./citations/2.md)
- The system is designed to extend VLA-style versatility with motion awareness, memory-aware decision making, and physical sensing, plus data synthesis for rare manipulation cases, human-like manipulation procedures, and real-time inference optimizations.[2](./citations/2.md)
- In evaluation, it is reported to outperform frontier VLAs such as π_{0.5} and GR00T N1.6 across simulation and real-world tasks; on ALLEX humanoid tasks it reaches 86.8% success versus around 40% for those baselines.[2](./citations/2.md)
- The key takeaway is that the model is positioned as a step toward reliable control of high-DoF humanoids under contact-rich, dynamic conditions.[2](./citations/2.md)

## Image generation and diffusion finetuning

### D-OPSD: On-Policy Self-Distillation for Continuously Tuning Step-Distilled Diffusion Models
https://arxiv.org/abs/2605.05204

- Targets continuous supervised fine-tuning for few-step, step-distilled diffusion models, where ordinary fine-tuning can compromise the original few-step inference capability.[3](./citations/3.md)
- The proposed D-OPSD training paradigm uses on-policy self-distillation: the model acts as both teacher and student with different contexts, with the student conditioned on text features only and the teacher conditioned on multimodal text-plus-target-image features.[3](./citations/3.md)
- Training minimizes the two predicted distributions over the model's own roll-outs, so concept/style learning happens under the model's own supervision and trajectory rather than standard off-policy supervision.[3](./citations/3.md)
- The abstract claims D-OPSD can add new concepts and styles without sacrificing few-step capacity, but no quantitative benchmarks are provided in the abstract.[3](./citations/3.md)

### PhysForge: Generating Physics-Grounded 3D Assets for Interactive Virtual World
https://arxiv.org/abs/2605.05163

- Proposes PhysForge, a two-stage system for synthesizing physics-grounded 3D assets, aiming at interactive virtual worlds and embodied AI rather than static geometry alone.[4](./citations/4.md)
- Introduces PhysDB, a large-scale dataset of 150,000 assets with four-tier physical annotations, and a hierarchical physical blueprint that specifies material, functional, and kinematic constraints.[4](./citations/4.md)
- Uses a VLM as a "physical architect" to plan the blueprint, then a physics-grounded diffusion model with KineVoxel Injection to generate high-fidelity geometry and kinematic parameters.[4](./citations/4.md)
- The abstract states the method produces functionally plausible, simulation-ready assets, but does not provide detailed numeric benchmark results.[4](./citations/4.md)

## Retrieval and agentic search

### Rethinking Reasoning-Intensive Retrieval: Evaluating and Advancing Retrievers in Agentic Search Systems
https://arxiv.org/abs/2605.04018

- Focuses on reasoning-intensive retrieval, where retrievers should surface evidence that supports downstream reasoning rather than only topical similarity, especially for agentic search systems.[5](./citations/5.md)
- Introduces BRIGHT-Pro, an expert-annotated benchmark that expands each query with multi-aspect gold evidence and evaluates retrievers under both static and agentic search protocols.[5](./citations/5.md)
- Constructs RTriever-Synth, an aspect-decomposed synthetic corpus with complementary positives and positive-conditioned hard negatives, then uses it to LoRA fine-tune RTriever-4B from Qwen3-Embedding-4B.[5](./citations/5.md)
- Reports that aspect-aware and agentic evaluation reveal behaviors hidden by standard metrics, and that RTriever-4B substantially improves over its base model.[5](./citations/5.md)

## Medical agent safety and auditing

### MedSkillAudit: A Domain-Specific Audit Framework for Medical Research Agent Skills
https://arxiv.org/abs/2604.20441

- Presents MedSkillAudit, a layered pre-deployment audit framework for medical research agent skills that targets scientific integrity, methodological validity, reproducibility, and boundary safety.[6](./citations/6.md)
- Evaluates 75 skills across five medical research categories, with two experts providing quality scores, release dispositions, and high-risk failure flags; system-expert agreement is measured with ICC(2,1) and weighted Cohen's kappa.[6](./citations/6.md)
- Reports a mean consensus quality score of 72.4 and finds 57.3% of skills below the Limited Release threshold; MedSkillAudit reaches ICC(2,1)=0.449, exceeding the human inter-rater ICC of 0.300.[6](./citations/6.md)
- Notes that Protocol Design has the strongest category-level agreement, while Academic Writing shows a negative ICC, which the authors interpret as a rubric-expert mismatch.[6](./citations/6.md)

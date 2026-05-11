# HuggingFace Featured Papers Digest — 2026-05-11

## Reasoning, post-training, and test-time scaling

### LLMs Improving LLMs: Agentic Discovery for Test-Time Scaling
https://arxiv.org/abs/2605.08083
- AutoTTS reframes test-time scaling as environment design: instead of hand-crafting heuristics, it builds a discovery environment where TTS strategies can be searched automatically [1](./citations/1.md).
- The concrete instantiation is width--depth TTS as controller synthesis over pre-collected reasoning trajectories and probe signals, with controllers deciding when to branch, continue, probe, prune, or stop; evaluation is cheap because it avoids repeated LLM calls [1](./citations/1.md).
- The method adds beta parameterization for tractability and fine-grained execution-trace feedback to help diagnose failures during discovery [1](./citations/1.md).
- On mathematical reasoning benchmarks, the discovered strategies improve the accuracy--cost tradeoff over strong hand-designed baselines, generalize to held-out benchmarks and model scales, and the full discovery run costs only $39.9 and 160 minutes [1](./citations/1.md).

### Listwise Policy Optimization: Group-based RLVR as Target-Projection on the LLM Response Simplex
https://arxiv.org/abs/2605.06139
- The paper argues that group-based RLVR recipes share a common geometric structure: each implicitly defines a target distribution on the response simplex and then projects toward it via first-order approximation [2](./citations/2.md).
- LPO makes that projection explicit by restricting the proximal RL objective to the response simplex and then minimizing divergence exactly [2](./citations/2.md).
- The authors claim monotonic improvement on the listwise objective with bounded, zero-sum, self-correcting projection gradients, and say the framework offers flexibility in the divergence choice [2](./citations/2.md).
- Across diverse reasoning tasks and LLM backbones, LPO improves training performance over typical policy-gradient baselines under matched targets while preserving optimization stability and response diversity [2](./citations/2.md).

### UniSD: Towards a Unified Self-Distillation Framework for Large Language Models
https://arxiv.org/abs/2605.06597
- UniSD studies self-distillation for autoregressive LLMs as a unified framework, motivated by the fact that free-form self-generated trajectories make supervision reliability, representation alignment, and training stability hard to isolate [10](./citations/10.md).
- The framework combines multi-teacher agreement, EMA teacher stabilization, token-level contrastive learning, feature matching, and divergence clipping [10](./citations/10.md).
- Across six benchmarks and six models from three families, the paper uses UniSD to study when self-distillation beats static imitation and how the components interact across tasks [10](./citations/10.md).
- The integrated UniSDfull pipeline reports +5.4 points over the base model and +2.8 points over the strongest baseline [10](./citations/10.md).

## Multimodal generation, video, and embodied learning

### HumanNet: Scaling Human-centric Video Learning to One Million Hours
https://arxiv.org/abs/2605.06747
- HumanNet is a one-million-hour human-centric video corpus spanning first-person and third-person perspectives, with fine-grained activities, human-object interactions, tool use, and long-horizon behaviors in diverse real-world environments [3](./citations/3.md).
- Beyond raw video, it includes interaction-centric annotations such as captions, motion descriptions, and hand/body signals for motion-aware and interaction-aware learning [3](./citations/3.md).
- The authors frame curation around human-centric filtering, temporal structuring, viewpoint diversity, and annotation enrichment as first-class design principles for embodied learning [3](./citations/3.md).
- In a controlled validation, continued training from Qwen VLM with 1000 hours of egocentric HumanNet video surpasses continued training with 100 hours of real-robot Magic Cobot data, suggesting egocentric human video may be a scalable and cost-effective substitute for robot data [3](./citations/3.md).

### 4DThinker: Thinking with 4D Imagery for Dynamic Spatial Understanding
https://arxiv.org/abs/2605.05997
- 4DThinker targets dynamic spatial reasoning from monocular video and argues that text-only reasoning is verbose and imprecise, while external geometric modules add inference complexity [5](./citations/5.md).
- The framework enables VLMs to “think with 4D” through dynamic latent mental imagery, i.e. internal simulation in continuous hidden space [5](./citations/5.md).
- It introduces a scalable annotation-free data generation pipeline, Dynamic-Imagery Fine-Tuning (DIFT) to supervise textual tokens and 4D latents, and 4D Reinforcement Learning (4DRL) with outcome-based rewards that restrict gradients to text tokens [5](./citations/5.md).
- The paper reports consistent gains over strong baselines across multiple dynamic spatial reasoning benchmarks and positions the work as a step toward intrinsic 4D reasoning in VLMs [5](./citations/5.md).

### Flow-OPD: On-Policy Distillation for Flow Matching Models
https://arxiv.org/abs/2605.08063
- Flow-OPD is presented as a unified post-training framework for flow-matching text-to-image models, aiming to fix reward sparsity, gradient interference, and the “seesaw effect” under multi-task alignment [6](./citations/6.md).
- The method uses a two-stage strategy: single-reward GRPO to train domain-specialized teachers, then a Flow-based Cold-Start plus on-policy sampling, task-routing labeling, and dense trajectory-level supervision to merge expertise into one student [6](./citations/6.md).
- It adds Manifold Anchor Regularization so a task-agnostic teacher can anchor generation to a high-quality manifold and reduce aesthetic degradation from RL-only alignment [6](./citations/6.md).
- Built on Stable Diffusion 3.5 Medium, the paper reports GenEval rising from 63 to 92 and OCR accuracy from 59 to 94, with roughly a 10-point overall improvement over vanilla GRPO [6](./citations/6.md).

### A^2RD: Agentic Autoregressive Diffusion for Long Video Consistency
https://arxiv.org/abs/2605.06924
- A^2RD targets long-video synthesis, where prior methods often drift semantically or collapse narratively over long horizons [7](./citations/7.md).
- It formulates generation as a closed-loop Retrieve--Synthesize--Refine--Update cycle with multimodal video memory, adaptive segment generation, and hierarchical test-time self-improvement [7](./citations/7.md).
- The authors also introduce LVBench-C, a benchmark with non-linear entity and environment transitions designed to stress long-horizon consistency [7](./citations/7.md).
- Across public benchmarks and LVBench-C over one- to ten-minute videos, the method reportedly improves consistency by up to 30% and narrative coherence by up to 20%, with human evaluation noting smoother motion and transitions [7](./citations/7.md).

## Retrieval, search, and long-context efficiency

### Beyond Retrieval: A Multitask Benchmark and Model for Code Search
https://arxiv.org/abs/2605.04615
- CoREB expands code search beyond first-stage retrieval to cover retrieval and reranking in production-like pipelines, addressing contamination, label noise, and binary relevance issues in existing benchmarks [4](./citations/4.md).
- The benchmark is built from counterfactually rewritten LiveCodeBench problems in five programming languages and includes timed releases with graded relevance judgments [4](./citations/4.md).
- The paper evaluates eleven embedding models and five rerankers on three tasks: text-to-code, code-to-text, and code-to-code [4](./citations/4.md).
- Reported findings include code-specialized embeddings outperforming general encoders on code-to-code retrieval, short keyword queries collapsing all models to near-zero nDCG@10, and the fine-tuned CoREB-Reranker being the first to show consistent gains across all three tasks [4](./citations/4.md).

### MISA: Mixture of Indexer Sparse Attention for Long-Context LLM Inference
https://arxiv.org/abs/2605.07363
- MISA is a drop-in replacement for DeepSeek Sparse Attention’s learned indexer, designed to reduce the cost of multi-head token scoring on long contexts [8](./citations/8.md).
- It treats indexer heads as a mixture-of-experts pool and uses a lightweight router over cheap block-level statistics to activate only a few heads per query [8](./citations/8.md).
- A hierarchical variant then enlarges the candidate set and reranks with the original DSA indexer to recover near-exact token selection [8](./citations/8.md).
- With eight active heads and no additional training, the method matches dense DSA on LongBench across DeepSeek-V3.2 and GLM-5, preserves Needle-in-a-Haystack heatmaps up to 128K tokens, recovers more than 92% of selected tokens, and yields a 3.82× kernel speedup on an NVIDIA H200 [8](./citations/8.md).

### HyperEyes: Dual-Grained Efficiency-Aware Reinforcement Learning for Parallel Multimodal Search Agents
https://arxiv.org/abs/2605.07177
- HyperEyes argues that multimodal search agents should search wider rather than longer by issuing multiple grounded queries concurrently within a round [9](./citations/9.md).
- The system fuses visual grounding and retrieval into one atomic action and trains in two stages: a parallel-amenable data synthesis pipeline plus Dual-Grained Efficiency-Aware RL [9](./citations/9.md).
- At the macro level, TRACE provides a trajectory-level reward with a monotonically tightened reference to suppress superfluous tool calls; at the micro level, on-policy distillation injects dense token-level corrections from an external teacher on failed rollouts [9](./citations/9.md).
- The paper introduces IMEB, a 300-instance benchmark that jointly evaluates search quality and efficiency, and reports that HyperEyes-30B beats the strongest open-source agent by 9.9% accuracy with 5.3× fewer tool-call rounds [9](./citations/9.md).

## Multimodal alignment, latent spaces, and generative modeling

### Anisotropic Modality Align
https://arxiv.org/abs/2605.07825
- AnisoAlign revisits the modality gap in shared multimodal contrastive spaces and argues the main obstacle is not a global shift but anisotropic residual structure concentrated along a small number of dominant directions [11](./citations/11.md).
- The paper’s principle is that effective alignment should match the target-modality distribution while preserving source semantic structure [11](./citations/11.md).
- The proposed AnisoAlign framework uses the target modality’s internal geometric prior and bounded correction on source representations to construct substitute target-modality representations for unpaired alignment [11](./citations/11.md).
- The authors say experiments validate the approach in both geometric diagnostics and text-only MLLM training [11](./citations/11.md).

### What Matters for Diffusion-Friendly Latent Manifold? Prior-Aligned Autoencoders for Latent Diffusion
https://arxiv.org/abs/2605.07915
- The paper studies what makes a latent space diffusion-friendly and identifies three properties: coherent spatial structure, local manifold continuity, and global manifold semantics [12](./citations/12.md).
- These geometric properties are reported to correlate more closely with downstream generation quality than reconstruction fidelity [12](./citations/12.md).
- Motivated by this, Prior-Aligned AutoEncoder (PAE) explicitly shapes the latent manifold using refined priors derived from VFMs and perturbation-based regularization [12](./citations/12.md).
- On ImageNet 256×256, PAE reportedly matches RAE with up to 13× faster convergence and reaches a new state-of-the-art gFID of 1.03 [12](./citations/12.md).

### STARFlow2: Bridging Language Models and Normalizing Flows for Unified Multimodal Generation
https://arxiv.org/abs/2605.08029
- STARFlow2 argues that autoregressive normalizing flows are a natural foundation for unified multimodal generation because they share the causal mask, KV-cache mechanism, and left-to-right structure of LLMs [13](./citations/13.md).
- The model is built on the Pretzel architecture, vertically interleaving a pretrained VLM stream with a TarFlow stream via residual skip connections under the same causal mask [13](./citations/13.md).
- The design also uses a deep-shallow flow and a unified FAE latent space to enable cache-friendly interleaved generation, with both text and visual outputs entering the KV-cache directly [13](./citations/13.md).
- The paper reports strong results on image generation and multimodal understanding benchmarks, supporting autoregressive flows as a viable multimodal modeling paradigm [13](./citations/13.md).

### Normalizing Trajectory Models
https://arxiv.org/abs/2605.08078
- NTM targets few-step generation for diffusion models while preserving exact likelihood, which distillation, consistency training, and adversarial methods usually sacrifice [14](./citations/14.md).
- Each reverse step is modeled as an expressive conditional normalizing flow with exact likelihood training, combining shallow invertible blocks per step with a deep parallel predictor across the trajectory [14](./citations/14.md).
- The model can be trained from scratch or initialized from pretrained flow-matching models, and its exact trajectory likelihood also enables self-distillation via a lightweight denoiser trained on the model’s own score [14](./citations/14.md).
- On text-to-image benchmarks, NTM matches or outperforms strong baselines in four sampling steps while retaining exact likelihood over the generative trajectory [14](./citations/14.md).

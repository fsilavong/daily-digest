# DeepMind publications digest

## Dynamic Reflections: Probing Video Representations with Text Alignment
https://deepmind.google/research/publications/193694/

- The paper studies video-text representation alignment as a probe for video encoders and language encoders, noting that prior work had mainly focused on image-text alignment and that the temporal setting for video was largely unexplored [1](./citations/1.md).
- It claims to conduct the first comprehensive study of video-text representation alignment, probing modern video and language encoders with a zero-shot setup over spatio-temporal data [1](./citations/1.md).
- A core finding is that alignment depends strongly on the richness of both the visual input at test time (static images versus multi-frame videos) and the text input (single caption versus a collection), especially for state-of-the-art video encoders [1](./citations/1.md).
- The authors propose parametric test-time scaling laws that capture this dependence and report that these laws show “remarkable predictive power” against empirical observations [1](./citations/1.md).
- They also report an initial correlation between semantic alignment and downstream performance on both semantic and non-semantic tasks, suggesting text alignment may be linked to general-purpose video representation and understanding [1](./citations/1.md).
- The paper additionally correlates temporal reasoning with cross-modal alignment, presenting it as a challenging test-bed for vision and language models [1](./citations/1.md).
- Venue: ICLR 2026 [1](./citations/1.md)

## Image Generators are Generalist Vision Learners
https://deepmind.google/research/publications/240658/

- This item argues that image generation training can play a role analogous to LLM pretraining, producing powerful and general visual representations that support strong zero-shot understanding behavior [2](./citations/2.md).
- The proposed model, Vision Banana, is built on Nano Banana Pro and is instruction-tuned on a mixture of its original training data plus a small amount of vision task data [2](./citations/2.md).
- The paper reframes vision tasks as image generation by parameterizing the output space of vision tasks as RGB images, which the authors say lets them better leverage the model’s generative capability [2](./citations/2.md).
- Vision Banana reportedly reaches state-of-the-art performance across a variety of 2D and 3D vision tasks, including segmentation tasks where it beats or rivals the Segment Anything series and metric depth estimation where it beats or rivals the Depth Anything series [2](./citations/2.md).
- The authors emphasize that these gains come from lightweight instruction-tuning without sacrificing the base model’s image generation capabilities [2](./citations/2.md).
- They frame the result as evidence for a paradigm shift: image generation pretraining as a generalist vision learner and image generation as a unified interface for vision tasks [2](./citations/2.md).
- The source links to arXiv:2604.20329 [2](./citations/2.md)

## The Abstraction Fallacy: Why AI Can Simulate But Not Instantiate Consciousness
https://deepmind.google/research/publications/231971/

- The item argues against computational functionalism, claiming that subjective experience does not emerge solely from abstract causal topology independent of physical substrate [3](./citations/3.md).
- It introduces the term “Abstraction Fallacy” for the claimed mistake of treating symbolic computation as an intrinsic physical process rather than a mapmaker-dependent description [3](./citations/3.md).
- The framework distinguishes simulation from instantiation: simulation is described as behavioral mimicry driven by vehicle causality, while instantiation is described as intrinsic physical constitution driven by content causality [3](./citations/3.md).
- The text claims this ontology shows algorithmic symbol manipulation cannot instantiate experience, and it says the argument does not depend on biological exclusivity [3](./citations/3.md).
- It further states that if an artificial system were ever conscious, that would be due to its physical constitution rather than its syntactic architecture [3](./citations/3.md).
- The source says this is a physically grounded refutation of computational functionalism intended to address uncertainty around AI consciousness and the AI welfare trap [3](./citations/3.md).
- Venue: PhilArchive [3](./citations/3.md)

## Simplicity and Complexity in Combinatorial Optimization
https://deepmind.google/research/publications/225507/

- The paper studies theoretical connections between Kolmogorov complexity, optima, and optimization in combinatorial optimization problems [4](./citations/4.md).
- It argues that extrema are more likely to have low complexity under certain circumstances, linking optima and complexity [4](./citations/4.md).
- It proposes that sampling candidate solutions according to algorithmic probability may be an effective optimization method [4](./citations/4.md).
- It also claims that coincidences in extrema across optimization problems are a priori more likely than under a purely random null model [4](./citations/4.md).
- The item is theory-oriented and does not describe benchmarks or empirical evaluation in the retrieved abstract [4](./citations/4.md).
- Venue: Entropy [4](./citations/4.md)

## Hybrid neural–cognitive models reveal how memory shapes human reward learning
https://deepmind.google/research/publications/94006/

- The paper addresses how past experience shapes future behavior in reward-guided learning, noting that standard reinforcement learning models use a small set of incrementally updated internal variables to summarize reward history and drive choice [5](./citations/5.md).
- The authors use a hybrid modeling approach that combines artificial neural networks with interpretable cognitive architectures, estimating a maximally general form for each algorithmic component and testing whether each component is necessary and sufficient [5](./citations/5.md).
- Applied to a large dataset of human reward-learning behavior, the models indicate that successful explanations require independent and flexible memory variables capable of tracking rich representations of the past [5](./citations/5.md).
- The retrieved abstract says the results question an entire class of popular RL models centered on incremental updating of scalar reward predictions [5](./citations/5.md).
- The item emphasizes a tradeoff between predictive accuracy and interpretability as part of the modeling approach [5](./citations/5.md).
- Venue: Nature Human Behaviour [5](./citations/5.md)
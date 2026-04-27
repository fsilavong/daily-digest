# BAIR Blog Digest

## Gradient-based Planning for World Models at Longer Horizons
https://bair.berkeley.edu/blog/2026/04/20/grasp/

- GRASP is presented as a gradient-based planner for learned world models that aims to make long-horizon planning practical by lifting the trajectory into virtual states, adding stochasticity to state iterates, and reshaping gradients so action gradients remain useful while brittle state-input gradients are avoided [1](./citations/1.md).
- The core planning reformulation is a collocation-style penalty over both states and actions, with fixed start state and goal at the terminal state; this keeps the same global minimizers as serial rollout planning while making the objective parallelizable across time [1](./citations/1.md).
- The post argues that deep world models make direct state optimization brittle because state Jacobians are adversarially sensitive off the data manifold, whereas action Jacobians are low-dimensional and more reliable to optimize through [1](./citations/1.md).
- GRASP combines three ingredients: Gaussian noise on virtual state updates for exploration, stop-gradient dynamics to suppress unstable state gradients, and dense goal shaping to keep earlier states aligned with the target; periodic “sync” steps briefly return to the true rollout objective to keep plans grounded [1](./citations/1.md).
- On Push-T, the post reports improved long-horizon planning success and speed across horizons 40 to 80, with GRASP often beating CEM, GD, and LatCo either in success rate or time to success [1](./citations/1.md).
- The authors frame the method as an initial step and call out open directions including diffusion-based world models, better optimizers/noising strategies, and integration into closed-loop planning or RL [1](./citations/1.md).

## Identifying Interactions at Scale for LLMs
https://bair.berkeley.edu/blog/2026/03/13/spex/

- The post argues that interpretability at scale must recover influential interactions, not just individual features or examples, because LLM behavior often depends on complex dependencies among features, training data, and internal components [2](./citations/2.md).
- SPEX (Spectral Explainer) recasts interaction discovery as sparse recovery under two assumptions emphasized in the post: sparsity of influential interactions and low-degreeness, meaning the important interactions involve only a small subset of features [2](./citations/2.md).
- ProxySPEX adds a hierarchy assumption and a softer search over interactions, and the post says it matches SPEX with about 10x fewer ablations [2](./citations/2.md).
- In feature attribution, the post says SPEX matches strong interaction methods on short inputs while retaining faithfulness as context grows to thousands of features; it also surfaces higher-order synergies that marginal methods miss, such as the interaction among repeated occurrences of "trolley" plus "pulling" and "lever" in a modified trolley-problem prompt [2](./citations/2.md).
- In data attribution, ProxySPEX is applied to a ResNet on CIFAR-10 to distinguish synergistic from redundant training-example interactions, with the post suggesting this can inform data selection that preserves synergies while removing redundancies [2](./citations/2.md).
- In component attribution, ProxySPEX is used on MMLU highschool-us-history, and the post claims a pruning strategy informed by these interactions can outperform competing methods and even improve target-task performance [2](./citations/2.md).
- The post closes by noting the framework extends interaction discovery from dozens to thousands of components and that unifying feature, data, and mechanistic perspectives remains open [2](./citations/2.md).

## Information-Driven Design of Imaging Systems
https://bair.berkeley.edu/blog/2026/01/10/information-driven-imaging/

- The post argues that imaging systems should be evaluated by information preserved in the measurements rather than by appearance or by downstream decoder-dependent metrics [3](./citations/3.md).
- The proposed framework estimates mutual information directly from noisy measurements by computing noise entropy analytically from known noise physics and learning measurement entropy with a probabilistic model such as a transformer, Gaussian process, Gaussian model, or PixelCNN [3](./citations/3.md).
- The post says the resulting estimate provides an upper bound on true information because model error can only overestimate, not underestimate, the information [3](./citations/3.md).
- Across color photography, radio astronomy, lensless imaging, and microscopy, the information metric is reported to predict downstream reconstruction or task performance, with higher information consistently corresponding to better results [3](./citations/3.md).
- IDEAL uses gradient ascent on the information estimate to optimize encoder parameters without training a decoder, and the post says it matches end-to-end optimization on color filter design while using less memory, less compute, and no task-specific decoder design [3](./citations/3.md).
- The approach is framed as applicable to other deterministic sensing systems with known noise characteristics, but it assumes deterministic encoding and known noise physics [3](./citations/3.md).

## RL without TD learning
https://bair.berkeley.edu/blog/2025/11/01/rl-without-td-learning/

- The post argues that scalable off-policy RL for long-horizon tasks should move beyond temporal-difference bootstrapping and instead use divide-and-conquer value learning [4](./citations/4.md).
- The proposed Transitive RL (TRL) framework uses deterministic goal-conditioned RL, the triangle inequality for shortest-path distance, and a transitive Bellman-style update that combines two shorter values through a subgoal midpoint [4](./citations/4.md).
- Because exact midpoint search is infeasible in large continuous state spaces, TRL restricts candidates to states that appear in the dataset trajectory and replaces a hard max with a soft choice via expectile regression [4](./citations/4.md).
- The post says TRL scales to difficult OGBench goal-conditioned tasks, including humanoidmaze and puzzle with 1B-sized datasets and horizons up to 3,000 steps, and achieves the best performance on most tasks [4](./citations/4.md).
- In a comparison against TD-n baselines, TRL matches the best tuned TD-n without requiring a choice of n, which the author presents as the main practical advantage of the divide-and-conquer paradigm [4](./citations/4.md).
- The main stated limitations are that the current formulation assumes deterministic dynamics and goal-conditioned RL, and extending it to regular reward-based RL and stochastic environments remains future work [4](./citations/4.md).

## What exactly does word2vec learn?
https://bair.berkeley.edu/blog/2025/09/01/qwem-word2vec-theory/

- The post claims that in a realistic small-initialization regime, word2vec learning reduces to unweighted least-squares matrix factorization, with the final representations given by PCA-like eigenvectors of a corpus-derived target matrix [5](./citations/5.md).
- The learning dynamics are described as discrete, sequential rank-incrementing steps: each step learns a new orthogonal concept subspace, and those subspaces do not rotate once learned [5](./citations/5.md).
- The target matrix is defined from co-occurrence and unigram probabilities, and the post says its top eigenvectors correspond to interpretable concepts such as celebrity biographies, government/municipal administration, and geography/cartography [5](./citations/5.md).
- The post says the theory is distribution-agnostic and makes no assumptions about the data distribution, but it does rely on a quartic approximation around the origin, hyperparameter constraints, tiny initialization, and vanishingly small gradient steps [5](./citations/5.md).
- As a coarse empirical check, the post reports analogy accuracy of 68% for word2vec, 66% for the approximate model, and 51% for PPMI [5](./citations/5.md).
- The post highlights that the theory provides one of the first closed-form descriptions of feature learning in a practical language model and helps explain the emergence of linear semantic structure [5](./citations/5.md).
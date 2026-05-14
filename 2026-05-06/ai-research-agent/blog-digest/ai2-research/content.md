# AllenAI Research Digest

## MolmoAct 2: An open foundation for robots that work in the real world
https://allenai.org/blog/molmoact2

- Ai2 says MolmoAct 2 is a substantial upgrade over MolmoAct: it is an open foundation model for robotics that outperforms capable proprietary robotics models on industry benchmarks, handles several real-world tasks out of the box without per-task fine-tuning, and runs up to 37x faster than its predecessor [1](./citations/1.md).
- The model is built on Molmo 2-ER, a specialized embodied-reasoning variant of Molmo 2 further trained on about 3M embodied-reasoning examples covering image-based pointing, object detection, abstract spatial reasoning, multi-image reasoning, and image/video spatial question answering [1](./citations/1.md).
- The action side combines Molmo 2-ER with a dedicated action expert that generates robot actions through flow matching, connected to the VLM through a KV-cache bridge; Ai2 also released an open action tokenizer, MolmoAct 2-FAST Tokenizer, as a fully open-source reimplementation trained on its data [1](./citations/1.md).
- Ai2 reports a major speed improvement: a single action call takes about 180 ms in the base model and 790 ms with adaptive depth reasoning, versus 6,700 ms for MolmoAct in the LIBERO benchmark environment on 1 NVIDIA H100 [1](./citations/1.md).
- The adaptive-depth variant, MolmoAct 2-Think, routes depth prediction only when expected to help and focuses depth tokens on regions with dynamic scene changes; Ai2 says this yields a 17% speedup versus full depth-token prediction while preserving deeper 3D reasoning [1](./citations/1.md).
- To train the model, Ai2 released the MolmoAct 2-Bimanual YAM dataset, a 700+ hour open-source bimanual tabletop manipulation dataset with over 30x the robot data used for MolmoAct; the accompanying text says it is the largest open-source bimanual robotics dataset ever released [1](./citations/1.md).
- Evaluation claims include 20.6% average success on MolmoBot, 0.443 on RoboEval, 87.1% average success in a Franka zero-shot test across 15 trials per task, 97.2% average success after post-training on LIBERO for MolmoAct 2, and 98.1% for MolmoAct 2-Think [1](./citations/1.md).
- Ai2 also says a third-party benchmark run by Cortex AI put MolmoAct 2 first among five policies with a 0.51 average score, ahead of OpenVLA-OFT, π0.5, Cosmos Policy, and X-VLA [1](./citations/1.md).
- The post frames the model as a practical deployment step for real-world robotics, including a reference hardware setup with two YAM arms and multiple Intel RealSense cameras, plus pilot use with Stanford's Cong Lab on a self-driving wetlab workflow [1](./citations/1.md).


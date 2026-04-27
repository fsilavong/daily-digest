# Ai2 research digest

## Introducing OlmoEarth embeddings: Custom embedding exports from OlmoEarth Studio for downstream analysis

Source: https://allenai.org/blog/olmoearth-embeddings

- OlmoEarth Studio now supports computing and exporting embedding vectors for Earth-observation data as Cloud-Optimized GeoTIFFs, using open-source OlmoEarth foundation models; the post says the source code, model weights, and paper are publicly available. [1](./citations/1.md)
- The workflow lets users choose area of interest, 1–12 monthly time spans, encoder variant, spatial resolution, and imagery source; exported vectors are stored as int8 values with one band per embedding dimension, and the post points to `dequantize_embeddings` for recovering floating-point vectors. [1](./citations/1.md)
- The post demonstrates four downstream uses: similarity search, few-shot segmentation, change detection, and PCA exploration. It gives a concrete segmentation example over Ca Mau, Vietnam: 60 labeled pixels, ESA WorldCover 2021 labels for mangrove/water/other, logistic regression on embeddings, and weighted F1 = 0.84. [1](./citations/1.md)
- For change detection, it compares monthly embeddings for September 2023 vs. September 2024 and reports that the Park Fire burn scar in Butte County, California lights up in cosine distance maps. [1](./citations/1.md)
- The post also names limitations: users should validate embeddings for their own use case, and output quality depends on input imagery; persistent cloud cover, atmospheric artifacts, or missing observations can affect the vectors. [1](./citations/1.md)

## Train separately, merge together: Modular post-training with mixture-of-experts

Source: https://allenai.org/blog/bar

- BAR (Branch-Adapt-Route) is a recipe for modular post-training: train independent domain experts through their own complete pipelines, then compose them into a unified mixture-of-experts model. The post positions this as a way to avoid retraining from scratch and to reduce catastrophic interference from adding new skills later. [2](./citations/2.md)
- The core technical mechanism is progressive unfreezing of shared parameters by stage. Mid-training keeps shared layers frozen; SFT unfreezes embeddings and the language modeling head; RLVR unfreezes all shared parameters, including attention. [2](./citations/2.md)
- The post gives a concrete tool-use result on BFCL: without unfreezing, the tool-use expert scored 20.3; with unfreezing, it reached 46.4. It also says domain-only SFT hurts general capabilities, so experts mix domain-specific and general SFT data. [2](./citations/2.md)
- On evaluation, BAR outperforms retraining with post-training only overall, 49.1 vs. 47.8, with reported gains in math (+7.8) and code (+4.7). The post also says naive dense-model averaging after mid-training fails badly, scoring 6.5 overall, while full retraining with mid-training remains the ceiling at 50.5. [2](./citations/2.md)
- A key limitation is that full retraining still performs best, but it requires full access to the original pretraining setup and is expensive. The post also notes BAR uses Olmo 2 as the base because the architecture was built around it. [2](./citations/2.md)

## Evaluating agents for scientific discovery

Source: https://allenai.org/blog/evaluating-scientific-discovery-agents

- The post argues that science-agent claims need benchmark evidence, and highlights two Ai2 benchmarks: ScienceWorld (2022) and DiscoveryWorld (2024). It frames them as tests of whether agents can actually do science, not just answer science questions. [3](./citations/3.md)
- DiscoveryWorld is described as an end-to-end scientific discovery benchmark on a fictional Planet X with 120 challenge tasks across eight topics, three difficulty levels, and parametric variations. Tasks require forming hypotheses, designing experiments, running them, and analyzing results across hundreds of in-game actions. [3](./citations/3.md)
- The post reports that top frontier models (as of early 2025) score in the low 80s on ScienceWorld, up from below 10% at launch, but still do not fully solve a 4th-grade science curriculum. It says DiscoveryWorld remains harder, with some leading systems completing only about 20% of tasks at higher difficulty, versus about 70% for human scientists with advanced degrees. [3](./citations/3.md)
- ScienceWorld is described as a text-based simulated lab with about 200 objects across 10 locations and 30 task types; agents must generalize across hundreds of randomized configurations. The post says models that did well on the ARC science exam still failed more than 90% of ScienceWorld when it launched. [3](./citations/3.md)
- The post does not present a model or new method; it is a benchmark-oriented overview. Its main caveat is that current agents still fall far short on long-horizon scientific discovery tasks, even as model capabilities improve. [3](./citations/3.md)

## Introducing WildDet3D: Open-world 3D detection from a single image

Source: https://allenai.org/blog/wilddet3d

- WildDet3D is an open model for monocular 3D detection that predicts 3D bounding boxes from a single RGB image and accepts text, point, and 2D-box prompts. The post emphasizes open-world use rather than a fixed category list. [4](./citations/4.md)
- The system combines a SAM3-based 2D detector, a frozen DINOv2 geometry backend with a trainable depth decoder, and a 3D detection head that fuses 2D detections with depth features through cross-attention. The geometry backend is modular, and the decoder uses spherical harmonic encodings of camera ray directions. [4](./citations/4.md)
- WildDet3D-Data contains over one million images with 3.7 million verified 3D annotations spanning more than 13K categories, including more than 100K human-annotated images. The post says the dataset was built from large 2D detection datasets using five 3D estimation methods, then refined, filtered, and selected with VLM and human review. [4](./citations/4.md)
- On Omni3D, the model reaches 34.2 AP with text prompts and 36.4 AP with oracle box prompts, improving on prior bests; with sparse depth at test time it rises to 41.6 AP and 45.8 AP. On zero-shot datasets, it reaches 40.3 ODS on Argoverse 2 and 48.9 ODS on ScanNet. [4](./citations/4.md)
- The post lists limitations: the model is still purely vision-based when only RGB is available, can be thrown off by workflow errors like scrolling too early, struggles with ambiguous instructions, and does not cover login or financial-transaction tasks. It also notes that server-side compute or further optimization is needed for real-time on-device use. [4](./citations/4.md)

## MolmoWeb: An open agent for automating web tasks

Source: https://allenai.org/blog/molmoweb

- MolmoWeb is an open visual web agent built on the Molmo 2 family, released in 4B and 8B parameter versions with weights, data, code, and evaluation tools. It operates by observing screenshots, then producing reasoning and browser actions such as clicking, typing, scrolling, tab changes, and sending messages. [5](./citations/5.md)
- The training data package, MolmoWebMix, combines 36K human task trajectories spanning more than 623K subtasks across 1.1K+ websites, synthetic trajectories from accessibility-tree agents, and GUI perception data including over 2.2M screenshot question-answer pairs from nearly 400 websites. [5](./citations/5.md)
- Benchmark coverage includes WebVoyager, Online-Mind2Web, DeepShop, and WebTailBench. The post reports the 8B model scores 78.2% on WebVoyager, 42.3% on DeepShop, and 49.5% on WebTailBench, and says it outperforms leading open-weight competitors. [5](./citations/5.md)
- It also reports strong grounding results on ScreenSpot and ScreenSpot v2, plus test-time scaling gains: 8B reaches 94.7% pass@4 on WebVoyager and 60.5% on Online-Mind2Web with multiple rollouts. [5](./citations/5.md)
- The post names limitations: screenshot text reading can fail, wrong early actions can derail an episode, ambiguous multi-constraint tasks are difficult, drag-and-drop and element-scoped scrolling remain challenging, and the model is not trained for login or financial-transaction tasks. [5](./citations/5.md)

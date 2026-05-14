# AllenAI Research Digest

## EMO: Pretraining mixture of experts for emergent modularity
- Source: https://allenai.org/blog/emo
- AllenAI presents EMO as a mixture-of-experts model pretrained end-to-end so modular structure emerges from the data rather than being manually imposed [1](./citations/1.md).
- The model is described as **1B-active, 14B-total-parameter**, with **8 active experts** out of **128 total experts**, trained on **1 trillion tokens** [1](./citations/1.md).
- The post says selective expert use can preserve near full-model performance while using only **12.5% of the total experts**; the reported drops are about **1% absolute at 25% of experts** and about **3% at 12.5%** [1](./citations/1.md).
- The core mechanism is to use **document boundaries as weak supervision** so tokens within a document share a restricted expert pool [1](./citations/1.md).
- AllenAI says EMO matches standard MoE performance on general-purpose benchmarks, and the release includes the full EMO model, a standard-MoE baseline, training code, and an interactive visualization [1](./citations/1.md).
- Limitation/caveat: the source only documents this one newly fetched item, so this digest is incomplete with respect to the requested latest 5-item check [1](./citations/1.md).

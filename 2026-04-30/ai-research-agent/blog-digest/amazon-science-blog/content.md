# Amazon Science Blog Digest

## Preserving the privacy of AI training data

- [Original URL](https://www.amazon.science/blog/preserving-the-privacy-of-ai-training-data)
- The post argues that ML systems trained on sensitive data can leak training information through membership inference, federated-learning gradient inversion, and attacks on shared federated-learning global models, and frames differential privacy plus secure multiparty computation as practical defenses [1](./citations/1.md).
- For membership inference, it describes a confidence-score threshold attack trained on a proxy model and says DP-SGD is the mitigation path discussed in the post [1](./citations/1.md).
- For federated learning, it describes gradient inversion against local updates and says private federated learning with secure multiparty computation / secret sharing is the mitigation discussed [1](./citations/1.md).
- The post reports 97% precision among records flagged as training data in a ResNet-50 / ImageNet-1k membership inference attack, and shows the expected privacy-accuracy tradeoff for DP-SGD on EMNIST: 78% test accuracy at ε=1.5, 82% at ε=3.0, versus 90% without DP [1](./citations/1.md).
- It also reports that a gradient inversion attack reconstructed single-sample batches exactly and 3 samples from a batch of 7, while the private federated-learning protocol prevented reconstruction of any training samples in the excerpted text [1](./citations/1.md).
- The post’s caveat is that smaller, domain-specific models on sensitive datasets are especially vulnerable, and that empirical understanding of differential privacy’s effective guarantees against attacks is still evolving [1](./citations/1.md).
- This matters because it gives a concrete, source-level map of privacy risks and defenses for sensitive-data training in healthcare, finance, and similar settings [1](./citations/1.md).
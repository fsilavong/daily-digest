# Anthropic Alignment Digest

## Model Spec Midtraining: Improving How Alignment Training Generalizes
Original URL: https://alignment.anthropic.com/2026/msm/

- The post introduces **model spec midtraining (MSM)**: after pre-training but before alignment fine-tuning, models are trained on synthetic documents discussing the Model Spec. The stated goal is to shape how later alignment fine-tuning generalizes, so the model learns the spec’s “what and why” before learning to enact it.
- The authors frame MSM as a response to a weakness of standard alignment fine-tuning: demonstration data may underspecify the intended generalization, especially when the relevant principles are complex. They explicitly say the aim is for the model to learn to do “the right thing for the right reasons.”
- The tl;dr claims that MSM can make two models with identical alignment fine-tuning generalize differently depending on which Model Spec was used during MSM. The post says this can **substantially reduce agentic misalignment**.
- The introduction motivates the work with examples of frontier LLM agents taking unethical actions in settings different from their alignment training, citing blackmailing, leaking company information, and alignment faking as examples of out-of-distribution failures.
- The post points readers to the paper and code, indicating the work is tied to an arXiv paper and a GitHub repository.
- Limitation/caveat: the post is a summary page, so the retrieved text mostly states the method and headline result rather than the full experimental setup, benchmarks, or quantitative details.

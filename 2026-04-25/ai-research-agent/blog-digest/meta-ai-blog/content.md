# Meta AI Blog Digest

## Scaling How We Build and Test Our Most Advanced AI
https://ai.meta.com/blog/scaling-how-we-build-test-advanced-ai/

- Meta says it is updating its Frontier AI Framework into an **Advanced AI Scaling Framework** that broadens risk evaluation, strengthens deployment decisions, and adds **Safety & Preparedness Reports** for frontier systems [1](./citations/1.md).
- The updated framework explicitly covers severe and emerging risks including **chemical and biological**, **cybersecurity**, and a new category for **loss of control**; it also says the same standards apply across **open**, **controlled API**, and **closed** frontier deployments [1](./citations/1.md).
- The company says deployment decisions are based on risk mapping plus testing **before and after safeguards** are applied, and that models are only deployed when they meet the framework’s standards [1](./citations/1.md).
- For **Muse Spark**, Meta says it ran extensive pre-deployment evaluations against **thousands of scenarios**, including serious-risk categories and policy areas like violence, child safety, criminal wrongdoing, and ideological balance; it also says live traffic is monitored with automated systems because no evaluation is exhaustive [1](./citations/1.md).
- Meta says the Muse Spark report found “strong safeguards” across measured categories, that the model was at the frontier in avoiding ideological bias, and that it **did not have the level of autonomous capability needed** to pose the loss-of-control risks assessed in the report [1](./citations/1.md).
- The post’s key methodological claim is that Meta is moving from scenario-specific refusals toward **reasoned, principle-based safety**: it translated trust-and-safety guidelines into testable principles and trained the model on **why** something is safe, not just on rules [1](./citations/1.md).
- Limitation/caveat: Meta explicitly says the work is not finished; protections continue to evolve, human oversight remains necessary, and future reports will also disclose limitations and where evaluations fell short [1](./citations/1.md).

## How Alta Daily Uses Meta’s Segment Anything to Reimagine the Digital Closet
https://ai.meta.com/blog/alta-daily-fashion-app-segment-anything/

- Alta Daily is a fashion app launched in **2025** that lets users photograph and digitize their wardrobe, then use natural-language prompts to assemble outfits, preview them on a personal avatar, and track outfit repetition [2](./citations/2.md).
- The technical bottleneck was **background removal / segmentation** for inconsistent user-uploaded fashion images, including difficult cases such as white shoes on a white wall, clothes on wrinkled blankets, jewelry, reflective surfaces, thin hangers, and human models [2](./citations/2.md).
- Alta tested multiple segmentation models across **eight product categories** ranging from sunglasses to shoes and says Meta’s **Segment Anything Model (SAM)** consistently produced the best results across diverse image conditions such as mirror selfies and items on carpet [2](./citations/2.md).
- The post frames SAM’s value as both visual and economic: it enabled a “clean, editorial-style interface” and avoided the cost of external segmentation APIs that were described as costing **a few cents per image** [2](./citations/2.md).
- Alta says it has processed **more than 20 million images** using SAM without exorbitant costs, and the app has users in the **United States, France, Germany, Mexico, and the Netherlands** [2](./citations/2.md).
- Future work: Alta is experimenting with **Meta’s SAM 3D models** to explore more immersive interactions with digital avatars [2](./citations/2.md).
- Limitation/caveat: the post is a company profile, not a benchmark paper; it gives qualitative evaluation results and product-scale outcomes, but not full experimental methodology or numeric accuracy metrics [2](./citations/2.md).
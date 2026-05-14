# AllenAI Research Digest

## Introducing AIMIP: The AI weather and climate model intercomparison project

- AIMIP is framed as a shared benchmark and dataset effort for evaluating AI climate models, motivated by the need for more rigorous common tests of accuracy and reliability in the field [1](./citations/1.md).
- The project brings together multiple modeling groups, including NVIDIA and Google Research, around a common experiment so models can be compared under the same setup and criteria [1](./citations/1.md).
- Phase 1 is limited to forecasting the global atmosphere from 1979–2024, with monthly and daily outputs, and models must be trained only on ERA5 historical observations from 1979–2014 [1](./citations/1.md).
- Ocean and sea ice are prescribed in Phase 1 so evaluation stays focused on the atmosphere; the post says later phases may extend to coupled modeling of ocean, sea ice, and other Earth-system components [1](./citations/1.md).
- The article says submitted AI models do very well on historical climate patterns, often outperforming a conventional physically based climate model, and the best models reduce time-averaged error in near-surface air temperature by a factor of 2 [1](./citations/1.md).
- A major caveat is generalization: models differ in how well they capture long-term warming, and they diverge strongly in an out-of-sample shock test, with some producing physically implausible results [1](./citations/1.md).

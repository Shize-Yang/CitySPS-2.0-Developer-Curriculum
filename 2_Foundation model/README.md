# 2 · Foundation Models

> 这一部分关注“如何让一个模型跨数据、跨任务、跨城市/区域泛化”，并同时参考其他复杂系统领域如何构建 Foundation Model。

## Urban / Spatio-temporal Foundation Models

- ⭐ **[Urban Foundation Models: A Survey](https://github.com/usail-hkust/Urban_Foundation_Model_Tutorial)** — *KDD 2024 Tutorial / Survey*  
  用于快速建立 Urban Foundation Model 的整体技术版图与任务谱系。

- ⭐ **[UniST: A Prompt-Empowered Universal Model for Urban Spatio-Temporal Prediction](https://arxiv.org/abs/2402.11838)** — *KDD 2024*  
  通过大规模时空预训练与知识引导 prompt，实现跨场景 few-shot / zero-shot 预测。  
  [Code](https://github.com/tsinghua-fib-lab/UniST)

- ⭐ **[BIGCity: A Universal Spatiotemporal Model for Unified Trajectory and Traffic State Data Analysis](https://arxiv.org/abs/2412.00953)** — *ICDE 2025*  
  用统一 ST-unit 同时建模轨迹与交通状态，是 CitySPS 做统一 mobility representation 的重要参考。  
  [Code](https://github.com/bigscity/BIGCity)

- **[OpenCity: Open Spatio-Temporal Foundation Models for Traffic Prediction](https://arxiv.org/abs/2408.10269)** — *2024*  
  关注跨城市、跨区域的 zero-shot traffic prediction 与 scaling。  
  [Code](https://github.com/HKUDS/OpenCity)

- **[UrbanCLIP: Learning Text-enhanced Urban Region Profiling with Contrastive Language-Image Pretraining from the Web](https://github.com/siruzhong/WWW24-UrbanCLIP)** — *WWW 2024*  
  文本—遥感/图像对齐的城市区域表征学习，为 CitySPS 的多模态 Urban Encoder 提供参考。

- **[UrbanGPT: Spatio-Temporal Large Language Models](https://arxiv.org/abs/2403.00813)** — *KDD 2024*  
  将时空依赖编码器与 instruction tuning 结合，探索 LLM 对时空任务的迁移与 zero-shot 能力。  
  [Code](https://github.com/HKUDS/UrbanGPT) · [Project](https://urban-gpt.github.io/)

- **[Diffusion Transformers as Open-World Spatiotemporal Foundation Models (UrbanDiT)](https://arxiv.org/abs/2411.12164)** — *NeurIPS 2025*  
  用 Diffusion Transformer 统一 grid / graph 数据与多种时空任务，强调 open-world generalization。  
  [Code](https://github.com/tsinghua-fib-lab/UrbanDiT)

- **[UrbanFM: Scaling Urban Spatio-Temporal Foundation Models](https://arxiv.org/abs/2602.20677)** — *2026*  
  从 heterogeneity、correlation、dynamics 三个维度讨论城市时空基础模型的 scaling。

## Foundation Models from Other Complex Domains

这些工作不是城市模型，但用于回答一个关键问题：**复杂、多模态、多任务系统如何形成统一、可迁移的表示？**

- **[A foundation model for the Earth system](https://doi.org/10.1038/s41586-025-09005-y)** — *Nature 2025*  
  Aurora 通过海量、多源地球系统数据预训练，在天气、空气质量、海浪和热带气旋等任务上统一迁移。

- **[A generalizable foundation model for analysis of human brain MRI](https://doi.org/10.1038/s41593-026-02202-6)** — *Nature Neuroscience 2026*  
  BrainIAC 展示了异构数据、self-supervised pretraining 与多下游任务适配的通用范式。  
  [Code](https://github.com/AIM-KannLab/BrainIAC)

- **[GaitDynamics: a generative foundation model for analyzing human walking and running](https://doi.org/10.1038/s41551-025-01565-8)** — *Nature Biomedical Engineering 2026*  
  一个生成式 foundation model 如何用灵活输入/输出覆盖不同动力学任务。  
  [Code](https://github.com/stanfordnmbl/GaitDynamics)

- **[Merlin: a computed tomography vision–language foundation model and dataset](https://doi.org/10.1038/s41586-026-10181-8)** — *Nature 2026*  
  3D 影像、结构化 EHR 与文本报告的多模态预训练范例。  
  [Code](https://github.com/StanfordMIMI/Merlin)

## Representation / Tokenization

- **[UniFlow: A Unified Pixel Flow Tokenizer for Visual Understanding and Generation](https://arxiv.org/abs/2510.10575)** — *ICLR 2026*  
  讨论如何用统一 tokenizer 同时服务理解与生成，对 CitySPS 的统一城市 token / latent representation 很有启发。  
  [Code](https://github.com/ZhengrongYue/UniFlow)

## What to compare

`Input representation` · `Pretraining objective` · `Backbone` · `Task unification` · `Cross-city generalization` · `Zero/Few-shot` · `Scaling` · `Multimodal alignment` · `Tokenizer / latent space`

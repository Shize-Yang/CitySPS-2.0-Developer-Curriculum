# 2 · Foundation Models

> 这一部分关注：**如何让一个模型跨数据、跨任务、跨城市/区域泛化，并形成可复用的城市表征与生成能力？**

**Legend:** ⭐ = Must Read · `[Paper]` = 论文 · `[Code]` = 代码 · `[Project]` = 项目主页 · `[Data]` = 数据/权重

## Foundations

- ⭐ **[On the Opportunities and Risks of Foundation Models](https://arxiv.org/abs/2108.07258)** — *Stanford CRFM, 2021*  
  Foundation Model 概念与研究议程的代表性文本。对 CitySPS 最重要的不是“大模型”三个字，而是 **pretraining → adaptation → cross-task generalization → emergent capability → system-level risk** 这套完整范式。  
  [Report](https://crfm.stanford.edu/report)

## ⭐ Urban / Spatio-temporal Core Reading

| Work | Venue / Year | Why it matters for CitySPS | Resources |
| --- | --- | --- | --- |
| ⭐ **Urban Foundation Models: A Survey / Tutorial** | KDD 2024 Tutorial | 快速建立 Urban Foundation Model 的任务谱系、数据模态与技术版图，是本节最适合作为入口的综述性材料。 | [Project](https://github.com/usail-hkust/Urban_Foundation_Model_Tutorial) |
| ⭐ **UniST: A Prompt-Empowered Universal Model for Urban Spatio-Temporal Prediction** | KDD 2024 | 大规模时空预训练 + prompt adaptation，实现跨场景 few-shot / zero-shot；是“一个模型覆盖多个城市时空任务”的直接参考。 | [Paper](https://arxiv.org/abs/2402.11838) · [Code](https://github.com/tsinghua-fib-lab/UniST) |
| ⭐ **BIGCity: A Universal Spatiotemporal Model for Unified Trajectory and Traffic State Data Analysis** | ICDE 2025 | 用统一 ST-unit 同时处理 trajectory 与 traffic state，对 CitySPS 统一 mobility representation 极具参考价值。 | [Paper](https://arxiv.org/abs/2412.00953) · [Code](https://github.com/bigscity/BIGCity) |
| ⭐ **OpenCity: Open Spatio-Temporal Foundation Models for Traffic Prediction** | arXiv 2024 | 强调跨城市、跨区域 zero-shot 交通预测与 scaling，适合研究“城市间迁移究竟能走多远”。 | [Paper](https://arxiv.org/abs/2408.10269) · [Code](https://github.com/HKUDS/OpenCity) · [Data](https://huggingface.co/datasets/hkuds/OpenCity-dataset/tree/main) · [Weights](https://huggingface.co/hkuds/OpenCity-Plus) |
| ⭐ **UrbanCLIP: Learning Text-enhanced Urban Region Profiling with Contrastive Language-Image Pretraining from the Web** | WWW 2024 | 用文本—视觉对齐学习城市区域表征，为 CitySPS 的遥感、街景、POI、文本等多模态 Urban Encoder 提供范式。 | [Paper + Code](https://github.com/siruzhong/WWW24-UrbanCLIP) |
| **UrbanGPT: Spatio-Temporal Large Language Models** | KDD 2024 | 把时空编码器与 instruction tuning / LLM 结合，探索语言模型承接时空数值任务的路径。 | [Paper](https://arxiv.org/abs/2403.00813) · [Code](https://github.com/HKUDS/UrbanGPT) · [Project](https://urban-gpt.github.io/) |
| ⭐ **Diffusion Transformers as Open-World Spatiotemporal Foundation Models (UrbanDiT)** | arXiv 2024 | 用 Diffusion Transformer 统一多类时空输入/输出和 open-world 任务，是“预测 + 生成 + 多任务统一”路线的重要参考。 | [Paper](https://arxiv.org/abs/2411.12164) · [Code](https://github.com/tsinghua-fib-lab/UrbanDiT) |
| ⭐ **UrbanFM: Scaling Urban Spatio-Temporal Foundation Models** | arXiv 2026 | 进一步把 urban FM 推到 scaling 问题：大规模 WorldST 预训练语料与 EvalST 评估体系对 CitySPS 未来数据规模、benchmark 和 scaling law 都很重要。 | [Paper](https://arxiv.org/abs/2602.20677) |

## General Time-series Foundation Models

这些工作并非城市专用，但在 **统一时间序列 tokenization、patching、pretraining objective、zero-shot forecasting、长上下文与大规模预训练** 上非常值得借鉴。

- ⭐ **[MOMENT: A Family of Open Time-series Foundation Models](https://arxiv.org/abs/2402.03885)** — *ICML 2024*  
  将 forecasting、classification、anomaly detection、imputation 等任务放入统一预训练框架，是“跨任务时间序列 FM”很好的工程基线。  
  [Code](https://github.com/moment-timeseries-foundation-model/moment)

- **[A Decoder-only Foundation Model for Time-series Forecasting (TimesFM)](https://arxiv.org/abs/2310.10688)** — *ICML 2024*  
  研究 decoder-only Transformer 如何通过大规模时间序列预训练实现 zero-shot forecasting。  
  [Code](https://github.com/google-research/timesfm)

- **[Chronos: Learning the Language of Time Series](https://arxiv.org/abs/2403.07815)** — *2024*  
  将连续时间序列量化成离散 token 并借鉴 language modeling，是 CitySPS 设计统一 numerical token / trajectory token 的典型参考。  
  [Code](https://github.com/amazon-science/chronos-forecasting)

## Representation / Tokenization / Understanding & Generation

- ⭐ **[UniFlow: A Unified Pixel Flow Tokenizer for Visual Understanding and Generation](https://arxiv.org/abs/2510.10575)** — *ICLR 2026*  
  讨论统一 tokenizer 如何同时支持理解和生成。CitySPS 的对应问题是：**能否设计一个 urban tokenizer / latent space，同时服务预测、生成、检索、模拟和 Agent/World Model？**  
  [Code](https://github.com/ZhengrongYue/UniFlow)

## Cross-domain Foundation Models Worth Studying

这些工作不属于城市领域，但用于观察其他复杂系统如何处理 **多模态、多尺度、异构观测和多下游任务**。

- **[A foundation model for the Earth system](https://doi.org/10.1038/s41586-025-09005-y)** — *Nature 2025*  
  Aurora 展示了在超大规模、多源地球系统数据上预训练并迁移到天气、空气质量、海浪、热带气旋等任务的路径。

- **[A generalizable foundation model for analysis of human brain MRI](https://doi.org/10.1038/s41593-026-02202-6)** — *Nature Neuroscience 2026*  
  可参考异构数据 self-supervised pretraining 与多下游任务适配。  
  [Code](https://github.com/AIM-KannLab/BrainIAC)

- **[GaitDynamics: a generative foundation model for analyzing human walking and running](https://doi.org/10.1038/s41551-025-01565-8)** — *Nature Biomedical Engineering, 2026*  
  典型的生成式动力学基础模型：灵活输入输出、多任务、连续动态，和 CitySPS mobility / behavior model 有较强方法同构性。  
  [Code](https://github.com/stanfordnmbl/GaitDynamics)

## Core design axes for CitySPS

| Axis | Key question |
| --- | --- |
| **Data scaling** | 预训练数据到底应该按城市数、时间长度、主体数、模态数还是 token 数来规模化？ |
| **Urban tokenizer / representation** | Grid、graph、trajectory、POI、text、image、policy 如何进入统一表示空间？ |
| **Pretraining objective** | Masked modeling、next-state prediction、contrastive、diffusion、autoregressive、multi-task 哪种最适合城市系统？ |
| **Task unification** | 预测、生成、分类、检索、模拟是否真的能由一个 backbone 统一？ |
| **Cross-city transfer** | zero-shot / few-shot 的有效性如何随城市差异、空间尺度和数据缺失变化？ |
| **Multimodal alignment** | 视觉、语言、空间、网络和行为数据如何对齐，而不丢失数值精度？ |
| **Generative capability** | Foundation Model 是只做 encoder，还是同时承担城市未来状态/行为生成？ |
| **Scaling law** | 参数、数据、任务和城市数量增加时性能是否存在可预测 scaling？ |
| **Evaluation** | 不能只看单一预测误差，还要看跨任务、跨城、OOD、zero-shot、校准和规律保持。 |

## CitySPS question

最终需要回答的不是“要不要做一个更大的 UrbanFM”，而是：

> **什么样的统一城市表征和预训练机制，能够成为 Agent、Mobility Model、Urban World Model 和 Planning Agent 共同使用的基础状态空间？**

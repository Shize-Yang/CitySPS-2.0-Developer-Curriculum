<div align="center">

# CitySPS 2.0 Handbook

**A curated research handbook for next-generation urban system modeling.**  
**面向 CitySPS 2.0 的核心文献、综述、方法、系统与学习资源索引。**

[Traditional Models](./0_CitySPS1.0%20与传统模型/) · [Reviews & Perspectives](./1_Reviews%20&%20Perspectives/) · [Urban Science](./2_Urban%20Science/) · [Foundation Models](./3_Foundation%20model/) · [Agent Systems](./4_Agent%20system/) · [World Models](./5_World%20model/) · [Learning Resources](./6_Learning%20Resources/)

</div>

---

## Contents

| Section | Focus |
| --- | --- |
| **[0 · CitySPS 1.0 & Traditional Models](./0_CitySPS1.0%20与传统模型/)** | CitySPS 系列工作、LUTI、microsimulation、综合城市模型、校准与政策模拟 |
| **[1 · Reviews & Perspectives](./1_Reviews%20&%20Perspectives/)** | 城市预测、城市模型演进、mobility、Foundation Model、Agent、World Model 的综述与研究议程 |
| **[2 · Urban Science](./2_Urban%20Science/)** | 城市复杂系统、标度、网络、空间相互作用、人群移动与城市演化 |
| **[3 · Foundation Models](./3_Foundation%20model/)** | 城市/时空基础模型、统一表征、多模态预训练、zero-shot 与 scaling |
| **[4 · Agent Systems](./4_Agent%20system/)** | LLM Agent、Generative Agents、社会模拟、城市行为、GIS 与规划 Agent |
| **[5 · World Models](./5_World%20model/)** | Learned dynamics、JEPA、latent imagination、planning、interactive world models 与 Urban World Model |
| **[6 · Learning Resources](./6_Learning%20Resources/)** | Stanford / Berkeley / Hugging Face 课程，以及 nanobot、MiniMind 等可读代码项目 |

> **Legend:** ⭐ = **Must Read** · `[Paper]` = 论文 · `[Code]` = 代码 · `[Project]` = 项目主页 · `[Data]` = 数据/模型

## ⭐ CitySPS Core Reading — Starter Kit

第一次进入仓库，建议先从下面这些工作建立完整的研究坐标，而不是只沿着某一个 AI 分支阅读。

| Area | Starter reading | Why start here |
| --- | --- | --- |
| **Urban Modelling Reviews** | [Predicting urban futures](https://doi.org/10.1177/03091325261472137) · [The Future of Urban Modelling: From BLV to AI](https://doi.org/10.1007/s11067-024-09658-8) | 先理解城市预测从机制模型走向算法预测时，解释、因果、政策控制和不确定性发生了什么变化。 |
| **Traditional Urban Models** | [UrbanSim](https://doi.org/10.1080/01944360208976274) · [MATSim](https://matsim.org/the-book/) · [POLARIS](https://polaris.taps.anl.gov/) | 理解城市状态、主体、反馈、政策情景和 operational simulation 在 AI 之前是如何被组织起来的。 |
| **Urban Science** | [Growth, Innovation, Scaling, and the Pace of Life in Cities](https://doi.org/10.1073/pnas.0610172104) · [Urban Growth and the Emergent Statistics of Cities](https://doi.org/10.1126/sciadv.aat8812) | 建立宏观城市规律与动态机制的基本坐标，并作为 CitySPS 的结构性验证来源。 |
| **Human Mobility** | [Understanding Individual Human Mobility Patterns](https://doi.org/10.1038/nature06958) · [Human Mobility: Models and Applications](https://doi.org/10.1016/j.physrep.2018.01.001) | 理解个体轨迹、群体流、机制模型和数据驱动 mobility modeling 的核心脉络。 |
| **Urban / ST Foundation Models** | [UniST](https://arxiv.org/abs/2402.11838) · [BIGCity](https://arxiv.org/abs/2412.00953) · [UrbanDiT](https://arxiv.org/abs/2411.12164) | 从城市时空预训练走到 trajectory/traffic 统一建模和预测/生成统一。 |
| **Geospatial Foundation Models** | [Prithvi-EO-2.0](https://github.com/NASA-IMPACT/Prithvi-EO-2.0) · [TerraMind](https://arxiv.org/abs/2504.11171) | 理解遥感、位置/时间 metadata 与多模态 Earth Observation 如何进入 foundation model。 |
| **Urban Representation** | [UrbanCLIP](https://github.com/siruzhong/WWW24-UrbanCLIP) · [OpenCity](https://arxiv.org/abs/2408.10269) | 理解多模态城市表征、跨城市迁移与 zero-shot 能力。 |
| **Agent Foundations** | [ReAct](https://arxiv.org/abs/2210.03629) · [Generative Agents](https://arxiv.org/abs/2304.03442) | 掌握 modern agent loop 与 memory–reflection–planning 的两个基础范式。 |
| **Large-scale Social Agents** | [AgentSociety 2](https://arxiv.org/abs/2607.11895) · [OASIS](https://arxiv.org/abs/2411.11581) · [YuLan-OneSim](https://arxiv.org/abs/2505.07581) | 观察一万到百万量级 generative-agent simulation 的系统结构、扩展方式与社会实验范式。 |
| **Urban Mobility Agents** | [GATSim](https://arxiv.org/abs/2506.23306) | 直接观察 mobility foundation model、认知 agent 与交通仿真器如何结合。 |
| **World Model Foundations** | [World Models](https://arxiv.org/abs/1803.10122) · [DreamerV3](https://doi.org/10.1038/s41586-025-08744-2) | 理解 representation → dynamics → imagination → decision 的核心链条。 |
| **Predictive World Models / JEPA** | [V-JEPA 2](https://arxiv.org/abs/2506.09985) · [V-JEPA 2.1](https://arxiv.org/abs/2603.14482) | 理解不重建全部观测、而在 latent representation 中预测有意义未来状态的另一条 world-model 路线。 |
| **Interactive / Physical World Models** | [Genie](https://arxiv.org/abs/2402.15391) · [Think2Drive](https://www.ecva.net/papers/eccv_2024/papers_ECCV/html/6129_ECCV_2024_paper.php) · [Cosmos](https://arxiv.org/abs/2501.03575) | 观察 world model 如何从 latent control 走向交互生成、自动驾驶和 Physical AI。 |
| **Engineering / Learning** | [Stanford CS336](https://cs336.stanford.edu/) · [Stanford CS329Z](https://cs329z.stanford.edu/) · [Stanford CS224V](https://web.stanford.edu/class/cs224v/) · [Berkeley CS285](https://rail.eecs.berkeley.edu/deeprlcourse/) | 从 Foundation Model 训练、Agent engineering 到 model-based RL 建立可实现的工程基础。 |

## 📊 Comparison Matrices

为了让 Handbook 真正支持技术选型，而不只是“收藏论文”，五个核心模块都建立了统一比较表：

- **[Traditional Urban Models Matrix](./0_CitySPS1.0%20与传统模型/Comparison%20Matrix.md)** — state / actor / dynamics / intervention / validation / open-source system。
- **[Urban Science Matrix](./2_Urban%20Science/Comparison%20Matrix.md)** — scale / variables / law / mechanism / data / CitySPS constraint。
- **[Foundation Models Matrix](./3_Foundation%20model/Comparison%20Matrix.md)** — data / representation / pretraining objective / backbone / tasks / transfer / resources。
- **[Agent Systems Matrix](./4_Agent%20system/Comparison%20Matrix.md)** — scale / memory / environment / actions / grounding / intervention / reproducibility。
- **[World Models Matrix](./5_World%20model/Comparison%20Matrix.md)** — state / action / dynamics / planning / horizon / uncertainty / CitySPS adaptation。

## 🛠️ Learning & Reproduction

课程和小型开源项目只作为研发辅助资源：

- **Courses:** Stanford CS336、CS224V Agentic AI、CS329Z Engineering AI Agents、Berkeley CS285、Hugging Face Agents Course、Stanford CS25、CS329X。
- **Hands-on Projects:** [nanobot](https://github.com/HKUDS/nanobot)、[MiniMind](https://github.com/jingyaogong/minimind)、[nanochat](https://github.com/karpathy/nanochat)、[smolagents](https://github.com/huggingface/smolagents)。

详见 **[6 · Learning Resources](./6_Learning%20Resources/)**。

## How entries are organized

各主题页优先采用 research-list / awesome-list 风格：

> ⭐ **Paper / System** — *Venue, Year*  
> 一句话说明它解决什么问题，以及为什么值得 CitySPS 参考。  
> `[Paper]` · `[Code]` · `[Project]` · `[Data]`

README 维护的是**可检索、可点击、带研究脉络并能支持技术决策的知识地图**。PDF 可以作为资料副本存在，但不作为页面的主要组织方式。

<div align="center">

# CitySPS 2.0 Handbook

**A curated research handbook for next-generation urban system modeling.**  
**面向 CitySPS 2.0 的核心文献、方法、系统与学习资源索引。**

[Traditional Models](./0_CitySPS1.0%20与传统模型/) · [Urban Science](./1_Urban%20Science/) · [Foundation Models](./2_Foundation%20model/) · [Agent Systems](./3_Agent%20system/) · [World Models](./4_World%20model/) · [Courses](./5_Courses/)

</div>

---

## Contents

| Section | Focus |
| --- | --- |
| **[0 · CitySPS 1.0 & Traditional Models](./0_CitySPS1.0%20与传统模型/)** | CitySPS 系列工作、LUTI、microsimulation、综合城市模型、校准与政策模拟 |
| **[1 · Urban Science](./1_Urban%20Science/)** | 城市复杂系统、标度、网络、空间相互作用、人群移动与城市演化 |
| **[2 · Foundation Models](./2_Foundation%20model/)** | 城市/时空基础模型、统一表征、多模态预训练、zero-shot 与 scaling |
| **[3 · Agent Systems](./3_Agent%20system/)** | LLM Agent、Generative Agents、社会模拟、城市行为、GIS 与规划 Agent |
| **[4 · World Models](./4_World%20model/)** | Learned dynamics、latent imagination、planning、interactive world models 与 Urban World Model |
| **[5 · Courses](./5_Courses/)** | 与 CitySPS 方法研发直接相关的高质量课程与讲义 |

> **Legend:** ⭐ = **Must Read** · `[Paper]` = 论文 · `[Code]` = 代码 · `[Project]` = 项目主页 · `[Data]` = 数据/模型

## ⭐ CitySPS Core Reading — Starter Kit

第一次进入仓库，建议先从下面这些工作建立完整的研究坐标，而不是只沿着某一个 AI 分支阅读。

| Area | Starter reading | Why start here |
| --- | --- | --- |
| **Traditional Urban Models** | [UrbanSim](https://doi.org/10.1080/01944360208976274) · [MATSim](https://matsim.org/the-book/) | 理解城市状态、主体、反馈、政策情景和 operational simulation 在 AI 之前是如何被组织起来的。 |
| **Urban Science** | [Growth, Innovation, Scaling, and the Pace of Life in Cities](https://doi.org/10.1073/pnas.0610172104) · [Urban Growth and the Emergent Statistics of Cities](https://doi.org/10.1126/sciadv.aat8812) | 建立宏观城市规律与动态机制的基本坐标，并作为 CitySPS 的结构性验证来源。 |
| **Human Mobility** | [Understanding Individual Human Mobility Patterns](https://doi.org/10.1038/nature06958) · [Human Mobility: Models and Applications](https://doi.org/10.1016/j.physrep.2018.01.001) | 理解个体轨迹、群体流、机制模型和数据驱动 mobility modeling 的核心脉络。 |
| **Foundation Models** | [On the Opportunities and Risks of Foundation Models](https://arxiv.org/abs/2108.07258) · [UniST](https://arxiv.org/abs/2402.11838) · [BIGCity](https://arxiv.org/abs/2412.00953) | 从 Foundation Model 总体范式走到城市时空统一建模。 |
| **Urban Representation** | [UrbanCLIP](https://github.com/siruzhong/WWW24-UrbanCLIP) · [UrbanDiT](https://arxiv.org/abs/2411.12164) | 理解多模态城市表征以及预测/生成统一的可能性。 |
| **Agent Foundations** | [ReAct](https://arxiv.org/abs/2210.03629) · [Generative Agents](https://arxiv.org/abs/2304.03442) | 掌握 modern agent loop 与 memory–reflection–planning 的两个基础范式。 |
| **Urban / Social Agents** | [AgentSociety 2](https://arxiv.org/abs/2607.11895) · [GATSim](https://arxiv.org/abs/2506.23306) | 直接观察大规模社会主体模拟与城市 mobility agent 如何落地。 |
| **World Model Foundations** | [World Models](https://arxiv.org/abs/1803.10122) · [DreamerV3](https://doi.org/10.1038/s41586-025-08744-2) | 理解 representation → dynamics → imagination → decision 的核心链条。 |
| **Interactive / Physical World Models** | [Genie](https://arxiv.org/abs/2402.15391) · [Think2Drive](https://www.ecva.net/papers/eccv_2024/papers_ECCV/html/6129_ECCV_2024_paper.php) · [Cosmos](https://arxiv.org/abs/2501.03575) | 观察 world model 如何从 latent control 走向交互生成、自动驾驶和 Physical AI。 |
| **Engineering** | [Stanford CS336: Language Modeling from Scratch](https://cs336.stanford.edu/) | 从数据、tokenization、模型、训练到系统实现理解现代 Foundation Model 工程。 |

## How entries are organized

各主题页优先采用 research-list / awesome-list 风格：

> ⭐ **Paper / System** — *Venue, Year*  
> 一句话说明它解决什么问题，以及为什么值得 CitySPS 参考。  
> `[Paper]` · `[Code]` · `[Project]` · `[Data]`

README 维护的是**可检索、可点击、带研究脉络的知识地图**。PDF 可以作为资料副本存在，但不作为页面的主要组织方式。

# 0 · CitySPS 1.0 & Traditional Urban Models

> 这一部分回答两个问题：**CitySPS 从哪里来？传统城市系统模型已经解决了什么、还没有解决什么？**

**Legend:** ⭐ = Must Read · `[Paper]` = 论文 · `[Code]` = 代码 · `[Project]` = 项目主页 · `[Docs]` = 文档

## ⭐ Must Read

| Work | Venue / Year | Why it matters for CitySPS | Resources |
| --- | --- | --- | --- |
| ⭐ **CitySPS / 城市复杂系统模拟技术** | 赵鹏军, 2023 | CitySPS 1.0 的直接起点。应重点理解其城市要素推演、决策模拟、状态监测、预警与数据服务，以及已有模块之间如何耦合。 | [Project](https://citysps.net.cn/) |
| ⭐ **UrbanSim: Modeling Urban Development for Land Use, Transportation, and Environmental Planning** | JAPA, 2002 | 经典 operational urban model：把土地开发、家庭/就业区位与政策情景放入可执行模拟框架，是 CitySPS 进行长期土地利用—交通联动的核心参照。 | [Paper](https://doi.org/10.1080/01944360208976274) · [Code](https://github.com/UDST/urbansim) · [Project](https://www.urbansim.com/) |
| ⭐ **Microsimulating Urban Systems (ILUTE)** | CEUS, 2004 | 以个体、家庭、企业等微观主体模拟整个都市区长期演化，代表“综合城市系统 + microsimulation + agent”的经典路线。 | [Paper](https://doi.org/10.1016/S0198-9715(02)00044-3) |
| ⭐ **The Multi-Agent Transport Simulation MATSim** | Book / Platform, 2016– | 大规模 agent-based transport simulation 的工程标杆：活动链、网络加载、迭代 replanning、政策实验均值得 CitySPS 行为层借鉴。 | [Book](https://matsim.org/the-book/) · [Code](https://github.com/matsim-org/matsim-libs) · [Docs](https://www.matsim.org/docs/) |
| ⭐ **SimMobility Short-Term: An Integrated Microscopic Mobility Simulator** | TRR, 2017 | 将秒级交通运行、日活动模式与更长期城市过程连接到统一多尺度平台；对 CitySPS 的 multi-timescale system architecture 很直接。 | [Paper](https://doi.org/10.3141/2622-02) · [Project](https://mfc.mit.edu/simmobility/) |
| ⭐ **A New Framework for Very Large-Scale Urban Modelling (QUANT)** | Urban Studies, 2021 | 将传统 LUTI 扩展到超大规模空间系统，并强调交互式 “what-if” 场景，是 CitySPS 政策干预/快速推演的重要前身。 | [Paper](https://doi.org/10.1177/0042098020982252) |
| ⭐ **HARMONY Model Suite** | PLOS ONE, 2025 | 把人口、区域经济、LUTI、货运和网络仿真组织成模块化战略—战术—运行三级模型，是“城市模型系统工程”很好的近期样本。 | [Paper](https://doi.org/10.1371/journal.pone.0330067) · [Project](https://harmony-h2020.eu/model-suite/) · [Docs](https://github.com/MobyX-HARMONY/HARMONY-Platform-Documentation/wiki/Component-Documentation) |
| **CityScope** | MIT Media Lab | 不是传统预测模型，而是把城市模型、实时交互、情景设计与公众/规划师决策连接起来；对 CitySPS 的 intervention interface 与 human-in-the-loop 很重要。 | [Project](https://cityscope.media.mit.edu/) · [Code](https://github.com/CityScope) · [Architecture](https://cityscope.media.mit.edu/intro/system/) |

## Recommended Reading

| Work | Focus | Resources |
| --- | --- | --- |
| **Integrated Land Use and Transportation Planning and Modeling: Addressing Challenges in Research and Practice** | UrbanSim 作者对 LUTI 理论、数据、实践障碍与政策应用的系统总结。 | [UrbanSim Research](https://www.urbansim.com/academic-research) |
| **Historical Validation of Integrated Transport–Land Use Model System** | 经典问题：城市模型不能只拟合当前状态，必须能做 historical backtesting。 | [Paper](https://doi.org/10.3141/2255-10) |
| **Advances in Integrated Land Use Transport Modeling** | LUTI 的历史、operational models、挑战与未来议程。 | [Paper](https://doi.org/10.1016/bs.atpp.2021.10.002) |
| **ILUTE: An Operational Prototype of a Comprehensive Microsimulation Model of Urban Systems** | 从框架走向真正可运行综合微观模拟时的设计取舍。 | [DOI](https://doi.org/10.1007/s11067-005-2630-5) |

## CitySPS 1.0

- [0_1 · CitySPS 系列工作](./0_1%20CitySPS相关文章/) — CitySPS 论文、书籍、平台与已有模块
- [0_2 · 传统模型与综述](./0_2%20传统模型及综述/) — 传统 LUTI / microsimulation / validation 文献的进一步整理

## What CitySPS 2.0 should inherit

| Traditional-model capability | CitySPS 2.0 question |
| --- | --- |
| **Explicit urban state** | 人口、家庭、企业、土地、交通、设施、经济和环境如何形成统一 Urban State Schema？ |
| **Behavioral mechanisms** | 规则/效用/离散选择等机制如何与 learned behavior model / LLM Agent 结合？ |
| **Multi-timescale dynamics** | 秒—日—月—年不同时间尺度如何共享状态并保持一致？ |
| **Feedback loops** | 交通 ↔ 土地 ↔ 人口 ↔ 经济 ↔ 公共服务之间的反馈如何显式保留？ |
| **Policy intervention** | 规划方案如何作为 action 进入系统，而不是只做被动预测？ |
| **Calibration & validation** | 如何继承传统模型的校准、历史回测、敏感性分析和情景验证传统？ |
| **System engineering** | 如何从“若干单模型”升级成可组合、可替换、可追踪的城市系统平台？ |

> **核心判断：** Foundation Model、Agent、World Model 应该增强传统城市模型，而不是把几十年积累的机制、校准与政策模拟能力全部推倒重来。

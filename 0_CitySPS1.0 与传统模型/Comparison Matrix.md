# Comparison Matrix · Traditional Urban Models

> 目标：不是给模型“排名”，而是比较它们如何组织 **state–actor–dynamics–intervention–validation**，帮助 CitySPS 2.0 决定哪些机制应保留、哪些环节需要由新 AI 范式替代。

| System | Primary scale / unit | Time | Land use | Transport / mobility | Explicit agents | Policy / intervention | Calibration / validation | Open source | What CitySPS should learn |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **UrbanSim** | parcel / zone + households, jobs, developers | multi-year | ✅ Core | ◐ usually coupled | ✅ | ✅ land-use / zoning / development scenarios | ✅ strong tradition | ✅ | 城市状态、区位选择、开发主体和政策情景的模块化耦合 |
| **ILUTE** | individuals / households / firms | long-term + activity/travel | ✅ | ✅ | ✅ | ✅ | ✅ | ◐ | 大规模 microsimulation 如何跨人口、活动、交通和长期演化组织数据与行为 |
| **MATSim** | person / activity chain / network | within-day iterative | — | ✅ Core | ✅ | ✅ pricing, network, service changes | ✅ traffic / behavior outputs | ✅ | 大规模 agent execution、activity chain、network loading 与 replanning |
| **SimMobility** | individuals + vehicles + land-use actors | seconds → days → years | ✅ long-term layer | ✅ Core | ✅ | ✅ | ✅ | ◐ | multi-timescale architecture：短期交通、中期行为、长期城市变化如何连接 |
| **QUANT** | zones / spatial interaction flows | scenario / strategic | ✅ | ✅ accessibility / flows | — | ✅ what-if planning | ✅ aggregate | ◐ | 超大尺度 spatial interaction、快速场景推演与交互式决策支持 |
| **HARMONY** | population / economy / LUTI / network modules | strategic → operational | ✅ | ✅ | ◐ | ✅ | ✅ modular evaluation | ◐ | 战略—战术—运行多层模型套件与跨模块接口设计 |
| **ActivitySim** | person / household | daily activity-travel | — | ✅ Core | ✅ | ✅ travel-demand policy | ✅ | ✅ | Python 配置驱动的 activity-based model、可复现数据管线与行为组件 |
| **POLARIS** | people / households / vehicles / network | within-day + demand | ◐ | ✅ Core | ✅ | ✅ transport / operations / demand policies | ✅ | ◐ | demand + DTA + operations 的统一高性能仿真架构 |
| **BEAM** | person / vehicle / services | within-day | — | ✅ | ✅ | ✅ mobility / energy / AV scenarios | ✅ | ✅ | mode choice、ride-hailing、能源与交通行为的系统联动 |
| **BISTRO** | interventions over BEAM | iterative optimization | — | ✅ | inherited | ✅ Core | objective-based | ✅ | “生成方案 → 仿真 → 评价 → 优化”闭环 |
| **CityScope** | interactive urban indicators / scenarios | interactive | ◐ | ◐ | human-in-loop | ✅ Core | scenario feedback | ✅ ecosystem | 模型如何真正进入规划师/公众交互与方案讨论，而不只是离线预测 |

## CitySPS design questions

- 哪些变量应作为显式 **urban state**，哪些放入 latent representation？
- 哪些主体必须保留 mechanism-based utility / constraints，哪些可以由 learned agent policy 近似？
- 交通、土地、人口、设施、经济应该采用统一模型还是模块化 world model？
- policy action 如何从“参数改动”升级为可组合的 intervention representation？
- validation 如何同时覆盖 micro behavior、meso flows、macro urban structure 和 policy backtesting？

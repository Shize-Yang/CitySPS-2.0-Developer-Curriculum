# Comparison Matrix · Urban Science

> 这里比较的不是“哪个理论更好”，而是不同城市科学工作提供了什么**可观测规律、机制假设和验证约束**，以及它们怎样进入 CitySPS。

| Work / concept | Scale | Main variables | Mechanism / law | Dynamic? | Typical data | CitySPS role |
| --- | --- | --- | --- | --- | --- | --- |
| **Urban Scaling — Bettencourt et al. 2007** | city system | population, infrastructure, socioeconomic outputs | power-law scaling | ◐ comparative | cross-city statistics | 用作跨城市宏观结构约束与 out-of-distribution sanity check |
| **Size, Scale and Shape of Cities — Batty 2008** | city / network | size, form, connectivity | complexity + network organization | ◐ | morphology / networks | 连接城市形态、规模与网络结构，指导 Urban State Schema |
| **Individual Human Mobility — González et al. 2008** | individual | trajectories, radius of gyration, return frequency | regularity + preferential return | ✅ | mobile traces | micro mobility behavior 的基础校准目标 |
| **Spatial Networks — Barthélemy 2011** | network | nodes, links, geometry, flows | spatial cost constrains topology | ◐ | transport / infrastructure networks | 路网与设施图表示、空间约束和 graph prior |
| **Radiation Model — Simini et al. 2012** | population flow | origin population, destination opportunities, intervening opportunities | parameter-free spatial interaction | mostly static | OD / population | OD 生成的机制基线；检验 learned flow model 是否真正超越经典机制 |
| **Origins of Scaling — Bettencourt 2013** | micro → macro | interactions, infrastructure, density | local interaction generates macro scaling | ◐ | urban indicators | 强调宏观规律需要微观机制解释，适合约束 agent → emergence |
| **Human Mobility: Models and Applications — Barbosa et al. 2018** | individual + population | trajectories, OD, migration | multiple generative mechanisms | ✅ | multi-source mobility | mobility model taxonomy、benchmark 与机制先验入口 |
| **Urban Growth & Emergent Statistics — Bettencourt 2020** | city growth | population, growth increments, distributions | stochastic growth + agent strategy | ✅ | longitudinal city data | 连接 urban growth、dynamics 与 macro statistics，适合作为 world-model validation |
| **Universal Visitation Law — Schläpfer et al. 2021** | visits / population | distance, visit frequency, opportunity | universal visitation scaling | ✅ | large-scale visitation | mobility generation 与 facility visitation 的结构性约束 |
| **Spatial interaction / gravity family** | OD / region | masses, opportunities, distance / cost | attraction × impedance | usually static / equilibrium | OD / commuting / migration | 作为所有 neural mobility / world model 的可解释机制 baseline |

## From theory to model constraint

CitySPS 中的城市科学知识至少可以通过四种方式进入模型：

1. **Feature / state design**：决定哪些城市变量和关系必须显式表示。
2. **Inductive bias**：把 spatial decay、network constraints、conservation 等规律写进模型结构或 loss。
3. **Behavior calibration**：用 mobility、visitation、time use 等经验规律约束 Agent。
4. **Evaluation**：不仅比较 RMSE，还检查长期 rollout 是否保持真实城市的 scaling、flow、network 与 inequality structure。

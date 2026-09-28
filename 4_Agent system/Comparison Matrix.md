# Comparison Matrix · Agent Systems

> 目标：比较 Agent 系统如何组织 **memory–goal–planning–action–environment–calibration–emergence**，并区分“通用工具 Agent”“社会模拟 Agent”和“城市行为 Agent”。

| System / work | Scale | Architecture | Memory | Environment / tools | Action space | Grounding / calibration | Intervention / experiments | Open resources | CitySPS relevance |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **ReAct** | single agent | reasoning ↔ acting loop | prompt/context | external tools / environment | tool actions | task feedback | task-level | ✅ Code | Planning Agent 最基本的 control loop |
| **Generative Agents** | tens of agents | memory + reflection + planning | episodic memory + reflection | simulated town / social environment | daily / social actions | human evaluation / behavior plausibility | scenario events | ✅ Code | 人类行为 Agent 的 canonical architecture |
| **Reflexion** | single / small agents | agent + verbal self-feedback | episodic verbal memory | task environments | task actions | reward / evaluator feedback | iterative improvement | ✅ Code | Agent 自我修正与无需参数更新的学习机制 |
| **UGI / Foundational Platform for Generative City Agents** | conceptual platform → scalable city agents | city simulator + UrbanKG + natural-language interface + city FM + generative agents | memory + persona + preference | city simulator / UrbanKG / domain simulators via language or MCP-like interface | perceive / act / communicate + domain tools | simulator feedback + factual urban knowledge + real data / stylized facts | ✅ policy exploration / urban simulation / decision-making | Paper / framework | 与 CitySPS 最接近的系统级概念框架之一：把 Agent 的灵活性与专业城市模型/知识底座的可靠性分层连接 |
| **AgentSociety** | 10k-scale social agents | LLM agents + urban/social environment | individual profiles + memory | realistic city / social interactions | work, travel, social, survey etc. | population / survey / real statistics | ✅ policy / shocks / social experiments | ✅ Code + Docs | CitySPS “城市主体 + 环境 + 干预 + 宏观涌现”最直接竞品之一 |
| **AgentSociety 2** | large-scale | simulated participants + AI social scientist + research workflow | persistent participant state | executable social-science environment | behavior + experimental interactions | empirical / experiment-oriented | ✅ Core | ✅ Code | 把仿真与自动实验设计连接起来，适合 CitySPS research agent |
| **OASIS** | up to million agents | scalable LLM-agent social simulation | profile / social context | dynamic social network + recommender | posting / following / interaction | social-platform patterns | ✅ information / network interventions | ✅ Code | 百万量级执行、批处理、网络涌现与系统扩展性参考 |
| **YuLan-OneSim** | up to 100k agents | scenario authoring + code generation + distributed agents | scenario-specific | configurable social environments | generated / configured actions | scenario / statistic dependent | ✅ social experiments | ✅ Code | 自然语言场景构建、自动仿真代码与 distributed execution |
| **CitySim** | large urban population | LLM-driven urban agents | persona + activity context | city places / schedules | daily activity / spatial behavior | urban density / POI activity patterns | urban scenarios | Paper | 直接模拟城市日程、地点选择和长期活动 |
| **GATSim** | urban mobility population | cognitive agent + mobility FM + traffic simulator | persona / mobility context | city + transportation simulator | activity / trip / route-related actions | mobility traces / travel behavior | transport scenarios | ✅ Code | 行为 Agent 与 mobility foundation model、仿真环境的直接集成 |
| **GeoAgent** | multi-agent workflow | planning → execution → review hierarchy | task/workflow memory | GIS tools / spatial data | geoprocessing operations | executable spatial-analysis results | analytical scenarios | Paper | CitySPS GIS / spatial tool agent 的参考架构 |
| **PlanGPT** | planning assistant / agent | domain LLM + retrieval + tools | planning context / knowledge | planning documents / tools | planning-analysis actions | professional knowledge / retrieval | planning tasks | ✅ Project | 专业规划知识、RAG、工具调用和决策支持 |
| **nanobot** | single + delegated subagents | lightweight agent runtime | session + long-term memory | files, shell, web, MCP, cron, APIs | tools + subagent delegation | user/tool feedback | automation / workflows | ✅ Code + Docs | 很小、可读的真实 Agent runtime，可直接学习 memory/tool/MCP/automation 工程组织 |

## What CitySPS must evaluate

- **Behavior realism**：个体轨迹、活动链、时间利用、消费/迁居等是否和真实数据一致？
- **Population realism**：合成 agent 人口是否匹配人口统计联合分布，而不是只写几句 persona？
- **Action grounding**：LLM 输出的自然语言 action 如何映射到可执行城市行为？
- **Environment grounding**：Agent 是否真正被 city simulator、UrbanKG、GIS、routing、mobility / land-use model 等环境约束，而不是只在 prompt 中“想象城市”？
- **Scale–quality trade-off**：1k、10k、100k、1M agents 扩展时，认知质量、成本和同步机制如何变化？
- **Emergence**：微观行为是否能生成可信的 OD、拥堵、设施使用、集聚/分异和社会网络结构？
- **Intervention response**：面对轨道、新区、价格、住房、极端天气等政策/冲击时，响应是 prompt imagination 还是有数据和机制支撑？
- **Behavioral science validation**：角色、激励、信息、同伴和环境改变后，Agent 行为是否可观察、可干预、可理论解释？
- **Reproducibility**：模型版本、prompt、sampling、memory state 与环境随机性是否可记录、可复现？

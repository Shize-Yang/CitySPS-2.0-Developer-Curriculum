# 3 · Agent Systems

> 这一部分关注：**Agent 如何感知环境、形成记忆与目标、规划行动、调用工具，并在多主体环境中产生可信的个体行为与宏观涌现？**

**Legend:** ⭐ = Must Read · `[Paper]` = 论文 · `[Code]` = 代码 · `[Project]` = 项目主页 · `[Data]` = 数据/benchmark

## ⭐ Foundations: What makes an Agent?

| Work | Venue / Year | Why it matters for CitySPS | Resources |
| --- | --- | --- | --- |
| ⭐ **ReAct: Synergizing Reasoning and Acting in Language Models** | ICLR 2023 | 现代 agent loop 的代表性范式：reasoning 与 action 交替进行。CitySPS 的 Planning Agent / tool-using agent 都应理解这一基本控制循环。 | [Paper](https://arxiv.org/abs/2210.03629) · [Code](https://github.com/ysymyth/ReAct) |
| ⭐ **Generative Agents: Interactive Simulacra of Human Behavior** | UIST 2023 | 将 memory、reflection、planning 组合成持续运行的社会主体，是 LLM-based social simulation 的关键起点。 | [Paper](https://arxiv.org/abs/2304.03442) · [Code](https://github.com/joonspk-research/generative_agents) |
| **Toolformer: Language Models Can Teach Themselves to Use Tools** | NeurIPS 2023 | 说明语言模型如何学习调用外部工具；对应 CitySPS 中 GIS、交通模型、数据库、仿真器、优化器等工具的调用。 | [Paper](https://arxiv.org/abs/2302.04761) |
| ⭐ **Reflexion: Language Agents with Verbal Reinforcement Learning** | NeurIPS 2023 | 用语言反馈、episodic memory 与 self-reflection 形成无需梯度更新的改进回路；可参考 Planning Agent 的自我修正机制。 | [Paper](https://arxiv.org/abs/2303.11366) · [Code](https://github.com/noahshinn/reflexion) |
| **Cognitive Architectures for Language Agents (CoALA)** | TMLR 2023 | 用 memory、action space、decision process 等组件统一描述 language agents，为 CitySPS Agent 架构提供更清晰的概念层。 | [Paper](https://arxiv.org/abs/2309.02427) |
| **Voyager: An Open-Ended Embodied Agent with Large Language Models** | 2023 | 通过自动课程、技能库与迭代提示实现长期能力积累；对应城市 Agent 的 skill / policy library 思路。 | [Paper](https://arxiv.org/abs/2305.16291) · [Project](https://voyager.minedojo.org/) |
| ⭐ **AgentBench: Evaluating LLMs as Agents** | ICLR 2024 | 多环境 agent benchmark，提醒 CitySPS Agent 不能只做 demo，而需要可重复、可比较的任务级评估。 | [Paper](https://arxiv.org/abs/2308.03688) · [Code + Data](https://github.com/THUDM/AgentBench) |

## ⭐ Large-scale Social Simulation

| Work | Year | Why it matters for CitySPS | Resources |
| --- | --- | --- | --- |
| ⭐ **AgentSociety: Large-Scale Simulation of LLM-Driven Generative Agents** | 2025 | 将 LLM agents 推到大规模社会模拟，并研究个体行为、社会交互与宏观涌现；是 CitySPS “大量城市主体”路线的直接参照。 | [Paper](https://arxiv.org/abs/2502.08691) · [System paper](https://aclanthology.org/2025.acl-industry.94/) · [Code](https://github.com/tsinghua-fib-lab/agentsociety/) |
| ⭐ **AgentSociety 2: An Integrated Research Environment for Executable Social Science** | 2026 | 进一步把 simulated participants、实验设计和 AI social scientist 连接起来，值得参考“城市仿真不仅运行 agent，还要支持可执行社会科学实验”的思路。 | [Paper](https://arxiv.org/abs/2607.11895) · [Code](https://github.com/tsinghua-fib-lab/AgentSociety) |

### Related social-agent systems

- **Stanford Generative Agents / Smallville** — memory–reflection–planning 的原型系统。  
  [Code](https://github.com/joonspk-research/generative_agents)

- **Concordia** — DeepMind 面向 generative agent social simulation 的 library，可参考环境、game master 与 agent component 的解耦。  
  [Code](https://github.com/google-deepmind/concordia)

## ⭐ Urban Behavior & Mobility Agents

| Work | Venue / Year | Why it matters for CitySPS | Resources |
| --- | --- | --- | --- |
| **CitySim: Modeling Urban Behaviors and City Dynamics with Large-Scale LLM-Driven Agent Simulation** | arXiv 2025 | 用 LLM-driven agents 建模日程、地点选择与城市活动，直接面向 population density / place popularity 等城市结果。 | [Paper](https://arxiv.org/abs/2506.21805) |
| ⭐ **GATSim: Urban Mobility Simulation with Generative Agents** | Transportation Research Part C, 2026 | 将 mobility foundation model、认知 agent 与交通仿真环境连接，是“数据驱动 mobility prior + LLM cognition + simulator”的代表组合。 | [Paper](https://arxiv.org/abs/2506.23306) · [Code](https://github.com/qiliuchn/gatsim) |

## Spatial Analysis & Planning Agents

| Work | Venue / Year | Why it matters for CitySPS | Resources |
| --- | --- | --- | --- |
| ⭐ **GeoAgent: A Hierarchical LLM-based Multi-agent Architecture for Autonomous Spatial Analysis** | IJGIS 2026 | Planning → Execution → Review 的分层多 Agent 架构，直接展示 LLM 如何自主完成复杂 GIS workflow。 | [Paper](https://doi.org/10.1080/13658816.2026.2624784) · [Code/Data](https://doi.org/10.6084/m9.figshare.29145008) |
| **PlanGPT: Enhancing Urban Planning with Tailored Language Model and Efficient Retrieval** | 2024–2025 | 面向城市规划领域的专门模型、检索与 agent framework，连接专业规划知识、文档和工具调用。 | [Paper](https://arxiv.org/abs/2402.19273) · [Project](https://plangpt.github.io/) |

## Tool-using / Coding Agents worth tracking

这些并非城市专用，但 CitySPS 的 Planning Agent 最终很可能要操作代码、数据库、GIS、模型和仿真器，因此值得作为 engineering reference：

- **SWE-agent / coding agents** — 研究 LLM 如何在真实软件环境中观察、编辑、执行、验证，而不是只生成文本。
- **Browser / computer-use agents** — 对未来 CitySPS 自动检索政策材料、调用网页数据和规划系统有参考价值。
- **Scientific agents** — 对自动形成假设、运行实验、分析结果和迭代模型有参考价值。

这里暂不追求完整收录；只有当其控制循环、工具接口或评估方式能迁移到 CitySPS 时再纳入核心列表。

## Agent architecture checklist for CitySPS

| Dimension | Core question |
| --- | --- |
| **State / Persona** | 人口属性、位置、家庭、职业、资源、角色与约束如何进入 agent state？ |
| **Memory** | 短期、长期、空间、事件和社会关系记忆如何组织？ |
| **Goal / Motivation** | 行为由 prompt、需求、utility、规则、learned policy 还是多目标共同驱动？ |
| **Planning** | 日程、路线、迁居、消费、社交和政策响应如何形成多时间尺度计划？ |
| **Action Space** | 自然语言 action 如何映射为城市世界中的可执行动作？ |
| **Tools** | Agent 如何调用 GIS、routing、search、database、optimization 与专业模型？ |
| **Environment** | Agent 与交通、土地、设施、市场、其他主体和 Urban World Model 如何交互？ |
| **Calibration** | 行为如何与调查、轨迹、OD、时间利用、消费等真实数据校准？ |
| **Emergence** | 微观 agent 是否产生真实可信的宏观空间结构与群体规律？ |
| **Scalability** | 1,000 / 100,000 / 1,000,000 agents 时，成本、通信、上下文和仿真速度如何控制？ |
| **Reproducibility** | LLM 随机性、版本变化和 prompt 变化如何记录并复现实验？ |

## Critical validation principle

> **“行为看起来像人” ≠ “这是一个有效的人类行为模型”。**

CitySPS 中的 generative agent 至少需要同时通过：

1. **Individual-level validation** — 行程链、时间利用、地点选择、迁居/消费决策是否接近真实个体数据；
2. **Population-level validation** — OD、流量、活动密度、访问频率等群体分布是否正确；
3. **Mechanism validation** — 对距离、时间、价格、收入、可达性和政策变化的响应方向是否合理；
4. **Counterfactual validation** — 已发生政策/冲击事件能否被 historical backtesting 重现；
5. **Stability / sensitivity** — 更换 LLM、prompt、temperature 后宏观结果是否稳定。

这也是 CitySPS 与一般“LLM 社会模拟 demo”需要拉开的关键距离。

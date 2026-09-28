# 3 · Agent Systems

> 这一部分关注 LLM Agent / Generative Agent 如何感知环境、形成记忆与目标、规划行动，并在多主体环境中产生可解释的群体行为。

## Foundations

- ⭐ **[ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629)** — *ICLR 2023*  
  现代 agent loop 的代表性工作：交替进行 reasoning 与 action。  
  [Code](https://github.com/ysymyth/ReAct)

- ⭐ **[Generative Agents: Interactive Simulacra of Human Behavior](https://arxiv.org/abs/2304.03442)** — *2023*  
  将 memory、reflection 与 planning 组合成可持续运行的生成式社会主体，是后续 LLM 社会模拟的重要起点。  
  [Code](https://github.com/joonspk-research/generative_agents)

- **[Cognitive Architectures for Language Agents (CoALA)](https://arxiv.org/abs/2309.02427)** — *TMLR 2023*  
  用 memory、action space、decision process 等概念系统化描述 language agent architecture。

## Large-scale Social Simulation

- ⭐ **[AgentSociety: Large-Scale Simulation of LLM-Driven Generative Agents Advances Understanding of Human Behaviors and Society](https://arxiv.org/abs/2502.08691)** — *2025*  
  面向大规模社会/城市主体模拟，重点关注人口规模、社会交互与宏观涌现。  
  [Code](https://github.com/robertmay615/agentsociety)

- ⭐ **[AgentSociety 2: An Integrated Research Environment for Executable Social Science](https://arxiv.org/abs/2607.11895)** — *2026*  
  将 AI social scientist 与 simulated participants 放入统一运行环境，进一步把 agent simulation 与可执行社会科学实验结合。  
  [Code](https://github.com/fnstggl/agentsociety2)

## Urban Behavior & Mobility Agents

- **[CitySim: Modeling Urban Behaviors and City Dynamics with Large-Scale LLM-Driven Agent Simulation](https://arxiv.org/abs/2506.21805)** — *2025*  
  用 LLM-driven agents 生成日程、空间行为和长期城市活动，用于人群密度、地点热度和城市行为模拟。

- **[GATSim: Urban Mobility Simulation with Generative Agents](https://arxiv.org/abs/2506.23306)** — *Transportation Research Part C, 2026*  
  将城市 mobility foundation model、认知 agent 与交通仿真环境连接，是 CitySPS 行为模型的重要直接参考。  
  [Code](https://github.com/qiliuchn/gatsim)

## Spatial Analysis & Planning Agents

- **[GeoAgent: a hierarchical LLM-based multi-agent architecture for autonomous spatial analysis](https://doi.org/10.1080/13658816.2026.2624784)** — *IJGIS 2026*  
  Planning → Execution → Review 的分层多 Agent 架构，用于复杂 GIS / spatial analysis workflow。

- **[PlanGPT: Enhancing Urban Planning with a Tailored Agent Framework](https://aclanthology.org/2025.acl-industry.54/)** — *ACL 2025 Industry Track*  
  将领域模型、检索和工具能力组合到城市规划 agent 中，连接专业知识与实际规划工作流。  
  [Project](https://plangpt.github.io/)

## What to compare

| Dimension | Questions |
| --- | --- |
| **State / Persona** | Agent 需要知道什么？人口属性、位置、历史、资源、角色如何编码？ |
| **Memory** | 短期记忆、长期记忆、空间记忆和群体记忆如何组织？ |
| **Goal / Motivation** | 行为由 prompt、规则、utility、需求还是 learned policy 驱动？ |
| **Planning** | Agent 如何从目标生成长期/短期行动序列？ |
| **Action Space** | 自然语言行动如何映射到真实城市中的出行、消费、迁居、政策响应等行为？ |
| **Environment** | Agent 与交通、土地、设施、其他主体以及 World Model 如何交互？ |
| **Calibration** | 怎样让 agent 行为与真实调查、轨迹、OD、时间利用和统计分布一致？ |
| **Emergence** | 微观 agent 是否产生可信的宏观城市模式？ |

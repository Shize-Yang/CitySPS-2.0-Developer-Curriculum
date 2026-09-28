# 1 · Reviews & Perspectives（综述与前沿）

> 这一部分不按具体技术模块分类，而是收录**能够帮助我们理解城市模型、城市预测与 AI 范式如何整体演化**的综述、观点与研究议程。它适合作为进入 CitySPS 2.0 各技术模块之前的“全局地图”。

**Legend:** ⭐ = Must Read · `[Paper]` = 论文 · `[List/Code]` = 持续更新的资料或代码

## ⭐ Must Read

| Work | Venue / Year | Why it matters for CitySPS | Resources |
| --- | --- | --- | --- |
| ⭐ **Predicting urban futures: Epistemic shifts and the governance of uncertainty** — Junxi Qu, Lingkun Meng, Tianren Yang | *Progress in Human Geography*, 2026 | 从 structural-equilibrium / process-based models 追踪到 algorithmic prediction，并讨论 explanation–prediction–policy control 的张力。对 CitySPS 尤其重要：预测更准并不自动意味着机制更可信、政策更可解释。 | [Paper](https://doi.org/10.1177/03091325261472137) |
| ⭐ **Modelling and Predictions of Urban Development: Progress, Challenges and Prospects** — Tianren Yang et al. | *国际城市规划*, 2022 | 系统梳理宏观、微观和集成城市模型，并提出精细化、技术/行为变化、跨尺度集成、事后评估与动态更新等方向；与 CitySPS 的长期路线高度相关。 | [Paper](https://doi.org/10.19830/j.upi.2022.418) |
| ⭐ **The Future of Urban Modelling: From BLV to AI** — Alan Wilson | *Networks and Spatial Economics*, 2025 | 从经典 spatial interaction / urban modelling 走向 data science 与 AI，强调 theory–method–policy–analytics–design 的重新整合。 | [Paper](https://doi.org/10.1007/s11067-024-09658-8) |
| ⭐ **City models: past, present and future prospects** — Ritter et al. | *Frontiers of Urban and Rural Planning*, 2025 | 从传统城市模型、数字城市表示延伸到生成式 AI 和“rich citizen models”，是传统模型 → AI agent 城市模型之间很好的桥梁。 | [Paper](https://doi.org/10.1007/s44243-025-00057-2) |
| **Urban models: Progress and perspective** | *Sustainable Futures*, 2024 | 重新梳理 aggregate static、urban dynamics、agent-based 等模型谱系，并讨论 top-down / bottom-up 的整合。 | [Paper](https://doi.org/10.1016/j.sftr.2024.100181) |
| ⭐ **Human mobility: Models and applications** — Barbosa et al. | *Physics Reports*, 2018 | 从个体到群体、短程到长程系统总结 mobility 规律和生成模型，是 CitySPS mobility / behavior 模块的基础综述。 | [Paper](https://doi.org/10.1016/j.physrep.2018.01.001) |
| **Deep Learning for Spatio-Temporal Data Mining: A Survey** — Wang et al. | *IEEE TKDE*, 2022 | 建立 ST data 类型、深度模型与任务之间的系统对应关系，是理解传统 STDL → ST Foundation Model 的重要过渡材料。 | [Paper](https://doi.org/10.1109/TKDE.2020.3025580) |
| ⭐ **Urban Foundation Models: A Survey** — Zhang et al. | *KDD*, 2024 | 从数据模态和任务角度系统定义 Urban Foundation Models，并讨论 Urban General Intelligence。 | [Paper](https://doi.org/10.1145/3637528.3671453) · [List](https://github.com/usail-hkust/Awesome-Urban-Foundation-Models) |
| ⭐ **Towards Urban General Intelligence: A Review and Outlook of Urban Foundation Models** | *ACM TIST*, 2026 | UFM 综述的扩展版，进一步覆盖 benchmarks、datasets 与 UGI 路线，适合跟踪 2024–2026 的快速演化。 | [Paper](https://arxiv.org/abs/2402.01749) |
| ⭐ **A Survey on Large Language Model Based Autonomous Agents** — Wang et al. | *Frontiers of Computer Science*, 2024 | 统一梳理 agent construction、applications 与 evaluation，是 Agent System 模块最适合作为入口的综述之一。 | [Paper](https://doi.org/10.1007/s11704-024-40231-1) · [List](https://github.com/Paitesanshi/LLM-Agent-Survey) |
| ⭐ **AI agent behavioral science** — Chen et al. | *Humanities & Social Sciences Communications*, 2026 | 将 AI agent 从“模型内部结构”转向“情境中的行为实体”来研究，系统覆盖 individual agent、multi-agent、human-agent interaction，并强调 observation、intervention、theory-guided interpretation。对 CitySPS 的 Agent validation 非常重要：不能只评模型能力，还要评真实情境中的行为、适应与失配。 | [Paper](https://doi.org/10.1057/s41599-026-07316-7) |
| ⭐ **Towards a foundational platform for generative agents in simulated city environment** — Xu et al. | *PLOS Complex Systems*, 2026 | 从 urban computing、digital twin、ABM 与 LLM agents 出发提出 Urban Generative Intelligence (UGI)：以 city simulator + UrbanKG + natural-language interface 为开放数字底座，在其上连接城市 foundation model 与 generative agents。与 CitySPS 2.0 的“城市环境 + Agent + 工具/知识 + 仿真反馈”高度同构。 | [Paper](https://doi.org/10.1371/journal.pcsy.0000093) |
| ⭐ **Understanding World or Predicting Future? A Comprehensive Survey of World Models** — Ding et al. | *ACM Computing Surveys*, 2025 | 将 world model 区分为“理解世界”和“预测未来”两类，并覆盖自动驾驶、机器人、urban systems 和 social simulacra；对定义 Urban World Model 很关键。 | [Paper](https://arxiv.org/abs/2411.14499) · [List](https://github.com/tsinghua-fib-lab/World-Model) |

## Suggested reading order

1. **先理解城市模型为什么存在**：Yang et al. 2022 → Wilson 2025 → Ritter et al. 2025。
2. **再理解城市预测正在发生什么变化**：Qu, Meng & Yang 2026。
3. **补足城市科学与 mobility 的机制基础**：Barbosa et al. 2018。
4. **进入城市智能体与系统层**：UGI 2026 → AI Agent Behavioral Science 2026。
5. **最后进入新 AI 技术栈**：Urban Foundation Models Survey → LLM Agent Survey → World Model Survey。

## What to extract

阅读综述时不要只记录“有哪些模型”，而应持续回答：

- **Problem framing**：城市模型到底是在解释、预测、模拟还是支持政策决策？
- **Epistemology**：模型依赖机制假设、统计关联，还是大规模预训练得到的隐式知识？
- **Integration**：人口、土地、交通、设施、经济、环境、行为如何耦合？
- **Agent behavior**：Agent 应该如何观察、干预、验证，而不是只凭“像人”判断有效性？
- **Uncertainty & causality**：预测误差、因果解释、反事实和政策效果如何区分？
- **Governance**：模型结果如何进入真实规划决策，如何保持透明、可审计和可讨论？
- **CitySPS gap**：已有综述中的哪些问题仍没有被 Foundation Model + Agent + World Model 真正解决？

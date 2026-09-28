# Tutorials & Talks · 教程与讲座

> 这里收录不是正式课程、但对 CitySPS 架构理解非常有价值的系统教程、讲座与 slide deck。重点是**能否提供一张清晰的方法地图**，而不是材料数量。

## ⭐ World Models / Urban World Models

### ⭐ 从理解世界到推演城市：连接物理与社会的世界模型

**冯杰 · 中关村学院 · 2026-09-18**  
English subtitle: *World Models for Physical and Social Intelligence: Foundations, Methods, and Urban Embodiment*

这份 160 页 Tutorial 很适合作为 CitySPS 的 World Model 入门和架构讨论材料。它不是只介绍 video generation，而是按能力链条组织：

1. **共同基础** — 区分 state / observation，建立 World Model 的基本定义；
2. **理解世界** — internal representation 如何支持知识、推理与决策；
3. **预测世界** — future generation、interactive environment 与 embodied world；
4. **应用与验证** — 不同领域如何真正使用和检验 World Model；
5. **城市世界模型** — 将城市研究拆为城市认知、行为动力学、交互环境与任务验证；
6. **社会具身智能** — 在物理约束、多主体信息差、规范、持续互动和协作中检验智能。

### 对 CitySPS 最值得保留的四块城市结构

| Capability | Input → Output | CitySPS correspondence |
| --- | --- | --- |
| **城市认知** | 多源证据 → 空间与社会状态 | Urban Foundation Model / Urban State Encoder / CityGPT-like spatial cognition |
| **行为动力学** | 空间与需求 → 活动、轨迹、流量 | Mobility / Behavior Model + Generative Agents |
| **交互环境** | 地图与图像 → 可运行三维世界 | Physical / Embodied Urban Environment；UrbanWorld2.0 等 |
| **任务验证** | 场景操作 → 可观测行动结果 | Agent evaluation、historical backtesting、Real2Sim2Real、policy intervention validation |

**为什么值得反复看：** 它把 World Model 从“一个模型架构”重新放回到 **认知—行为—环境—验证** 的系统关系里。对于 CitySPS 2.0，这比简单复制 Dreamer 或视频生成模型更重要。

- [Author / Homepage](https://vonfeng.github.io/)
- [Related World Model Survey](https://arxiv.org/abs/2411.14499)
- [World Model module in this Handbook](../5_World%20model/)

## Selection rule

后续进入这一页的 Tutorial / Talk 至少满足一个条件：

- 对一个 CitySPS 核心模块提供系统性方法地图；
- 能把多个分散论文组织成清晰的技术演化路线；
- 对“城市如何迁移/改造这些方法”有明确讨论；
- 包含值得反复引用的 taxonomy、framework、evaluation framework 或 research agenda。

# 5 · World Models

> 这一部分关注：**模型如何学习 environment dynamics，并利用 learned world 做 rollout、planning、control 与 counterfactual simulation？** 对 CitySPS 来说，它最终要回答的是“城市在某种行动与外部冲击下会怎样演化”。

**Legend:** ⭐ = Must Read · `[Paper]` = 论文 · `[Code]` = 代码 · `[Project]` = 项目主页 · `[Data]` = 数据/模型

📊 **[Comparison Matrix](./Comparison%20Matrix.md)** — 比较 state、action conditioning、dynamics/output、planning、horizon、uncertainty 与开放资源。

## ⭐ Foundations: Learned Dynamics in Latent Space

| Work | Venue / Year | Why it matters for CitySPS | Resources |
| --- | --- | --- | --- |
| ⭐ **World Models** | 2018 | 现代 neural world model 的经典起点：先学习压缩表示和环境动力学，再在 learned world 中训练 controller。最重要的是“representation + dynamics + control”的模块化思想。 | [Paper](https://arxiv.org/abs/1803.10122) · [Project](https://worldmodels.github.io/) |
| ⭐ **PlaNet: Learning Latent Dynamics for Planning from Pixels** | ICML 2019 | 在 latent state-space model 中做 planning，证明高维 observation 不必直接在像素空间规划；对应 CitySPS 的 urban latent state + intervention planning。 | [Project](https://planetrl.github.io/) · [Code](https://github.com/google-research/planet) |
| ⭐ **Dream to Control: Learning Behaviors by Latent Imagination** | ICLR 2020 | Dreamer 用 imagined rollouts 在 latent world 中直接学习 actor/critic，把 world model 从“预测器”升级成“决策环境”。 | [Paper](https://arxiv.org/abs/1912.01603) · [Code](https://github.com/danijar/dreamer) |
| **DreamerV2: Mastering Atari with Discrete World Models** | ICLR 2021 | 通过 discrete latent state 改进复杂环境建模，为城市 token / discrete latent dynamics 提供参考。 | [Paper](https://arxiv.org/abs/2010.02193) · [Code](https://github.com/danijar/dreamerv2) |
| ⭐ **Mastering Diverse Control Tasks through World Models (DreamerV3)** | Nature, 2025 | 一个统一 world-model RL 配方跨大量任务与环境工作，重点价值在“通用训练 recipe + robust dynamics learning + imagination”。 | [Paper](https://doi.org/10.1038/s41586-025-08744-2) · [Code](https://github.com/danijar/dreamerv3) |

## Planning with Learned Models

| Work | Venue / Year | Why it matters for CitySPS | Resources |
| --- | --- | --- | --- |
| ⭐ **MuZero: Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model** | Nature, 2020 | 不要求显式重构完整环境，只学习对 planning 有用的 representation、reward 和 dynamics；提醒 CitySPS world model 不一定必须预测所有城市变量。 | [Paper](https://www.nature.com/articles/s41586-020-03051-4) |
| ⭐ **TD-MPC2: Scalable, Robust World Models for Continuous Control** | ICLR 2024 | 将 latent dynamics 与 model predictive control 结合，并强调规模化、robustness 与多任务控制。对政策 action optimization 很有参考价值。 | [Paper](https://arxiv.org/abs/2310.16828) · [Code](https://github.com/nicklashansen/tdmpc2) · [Project + Models](https://www.tdmpc2.com/) |

## ⭐ Predictive Representation / JEPA Route

JEPA 路线和 Dreamer / video-generation 路线非常不同：它不要求重建每一个可见细节，而是在 representation space 中预测“真正有意义、可预测的未来”。这对高度异构、噪声大且长时程的城市系统尤其值得关注。

- ⭐ **A Path Towards Autonomous Machine Intelligence** — *Yann LeCun, 2022*  
  提出以 world model、latent-variable energy-based model、JEPA、planning 等为核心的自主智能架构愿景。对于 CitySPS 的价值是：**未来状态不一定要逐像素/逐变量重建，可以在抽象 latent space 中预测对决策有用的信息。**  
  [Paper](https://openreview.net/forum?id=BZ5a1r-kVsf)

- ⭐ **[V-JEPA 2: Self-Supervised Video Models Enable Understanding, Prediction and Planning](https://arxiv.org/abs/2506.09985)** — *Meta FAIR, 2025*  
  用大规模互联网视频预训练 predictive representation，再以少量 action-conditioned robot data 构建 V-JEPA 2-AC world model，实现理解、预测和规划。对 CitySPS 很有启发：**先学习通用城市状态表征，再用有限干预/政策数据学习 action-conditioned dynamics。**  
  [Code + Models](https://github.com/facebookresearch/vjepa2) · [Project](https://ai.meta.com/research/vjepa/)

- **V-JEPA 2.1: Unlocking Dense Features in Video Self-Supervised Learning** — *2026*  
  在 JEPA 预训练中进一步加入 dense predictive loss、deep self-supervision 与多模态 tokenizer，并展示 data/model scaling。对 CitySPS 的 dense spatial representation 与 multi-scale urban feature learning 也值得跟踪。  
  [Paper](https://arxiv.org/abs/2603.14482) · [Code](https://github.com/facebookresearch/vjepa2)

## ⭐ Generative / Interactive World Models

这条路线不再只学习 compact latent dynamics，而是直接生成可观察世界的未来状态。CitySPS 需要理解它，但不能简单照搬“video world model”。

| Work | Year | Key idea | Resources |
| --- | --- | --- | --- |
| ⭐ **Genie: Generative Interactive Environments** | 2024 | 从无 action label 视频中学习 latent actions 和可交互未来，是“从被动 observation 学 interaction”路线的代表。 | [Paper](https://arxiv.org/abs/2402.15391) · [Project](https://deepmind.google/research/publications/60474/) |
| ⭐ **UniSim: Learning Interactive Real-World Simulators** | ICLR 2024, Outstanding Paper | 将视觉、语言和动作条件统一到可交互真实世界生成器中；对多模态 condition → future state 很有启发。 | [Paper](https://arxiv.org/abs/2310.06114) · [Project](https://universal-simulator.github.io/) |
| ⭐ **DIAMOND: Diffusion for World Modeling — Visual Details Matter in Atari** | NeurIPS 2024 Spotlight | diffusion model 直接作为交互环境 dynamics；展示生成质量和 control performance 可以共同优化。 | [Paper](https://arxiv.org/abs/2405.12399) · [Code](https://github.com/eloialonso/diamond) · [Project](https://diamond-wm.github.io/) |
| **GameNGen: Diffusion Models Are Real-Time Game Engines** | 2024 | action-conditioned diffusion 在实时交互循环中直接生成下一世界状态，是生成模型作为 simulator 的极端案例。 | [Paper](https://arxiv.org/abs/2408.14837) · [Project](https://gamengen.github.io/) |

## Autonomous Driving / Physical AI

这些工作与城市系统比游戏 world model 更接近，因为它们要处理真实空间、交通主体、动作条件和安全关键 planning。

- ⭐ **[GAIA-1: A Generative World Model for Autonomous Driving](https://arxiv.org/abs/2309.17080)** — *Wayve, 2023*  
  将 video、text、vehicle action 统一到 driving world model 中；对应 CitySPS 的 observation + semantic context + intervention conditioning。

- ⭐ **[Think2Drive: Efficient Reinforcement Learning by Thinking with Latent World Model for Autonomous Driving](https://www.ecva.net/papers/eccv_2024/papers_ECCV/html/6129_ECCV_2024_paper.php)** — *ECCV 2024*  
  以 compact latent world model 作为 neural simulator，在 CARLA 中做高效 policy learning；很适合作为“真实复杂环境 + learned simulator + planner”的直接案例。

- ⭐ **[Cosmos World Foundation Model Platform for Physical AI](https://arxiv.org/abs/2501.03575)** — *NVIDIA, 2025*  
  代表 world model 向大规模视频预训练、physical AI、可控生成和下游 adaptation 扩展的路线。  
  [Code](https://github.com/NVIDIA/cosmos)

## Toward an Urban World Model

对 CitySPS 来说，World Model 不是“生成一段看起来像城市的视频”。它更接近一个 **heterogeneous, intervention-conditioned, multi-scale urban dynamics model**：

```text
Urban state z_t
    + intervention / action a_t
    + external shock e_t
    + spatial / institutional knowledge K
                    ↓
            Urban World Model
                    ↓
 future state distribution p(z_{t+1:t+H} | z_t, a_t, e_t, K)
                    ↓
     evaluation / planning / optimization
```

### Three world-model routes CitySPS should compare

| Route | Representative work | Strength | Main risk for CitySPS |
| --- | --- | --- | --- |
| **Latent dynamics + imagination** | Dreamer / TD-MPC2 | Efficient rollout、planning、control | latent state 可能忽略长期社会结构和制度变量 |
| **Predictive representation / JEPA** | V-JEPA 2 | 不重建无关细节，强调 abstract predictable state | 如何定义“对城市决策真正有用”的 target representation 仍是核心难题 |
| **Generative world simulation** | Genie / UniSim / DIAMOND / Cosmos | 多模态、可观察、可交互未来生成 | 容易把视觉逼真误当成城市机制正确 |

### What CitySPS should borrow

| World-model idea | Urban adaptation |
| --- | --- |
| **Latent state-space model** | 用统一 urban latent state 压缩人口、土地、交通、设施、经济、环境等异构状态 |
| **Action-conditioned dynamics** | 将轨道、新区、道路、住房、产业、公服等真实政策/规划动作显式输入 dynamics |
| **Imagination / rollout** | 在 latent world 中推演未来城市轨迹，而非每次调用完整昂贵仿真器 |
| **Model predictive planning** | 多个备选规划方案在线 rollout → 评估 → 重新规划 |
| **Task-relevant state** | 不要求预测全部城市细节，而优先保留对决策和评价有用的信息 |
| **Generative modeling** | 对多模态未来状态和多种可能未来建模，而不是单点预测 |
| **World-model pretraining** | 在多城市、多年份、多事件数据上学习通用城市动态，再适配本地城市 |

### What CitySPS should **not** copy blindly

1. **Video ≠ Urban State**：城市不是 RGB frame sequence，核心状态包括人口、网络、制度、土地、价格、政策、行为和不可见 latent processes。
2. **Action ≠ joystick**：城市 action 往往高维、组合式、延迟生效并带制度约束。
3. **Long horizon matters more**：游戏/驾驶常关注秒—分钟，城市政策通常跨月—年，error accumulation 与 structural change 更严重。
4. **Counterfactual ≠ forecast**：政策模拟要求回答“如果实施了一个现实中未实施的方案会怎样”，需要更强的因果识别、机制约束和不确定性表达。
5. **Multi-agent feedback**：人口与企业会对政策和彼此反应，world dynamics 不能把 human behavior 当作固定背景。
6. **Validation must be historical and structural**：不仅比较下一时刻误差，还要验证长期分布、城市规律、历史政策冲击和跨城市迁移。

## Core evaluation dimensions

| Dimension | Urban question |
| --- | --- |
| **State representation** | z_t 是否保留了城市政策与行为需要的关键信息？ |
| **One-step accuracy** | 下一状态预测是否准确？ |
| **Long-horizon stability** | 多步 rollout 是否漂移、坍缩或违反基本城市规律？ |
| **Action response** | 模型是否对干预方向、强度、空间范围和时滞作出合理响应？ |
| **Shock response** | 极端天气、疫情、经济冲击和重大活动是否能作为 e_t 进入模型？ |
| **Uncertainty / multimodality** | 对同一政策是否能表达多个合理未来，而不是伪确定性？ |
| **Counterfactual validity** | 能否重现已发生政策事件，并可信外推到未观察 action？ |
| **Cross-city transfer** | 在未见城市、不同规模/制度/形态下是否仍保持有效？ |
| **Decision usefulness** | world model 提升了 policy ranking / optimization，还是只提升预测指标？ |

## CitySPS target

最终希望得到的不是单纯“城市预测模型”，而是一个可以被 Agent 和 Planner 调用的动态环境：

> **Urban World Model = 可学习、可推演、可干预、可验证、可用于规划决策的城市动态模型。**

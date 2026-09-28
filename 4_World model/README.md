# 4 · World Models

> 这一部分关注模型如何学习 **state → action → next state** 的动态关系，并利用 learned dynamics 做 imagination、planning、control 与 counterfactual simulation。

## Foundations

- ⭐ **[World Models](https://arxiv.org/abs/1803.10122)** — *Ha & Schmidhuber, 2018*  
  现代 neural world model 的经典起点：学习压缩世界表征与动态模型，再在 learned environment 中训练 controller。

- **[PlaNet: Learning Latent Dynamics for Planning from Pixels](https://planetrl.github.io/)** — *ICML 2019*  
  在 learned latent space 中进行 planning，强调 model-based control 与高维感知之间的连接。  
  [Code](https://github.com/google-research/planet)

## Dreamer Family

- ⭐ **[Dream to Control: Learning Behaviors by Latent Imagination](https://arxiv.org/abs/1912.01603)** — *ICLR 2020*  
  在 latent world model 中进行 imagined rollouts，并直接学习 actor / critic。  
  [Code](https://github.com/danijar/dreamer)

- **[DreamerV2: Mastering Atari with Discrete World Models](https://arxiv.org/abs/2010.02193)** — *ICLR 2021*  
  以离散 latent representation 提升复杂环境中的 world model learning。  
  [Code](https://github.com/danijar/dreamerv2)

- ⭐ **[DreamerV3: Mastering Diverse Domains through World Models](https://arxiv.org/abs/2301.04104)** — *Nature 2025*  
  用统一配置跨越多种控制任务，是 CitySPS 设计 general-purpose urban dynamics learner 的重要方法参考。

## Generative / Interactive World Models

- **[Genie: Generative Interactive Environments](https://arxiv.org/abs/2402.15391)** — *2024*  
  从未标注视频学习可交互世界，并学习 latent action space；代表“生成式 world model”路线。

- **[GameNGen: Diffusion Models Are Real-Time Game Engines](https://arxiv.org/abs/2408.14837)** — *2024*  
  通过 action-conditioned diffusion 直接生成下一帧环境状态，展示生成模型作为 simulator 的可能性。

- **[NVIDIA Cosmos World Foundation Models](https://blogs.nvidia.com/blog/cosmos-world-foundation-models/)** — *2025*  
  面向 robotics / autonomous driving 的 world foundation model 平台，强调大规模视频预训练、物理一致性与可控生成。

## Autonomous Driving / Physical AI

- ⭐ **[Think2Drive: Efficient Reinforcement Learning by Thinking with Latent World Model for Autonomous Driving](https://www.ecva.net/papers/eccv_2024/papers_ECCV/html/6129_ECCV_2024_paper.php)** — *ECCV 2024*  
  将 compact latent world model 作为 neural simulator，在 CARLA 中训练驾驶 planner，是“复杂真实环境 + world model + policy”结合的直接案例。

## Toward an Urban World Model

对 CitySPS 来说，World Model 不是简单的视频生成模型。更核心的问题是：

```text
Urban state z_t
    + intervention / action a_t
    + external shock e_t
    + spatial knowledge K
                ↓
        Urban World Model
                ↓
   future urban state z_{t+1:t+H}
```

重点比较：

| Dimension | Urban question |
| --- | --- |
| **State representation** | 城市状态由人口、土地、交通、设施、经济、环境等哪些变量构成？ |
| **Action conditioning** | 轨道交通、新区、住房、产业、道路、公共服务等干预如何编码？ |
| **Exogenous shocks** | 极端天气、疫情、活动和经济冲击如何进入动态模型？ |
| **Long-horizon rollout** | 如何避免长期推演中的 error accumulation 与状态漂移？ |
| **Uncertainty** | 对未来状态与政策效果的不确定性如何量化？ |
| **Counterfactual** | 如何区分“预测未来”与“模拟一个未发生的政策世界”？ |
| **Validation** | 如何用历史 backtesting、真实政策事件和跨城市迁移验证 world model？ |

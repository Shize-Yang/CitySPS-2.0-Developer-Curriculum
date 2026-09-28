# Comparison Matrix · World Models

> 目标：比较不同 World Model 对 **state、action、dynamics、rollout、planning 与 uncertainty** 的处理方式，判断什么才适合迁移到 Urban World Model。

| Model | State / representation | Action conditioning | Dynamics / output | Planning / control | Horizon | Uncertainty | Open resources | CitySPS relevance |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **World Models** | compressed VAE latent | controller action | recurrent latent dynamics | controller trained in imagined world | medium | implicit stochasticity | ✅ Project / Code ecosystem | representation + dynamics + controller 的经典三段式 |
| **PlaNet** | latent state-space model | control action | probabilistic latent transition + reward | online planning / MPC in latent space | medium | ✅ probabilistic state model | ✅ Code | `urban latent state + action → future` 的直接结构参考 |
| **DreamerV3** | recurrent latent state (RSSM) | action | latent transition + reward / continuation | actor–critic trained on imagined rollouts | long multi-step | stochastic latent | ✅ Code | 不必每次在真实环境试错，可在 learned urban world 中训练/评价 policy |
| **MuZero** | task-relevant learned representation | action | latent dynamics + reward + value | tree search | planning horizon | implicit via search / value | implementations | 提醒 CitySPS：world model 不一定重建完整城市，只需学习对决策有用的 dynamics |
| **TD-MPC2** | compact latent state | continuous action | latent transition + reward/value | model predictive control | receding horizon | limited explicit uncertainty | ✅ Code + Models | 连续政策 action、optimization 与 robust latent dynamics 的参考 |
| **V-JEPA 2 / 2-AC** | predictive semantic representation | action in AC variant | predicts future latent features rather than pixels | action-conditioned planning demonstrations | multi-step | latent prediction | ✅ Code + Models | 对城市特别有价值：避免重建所有噪声变量，只预测可决策的抽象未来状态 |
| **Genie** | video tokens + learned latent actions | inferred / latent action | generative future visual states | interactive rollout | short–medium | generative distribution | Project / paper | 从 passive observations 学“可交互 dynamics”的范式 |
| **UniSim** | multimodal visual world representation | language / action / visual conditions | conditional future world generation | interactive simulation | short–medium | generative | ✅ Project | 多模态 condition → future state；可启发遥感/街景/文本干预条件化 |
| **DIAMOND** | pixel/video representation | environment action | diffusion next-state generation | policy learning inside model | multi-step | diffusion distribution | ✅ Code | diffusion 作为 simulator；帮助理解高保真生成和控制如何结合 |
| **Cosmos** | video / physical-world latent or tokens | text / trajectory / action conditioning | world generation / prediction | Physical AI training / evaluation | varying | generative | ✅ Models / platform | 大规模 Physical AI world foundation model 的系统工程与数据路线 |
| **GAIA-1** | driving video tokens | vehicle action / context | generative driving future | simulation / scenario generation | multi-step | generative | Paper / demos | 自动驾驶世界模型：现实动态、action condition、场景生成的城市相邻案例 |
| **Think2Drive** | compact latent driving state | driving control | latent dynamics | RL / planner in learned simulator | long control sequences | model-dependent | Paper | “真实复杂系统 + learned simulator + planner”的直接案例 |

## Urban World Model requirements

一个真正的 Urban World Model 至少还要比上述模型多处理几件事：

1. **Multi-timescale**：分钟级出行、日活动、月度市场变化、年度土地利用演化共同存在。
2. **Multi-actor**：居民、家庭、企业、开发商、政府、交通运营者的 actions 同时改变状态。
3. **Structured intervention**：地铁、新区、住房、税费、产业、公共服务不能只作为 text prompt，而应有明确 action schema。
4. **Exogenous shocks**：天气、灾害、疫情、重大活动、宏观经济变化需要与人为 intervention 分开建模。
5. **Counterfactual validity**：预测 `future under observed policy` 与推演 `future under unseen policy` 不是同一任务。
6. **Uncertainty & causal validity**：需要输出政策效果置信度、OOD 风险，并和纯相关预测区分。
7. **Multi-level validation**：同时检查变量预测误差、长期结构、城市科学规律和历史政策 backtesting。

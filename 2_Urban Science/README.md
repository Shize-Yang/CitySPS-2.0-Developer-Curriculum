# 2 · Urban Science

> 城市科学回答的是：**CitySPS 应该学习、解释和检验哪些真实城市规律？** 这一部分优先收录能够为城市状态、行为机制、空间交互、动力学与验证提供理论约束的工作。

**Legend:** ⭐ = Must Read · `[Paper]` = 论文 · `[Code]` = 代码 · `[Data]` = 数据 · `[Project]` = 项目主页

📊 **[Comparison Matrix](./Comparison%20Matrix.md)** — 比较不同城市科学理论的尺度、变量、机制及其如何进入 CitySPS 约束与验证。

## ⭐ Must Read

| Work | Venue / Year | Why it matters for CitySPS | Resources |
| --- | --- | --- | --- |
| ⭐ **Growth, Innovation, Scaling, and the Pace of Life in Cities** | PNAS, 2007 | 城市标度研究的奠基工作之一：基础设施、社会经济产出和城市规模之间存在系统性 scaling，为 CitySPS 的宏观约束与跨城市比较提供基线。 | [Paper](https://doi.org/10.1073/pnas.0610172104) |
| ⭐ **The Size, Scale, and Shape of Cities** | Science, 2008 | 把城市理解为复杂系统，并将 scale、spatial form、network 与 growth 联系起来，是传统 urban modeling 与新城市科学之间的关键桥梁。 | [Paper](https://doi.org/10.1126/science.1151419) |
| ⭐ **Understanding Individual Human Mobility Patterns** | Nature, 2008 | 从大规模移动数据发现个体轨迹的稳定空间尺度、回访与规律性，是所有 mobility behavior model 的基础文献。 | [Paper](https://doi.org/10.1038/nature06958) |
| ⭐ **Spatial Networks** | Physics Reports, 2011 | 系统总结空间约束如何塑造网络结构、运输网络与流过程；对 CitySPS 的路网、设施网络、城市关联图建模非常基础。 | [Paper](https://doi.org/10.1016/j.physrep.2010.11.002) · [arXiv](https://arxiv.org/abs/1010.0302) |
| ⭐ **A Universal Model for Mobility and Migration Patterns** | Nature, 2012 | Radiation model 将 population/opportunity 与 OD flow 连接起来，并提供 parameter-free 机制模型；是学习式 mobility model 必须比较的经典基线。 | [Paper](https://doi.org/10.1038/nature10856) · [Implementation](https://github.com/scikit-mobility/scikit-mobility/blob/master/skmob/models/radiation.py) |
| ⭐ **The Origins of Scaling in Cities** | Science, 2013 | 从局部社会交互、基础设施与空间约束推导宏观 scaling，强调“宏观规律应有微观机制解释”。 | [Paper](https://doi.org/10.1126/science.1235823) |
| ⭐ **Human Mobility: Models and Applications** | Physics Reports, 2018 | 人群移动领域最重要的系统综述之一，贯通 individual / population mobility、gravity / radiation / generative models 与应用。 | [Paper](https://doi.org/10.1016/j.physrep.2018.01.001) · [arXiv](https://arxiv.org/abs/1710.00004) |
| ⭐ **Urban Growth and the Emergent Statistics of Cities** | Science Advances, 2020 | 将城市增长、随机动力学、agent strategy 与 scaling 统一到动态框架中，是 CitySPS 从静态规律走向 learned urban dynamics 的直接理论参考。 | [Paper](https://doi.org/10.1126/sciadv.aat8812) · [Code + Data](https://github.com/mansueto-institute/Urban-Growth-Emergent-Statistics) |
| ⭐ **The Universal Visitation Law of Human Mobility** | Nature, 2021 | 把 visit frequency 与 distance 统一成稳定标度关系，并给出 exploration / preferential return 机制；可直接用于 CitySPS mobility simulation 的校准与验证。 | [Paper](https://doi.org/10.1038/s41586-021-03480-9) · [Code + Data](https://github.com/leiii/VisitationLaw) |

## Spatial Interaction & Mobility

- **[Uncovering the Spatial Structure of Mobility Networks](https://doi.org/10.1038/ncomms7007)** — *Nature Communications, 2015*  
  从多城市移动网络中识别空间结构与城市组织，对“OD graph 反映什么城市结构”这一问题非常直接。

- **Gravity / Spatial Interaction Models**  
  CitySPS 不应只把 gravity model 当 baseline，而应把它作为“机会规模 + 空间阻抗 → 流”的机制先验，与 neural / foundation mobility models 对照。

- **[scikit-mobility](https://github.com/scikit-mobility/scikit-mobility)**  
  提供 gravity、radiation、individual mobility generative models、mobility measures 等可复用实现，适合做 CitySPS 机制基线与数据诊断。

## Urban Growth, Scaling & Complexity

- **[Building a Science of Cities](https://doi.org/10.1016/j.cities.2011.11.008)** — *Cities, 2012*  
  Michael Batty 对城市科学发展方向的概括，适合建立“城市模型—复杂系统—数据科学”的整体历史脉络。

- **The New Science of Cities** — *Michael Batty, MIT Press, 2013*  
  从 networks、flows、interaction 与 spatial dynamics 重新理解城市，适合作为 CitySPS 的理论背景书。

- **The Structure and Dynamics of Cities** — *Marc Barthelemy, Cambridge University Press, 2016*  
  以统计物理、网络和空间机制为主线解释城市结构与演化，适合 World Model 的 mechanism prior 设计。

## Classic Mechanism Models Worth Keeping

- **Schelling: Dynamic Models of Segregation** — *Journal of Mathematical Sociology, 1971*  
  最经典的“简单个体规则 → 宏观空间涌现”例子之一。对 LLM/learned agents 的一个提醒是：更复杂的 agent 并不自动意味着更好的社会机制解释。  
  [Paper](https://doi.org/10.1080/0022250X.1971.9989794)

- **Central Place / Location / Accessibility theories**  
  Christaller、Alonso、Hansen 等经典空间理论不一定直接转化为神经网络，但应作为 CitySPS 的 concept vocabulary 与机制检查清单长期保留。

## CitySPS Research Map

| Topic | Core question | How it can constrain CitySPS |
| --- | --- | --- |
| **Urban Scaling** | 哪些指标随城市规模呈稳定 scaling？ | 跨城市 sanity check、loss/regularization、模型外推边界 |
| **Urban Complexity** | 哪些宏观结构由局部相互作用涌现？ | Agent → macro emergence validation |
| **Spatial Interaction** | 人、机会、空间阻抗如何形成 OD？ | mobility baseline、counterfactual response |
| **Networks & Flows** | 网络拓扑与空间嵌入如何影响流与韧性？ | Road/POI/functional graph encoder 与 intervention evaluation |
| **Human Mobility** | exploration、return、distance、frequency 有哪些规律？ | 行为 agent / trajectory generator 的校准指标 |
| **Accessibility & Land Use** | 可达性如何反馈到区位与开发？ | LUTI feedback + policy channel |
| **Urban Growth** | 城市状态如何长期演化且保持统计规律？ | Urban World Model 的长期 dynamics benchmark |
| **Agglomeration / Segregation** | 集聚、分异与不平等如何形成？ | 社会后果与政策干预评估 |

## Recommended evaluation principle

对任何 CitySPS 新模型，至少问四件事：

1. **它能不能重现已知城市规律？**
2. **它在哪些城市/尺度上违反这些规律？**
3. **规律是被模型真正学到，还是训练数据记忆出来？**
4. **政策干预后，规律如何变化，变化是否具有机制解释？**

# Stanford CS336 · Language Modeling from Scratch

**Stanford University · Spring 2026**  
[Course Website](https://cs336.stanford.edu/) · [Lecture Materials](https://github.com/stanford-cs336/lectures)

## Why it matters for CitySPS

CS336 的价值不在于“学会调用 LLM”，而在于从头理解一个现代 Foundation Model 的完整构建链条：

`data → tokenizer → model → optimization → scaling → distributed training → evaluation`

这套思路可以直接迁移到 CitySPS 的 Urban Foundation Model、统一编码器与大规模预训练工程。

## Recommended topics

| Topic | Priority | CitySPS connection |
| --- | --- | --- |
| Data collection & cleaning | ★★★★★ | 城市多源预训练数据构建与质量控制 |
| Tokenization / representation | ★★★★★ | Urban token、空间单元、轨迹/流/图的统一表示 |
| Transformer architecture | ★★★★☆ | Foundation Model backbone |
| Optimization & training stability | ★★★★★ | 大规模时空预训练 |
| Scaling laws | ★★★★★ | 数据、模型规模和算力配置 |
| Systems / distributed training | ★★★★★ | 多 GPU 训练与训练效率 |
| Evaluation | ★★★★☆ | 泛化、zero-shot / few-shot 与模型能力评估 |
| Alignment / post-training | ★★★☆☆ | LLM Agent / Planning Agent 阶段更相关 |

## How to use

不要求按学期顺序完整学习。更适合作为 CitySPS 开发中的**技术参考课程**：遇到数据、表示、训练、scaling 或 distributed systems 问题时回到对应 lecture / assignment。

# Courses · 精选课程

> 这里不是要建立一套固定“培训计划”，而是保存对 CitySPS 研发真正有用的高质量课程。建议按负责模块选择，而不是全部从头到尾学完。

## ⭐ Core Courses

| Course | Focus | Why it matters for CitySPS | Recommended parts | Link |
| --- | --- | --- | --- | --- |
| ⭐ **Stanford CS336 — Language Modeling from Scratch** | 从数据、tokenizer、Transformer、训练、scaling 到 evaluation，从零构建语言模型 | Foundation Model 负责人理解完整 pretraining stack 的首选课程 | data / tokenizer / architecture / optimization / systems / scaling / evaluation | [Course](https://cs336.stanford.edu/) |
| ⭐ **Stanford CS224V — Agentic AI (Fall 2026)** | dependable agents、RAG、research agents、formal task descriptions、long-horizon agent methods | 对 Planning Agent、Research Agent、知识检索与降低 hallucination 直接相关 | RAG without hallucination / research agents / formal methods / long-horizon agents | [Course](https://web.stanford.edu/class/cs224v/) |
| ⭐ **Stanford CS329Z — Engineering AI Agents (Fall 2026)** | 从 LLM pipelines 到 compound AI systems 与 autonomous agents；强调 components、data、evaluation 与 engineering trade-offs | 最适合研究 CitySPS Agent 如何真正做成可运行系统，而不只是 prompt demo | retrieval / tool use / memory / multi-agent / data / evaluation / agent safety | [Course](https://cs329z.stanford.edu/) |
| ⭐ **UC Berkeley CS285 — Deep Reinforcement Learning, Decision Making, and Control** | model-free / model-based RL、imitation、exploration、video prediction、transfer | Urban World Model → Planning / Intervention Optimization 的基础课程 | model-based RL / MPC / imitation / offline RL / exploration | [Course](https://rail.eecs.berkeley.edu/deeprlcourse/) |
| ⭐ **Hugging Face Agents Course** | Agent 基础、Think→Act→Observe、tools、smolagents、LlamaIndex、LangGraph、Agentic RAG、evaluation | 快速建立现代 Agent 工程与框架直觉，适合与 nanobot / smolagents 源码配合 | Unit 1 / smolagents / Agentic RAG / observability & evaluation | [Course](https://huggingface.co/learn/agents-course/) |
| **Stanford CS25 — Transformers United V6** | Transformer / foundation-model 前沿专题讲座 | 不是系统教材，但适合持续跟踪 LLM、多模态、机器人和 Transformer 新方向 | 按讲者/主题选看，不要求完整学习 | [Course](https://web.stanford.edu/class/cs25/) |
| **Stanford CS329X — Human-Centered LLMs (Fall 2026)** | human-centered design、alignment、preference tuning、personalization、HCI、privacy、risk | CitySPS 最终面对规划师、政府和公众；Planning Agent 不能只优化性能，还要考虑 human-in-the-loop、可解释与责任 | alignment / personalization / HCI / privacy / risk measurement | [Course](https://web.stanford.edu/class/cs329x/) |

## Suggested mapping to CitySPS

| CitySPS module | Priority resources |
| --- | --- |
| **Urban Foundation Model / Encoder** | CS336 → CS25 |
| **LLM / Planning Agent** | CS329Z → CS224V → Hugging Face Agents Course |
| **Urban World Model / Policy Optimization** | CS285 → CS336（representation / scaling 部分） |
| **Human-in-the-loop Planning Intelligence** | CS329X → CS224V |
| **Agent engineering / prototypes** | CS329Z + Hugging Face Agents Course + nanobot / smolagents |

## How to use these courses

课程条目进入 Handbook 的标准不是“名校课程越多越好”，而是它能否解决 CitySPS 的真实研发问题：

- 能否帮助理解底层模型，而不只是调用 API；
- 是否包含可复现作业、代码或系统设计；
- 是否能对应 Foundation Model、Agent、World Model、Planning / Optimization 中的一个实际模块；
- 是否能形成持续更新的技术参照，而不是一次性的入门教程。

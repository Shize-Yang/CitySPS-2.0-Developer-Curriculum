# Hands-on Projects · 可读代码项目

> 这一部分收录**代码足够完整、又足够可读**的开源项目。目的不是把 CitySPS 建在这些项目上，而是通过真正读源码、跑训练和改模块，快速理解现代 Foundation Model / Agent 的工程骨架。

## ⭐ Recommended Projects

| Project | What it is | What to learn | Why useful for CitySPS | Resources |
| --- | --- | --- | --- | --- |
| ⭐ **nanobot** | HKUDS 的超轻量 Python AI Agent runtime；包含 tools、长期记忆、MCP、model routing、subagent delegation、scheduled automation、WebUI/API | agent loop、tool registry、memory、MCP、subagents、automation、provider abstraction | 很适合直接读一个“小而完整”的 Agent 系统；比一上来读巨型 Agent framework 更容易理解 Planning Agent 工程结构 | [Code](https://github.com/HKUDS/nanobot) · [Docs](https://nanobot.wiki/docs/latest/getting-started/nanobot-overview) |
| ⭐ **MiniMind** | 从零训练约 64M 级超小语言模型的完整 PyTorch 项目 | tokenizer、Dense/MoE、pretrain、SFT、LoRA、DPO、PPO/GRPO、Tool Use、Agentic RL、distillation | 可低成本走完“数据 → 预训练 → 对齐 → tool use / agentic RL”全流程，适合真正理解 Foundation Model 训练链 | [Code](https://github.com/jingyaogong/minimind) · [Models/Data](https://huggingface.co/collections/jingyaogong/minimind-66caf8d999f5c7fa64f399e5) |
| ⭐ **nanochat** | Karpathy 的 minimal full-stack LLM training/chat harness | tokenization、pretraining、finetuning、evaluation、inference 的最小实现 | 和 CS336 / MiniMind 配合，用少量代码理解语言模型从训练到 chat 的完整链路 | [Code](https://github.com/karpathy/nanochat) |
| ⭐ **smolagents** | Hugging Face 的轻量 Agent library，核心逻辑紧凑，支持 code agents 和 tool-calling agents | tool calling、CodeAgent、model abstraction、agent execution loop | 与 Hugging Face Agents Course 配套，适合做 CitySPS tool agent / GIS agent 的快速原型 | [Code](https://github.com/huggingface/smolagents) · [Docs](https://huggingface.co/docs/smolagents/) |

## Suggested mini-reproduction tasks

这些不是课程作业，而是适合在真正研发前快速“摸清底层”的小实验：

1. **MiniMind / nanochat**：从零跑一个小模型，修改 tokenizer 或输入 schema，观察 training loss / downstream behavior。
2. **nanobot**：自己实现一个 `GIS tool` 或 `CitySPS API tool`，把 tool → memory → agent loop 走通。
3. **smolagents**：实现一个能够读取城市数据、调用 Python/GIS 工具并返回可复现分析结果的 spatial agent。
4. **Agent runtime comparison**：用同一个简单任务分别在 nanobot 和 smolagents 中实现，比较状态、工具、记忆和执行 loop 的工程差异。

## Selection rule

后续新增项目优先满足至少一项：

- **from scratch**：能看到关键算法而不是只封装 API；
- **small & readable**：核心逻辑足够紧凑，适合阅读；
- **end-to-end**：覆盖完整训练/Agent pipeline；
- **directly transferable**：可以直接帮助 CitySPS 的 Encoder、Agent、World Model 或 Planning 模块原型开发。

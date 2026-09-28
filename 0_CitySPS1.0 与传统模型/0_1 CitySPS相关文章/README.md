# 0_1 · CitySPS 系列工作

这里集中整理 **CitySPS 1.0 / CitySPS 系列论文、模型与项目材料**。

## Reading format

后续每项 CitySPS 工作统一按下面的形式整理：

| Work | Year | Problem | Key idea | Links |
| --- | ---: | --- | --- | --- |
| CitySPS 系列工作 | — | 城市系统建模与模拟 | 提取 CitySPS 1.0 的状态表示、模块关系、模拟逻辑与政策接口 | Paper · Code · Project |

## Questions for CitySPS 2.0

对于每篇 CitySPS 工作，优先回答四个问题：

1. **What remains valid?** 哪些设计在 CitySPS 2.0 中应直接继承？
2. **What breaks?** 哪些模块受到数据规模、泛化能力、行为假设或计算能力限制？
3. **What can be learned?** 哪些原本手工定义的状态、规则或参数可以通过数据学习？
4. **What should stay mechanistic?** 哪些政策、制度和因果机制不能被纯数据驱动模型替代？

> 这里将优先放正式论文、代码仓库和项目主页链接，而不是以 PDF 文件名作为目录。

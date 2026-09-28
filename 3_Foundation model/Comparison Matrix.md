# Comparison Matrix · Foundation Models

> 目标：比较不同 Foundation Model **如何统一数据、表示、任务与泛化**，而不是只看参数规模。对 CitySPS 最重要的是判断：哪些设计能形成统一 Urban Encoder / Tokenizer，哪些只是单任务大模型。

| Work | Data / modalities | Representation | Pretraining objective | Backbone | Tasks | Generalization | Open resources | CitySPS relevance |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **UniST** | multi-city urban spatio-temporal grids | patch / prompt-conditioned ST representation | masked / large-scale ST pretraining + prompt adaptation | Transformer | traffic / crowd / urban ST forecasting | few-shot / zero-shot across scenarios | ✅ Code | 通用时空预训练 + prompt adaptation 的直接样板 |
| **BIGCity** | trajectory + traffic-state data | unified ST-unit | unified pretraining across trajectory / traffic tasks | Transformer-style universal ST model | trajectory understanding + traffic-state analysis | cross-task | ✅ Code | 对 CitySPS 统一 mobility token / representation 最直接 |
| **OpenCity** | multi-city traffic sensor / graph data | graph / temporal tokens | open ST pretraining for traffic prediction | ST Transformer | traffic forecasting | ⭐ cross-city zero-shot / scaling | ✅ Code + Data + Weights | 检验跨城市迁移与 scaling 的关键参考 |
| **UrbanCLIP** | remote sensing / street-view / web text / region context | contrastive region embedding | image–text contrastive learning | vision + language encoders | urban-region profiling | transfer across downstream urban tasks | ✅ Code | 多模态 Urban Encoder：视觉、文本、空间语义对齐 |
| **UrbanGPT** | numeric ST signals + language instructions | ST encoder aligned with LLM tokens | instruction tuning / cross-modal alignment | ST encoder + LLM | forecasting / urban QA | task transfer / instruction following | ✅ Code + Project | 研究 LLM 如何承接城市数值时空任务 |
| **CityGPT** | city map / simulator-derived urban experience + general instructions | natural-language urban knowledge / spatial-reasoning instructions | CityInstruction + Self-Weighted Fine-Tuning | ChatGLM3 / Llama3 / Qwen2.5 family | CityQA / CityWalk / CityReasoning + CityEval | cross-LLM transfer; city-scale spatial cognition | ✅ Code + Data + Benchmark | 把离线城市空间知识与 embodied mobility experience 注入 LLM，直接服务城市认知型 Agent |
| **UrbanDiT** | grid / graph / heterogeneous ST data | unified latent / token space | diffusion generative objective | Diffusion Transformer | prediction + generation | open-world / heterogeneous tasks | ✅ Code | 预测与生成统一、缺失补全和 counterfactual generation 的候选路线 |
| **UrbanFM** | WorldST-scale heterogeneous urban ST corpus | scalable urban representation | large-scale ST pretraining | Transformer family | multiple urban ST tasks | scaling / cross-domain | Paper | CitySPS 数据规模、benchmark 与 scaling-law 设计参考 |
| **Prithvi-EO-2.0** | multispectral EO time series + geolocation / time metadata | patch tokens with spatiotemporal metadata | masked autoencoding | ViT | EO segmentation / classification / regression | geospatial transfer | ✅ Code + Weights | 遥感进入 Urban State；位置/时间 metadata-aware pretraining |
| **TerraMind** | multimodal EO (imagery + geospatial modalities) | multimodal generative tokens | any-to-any multimodal generative pretraining | generative multimodal Transformer | understanding + generation + modality translation | cross-modal / missing modality | ✅ Code | CitySPS 多模态缺失补全、跨模态生成与统一地理表示 |
| **MOMENT** | large heterogeneous time-series corpora | patch time-series embedding | masked time-series modeling | Transformer | classification / anomaly / forecasting / imputation | zero-/few-shot across datasets | ✅ Code / Models | 非城市专用的通用时间序列 FM baseline |
| **TimesFM** | very large time-series corpus | patch / decoder tokens | autoregressive forecasting pretraining | decoder-only Transformer | zero-shot forecasting | cross-domain zero-shot | ✅ Code / Weights | 大规模 forecasting scaling 和上下文窗口设计参考 |
| **Chronos** | broad time-series datasets | quantized value tokens | language-model-style next-token prediction | T5-style Transformer | probabilistic forecasting | zero-shot | ✅ Code / Weights | “时间序列 tokenization → LM objective” 的极简范式 |

## Key design axes for CitySPS

| Axis | Question |
| --- | --- |
| **Urban token / latent** | 城市状态应该按 grid、region、node、trajectory、event 还是多尺度 token 统一？ |
| **Multimodality** | OD、轨迹、路网、POI、遥感、政策文本、气象如何进入同一 representation？ |
| **Objective** | masked modeling、contrastive、autoregressive、diffusion、JEPA 哪些更适合城市系统？ |
| **Task unification** | prediction、generation、retrieval、classification、simulation 能否共享 backbone？ |
| **Spatial cognition** | 模型是否真正理解 city-scale topology、direction、distance、navigation 与 urban semantics，而不只是记忆坐标？ |
| **Transfer** | 跨城市、跨国家、跨任务、跨模态的 zero/few-shot 应如何分别评估？ |
| **Scaling** | 数据量、参数量、城市数和任务数增加时，性能是否稳定提升？ |
| **Interpretability** | latent representation 是否能和真实城市状态变量、机制或政策语义对齐？ |

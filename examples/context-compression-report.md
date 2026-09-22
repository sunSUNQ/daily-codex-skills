# LLM 上下文压缩：调研报告样例

> 这是使用 `topic-progress-research` 对“LLM 上下文压缩”执行得到的样例快照（2026-09-22）。它与同目录 PDF 对应，供查看完整报告结构与来源呈现方式。该样例形成于 `max_community_sources` 默认值提升前，因此社区资料只列出了当时已核验的 4 条；当前 Skill 的默认上限为 20。

## 有效范围与调用

```text
使用 $topic-progress-research 调研 LLM 上下文压缩。
```

| 参数 | 本次设置 |
|---|---|
| `paper_years` | 5 |
| `project_recency` | 12 months |
| `max_projects` | 20 |
| `published_only` | true |
| `include_close` | true |
| `community_sources` | true |

检索词包含：`context compression`、`prompt compression`、`long-context compression`、`RAG compression`、`soft-token memory`、`KV-cache compression`、`agent context management`、`tool-output compression`、`CLI proxy` 与 `MCP context`。

会议发现使用 [CCFDDL](https://ccfddl.com/)，CCF 分级依据 [CCF 人工智能目录](https://www.ccf.org.cn/Academic_Evaluation/AI/)。ICLR 未列入当前 CCF AI 目录，不据此推断等级。

## 已发表论文候选池

论文标题为官方出版/论文页直链；代码仅在已验证与论文有关联时列出。

| 会议 / CCF | 论文 | 已验证代码 / 实验仓库 |
|---|---|---|
| EMNLP 2023 / B | [LLMLingua](https://aclanthology.org/2023.emnlp-main.825/) | [microsoft/LLMLingua](https://github.com/microsoft/LLMLingua) |
| EMNLP 2023 / B | [Selective Context](https://aclanthology.org/2023.emnlp-main.391/) |  |
| EMNLP 2023 / B | [AutoCompressors](https://aclanthology.org/2023.emnlp-main.232/) | [princeton-nlp/AutoCompressors](https://github.com/princeton-nlp/AutoCompressors) |
| EMNLP 2023 / B | [Learning to Compress Prompts with Sentinel Tokens](https://aclanthology.org/2023.emnlp-main.794/) |  |
| EMNLP Findings 2023 / B | [TCRA-LLM](https://aclanthology.org/2023.findings-emnlp.655/) |  |
| NeurIPS 2023 / A | [Learning to Compress Prompts with Gist Tokens](https://proceedings.neurips.cc/paper_files/paper/2023/hash/3d77c6dcc7f143aa2154e7f4d5e22d68-Abstract-Conference.html) | [jayelm/gisting](https://github.com/jayelm/gisting) |
| ICLR 2024 / 未列入 | [RECOMP](https://proceedings.iclr.cc/paper_files/paper/2024/hash/bda88ed2892f5e61c9a9bf215c566913-Abstract-Conference.html) | [carriex/recomp](https://github.com/carriex/recomp) |
| ICLR 2024 / 未列入 | [In-Context Autoencoder](https://openreview.net/pdf?id=uREj4ZuGJE) | [getao/icae](https://github.com/getao/icae) |
| ACL 2024 / A | [LongLLMLingua](https://aclanthology.org/2024.acl-long.91/) | [microsoft/LLMLingua](https://github.com/microsoft/LLMLingua) |
| ACL Findings 2024 / A | [LLMLingua2](https://aclanthology.org/2024.findings-acl.57/) | [microsoft/LLMLingua](https://github.com/microsoft/LLMLingua) |
| AAAI 2025 / A | [CPC](https://ojs.aaai.org/index.php/AAAI/article/view/34639) |  |
| AAAI 2025 / A | [AttnComp](https://ojs.aaai.org/index.php/AAAI/article/view/34800) |  |
| ACL 2025 / A | [DAC](https://aclanthology.org/2025.acl-long.952/) |  |
| ACL 2025 / A | [500xCompressor](https://aclanthology.org/2025.acl-long.1219/) | [ZongqianLi/500xCompressor](https://github.com/ZongqianLi/500xCompressor) |
| ACL 2025 / A | [Pretraining Context Compressors for Long-Context Language Models](https://aclanthology.org/2025.acl-long.1394/) |  |
| ACL 2026 / A | [GMSA](https://aclanthology.org/2026.acl-long.1324/) |  |
| ACL 2026 / A | [Attn-GS](https://aclanthology.org/2026.acl-long.1663/) |  |
| ACL 2026 / A | [SARA](https://ahren09.github.io/publication/acl26_sara/) | [Ahren09/SARA](https://github.com/Ahren09/SARA) |
| ICML 2026 / A | [ACON](https://openreview.net/pdf?id=x0alNh5o8v) | [microsoft/acon](https://github.com/microsoft/acon) |
| ACL Findings 2026 / A | [BRIEF-Pro](https://aclanthology.org/2026.findings-acl.696/) |  |

## 开源项目 Top 20

指标均是 2026-09-22 快照；项目均来自 GitHub。

| 排名 | 项目 | Stars | Forks | 许可证 | 最近活动 | 主要边界 |
|---:|---|---:|---:|---|---|---|
| 1 | [RTK](https://github.com/rtk-ai/rtk) | 81,336 | 5,153 | Apache-2.0 | 2026-09-21 | Coding-agent shell/tool output |
| 2 | [LLMLingua](https://github.com/microsoft/LLMLingua) | 6,689 | 428 | MIT | 2026-09-10 | Prompt/RAG compression |
| 3 | [Chisle](https://github.com/JayPokale/Chisle) | 494 | 32 | MIT | 2026-09-19 | Coding-agent text/tool output |
| 4 | [Context Engine](https://github.com/Context-Engine-AI/Context-Engine) | 402 | 55 | MIT | 2026-07-08 | Agent context/MCP |
| 5 | [AutoCompressors](https://github.com/princeton-nlp/AutoCompressors) | 336 | 27 | 未声明 | 2024-09-09 | Soft-token compression |
| 6 | [leanctx](https://github.com/jia-gao/leanctx) | 326 | 5 | MIT | 2026-08-22 | Context reduction |
| 7 | [Gist Tokens](https://github.com/jayelm/gisting) | 322 | 26 | Apache-2.0 | 2025-02-14 | Gist-token compression |
| 8 | [SARA](https://github.com/Ahren09/SARA) | 262 | 0 | Apache-2.0 | 2026-07-23 | Adaptive compression |
| 9 | [tokenfold](https://github.com/snchimata/tokenfold) | 206 | 35 | Apache-2.0 | 2026-09-21 | Token/context folding |
| 10 | [ICAE](https://github.com/getao/icae) | 178 | 19 | CC0-1.0 | 2024-05-11 | Memory-slot compression |
| 11 | [RECOMP](https://github.com/carriex/recomp) | 149 | 8 | MIT | 2026-01-06 | RAG compression |
| 12 | [ACON](https://github.com/microsoft/acon) | 116 | 17 | MIT | 2025-10-14 | Adaptive context compression |
| 13 | [Supercompress](https://github.com/Supercompress/Supercompress) | 79 | 23 | MIT | 2026-09-08 | Prompt/context compression |
| 14 | [500xCompressor](https://github.com/ZongqianLi/500xCompressor) | 64 | 8 | 未声明 | 2026-03-09 | Paper implementation |
| 15 | [Distil](https://github.com/dshakes/distil) | 16 | 3 | 未声明 | 2026-09-21 | Tool output distillation |
| 16 | [context-compress](https://github.com/Open330/context-compress) | 8 | 0 | MIT | 2026-09-12 | Context compression |
| 17 | [tare](https://github.com/mstuart/tare) | 4 | 1 | MIT | 2026-09-21 | Agent/tool context |
| 18 | [capsule](https://github.com/hakiyaka/capsule) | 4 | 0 | MIT | 2026-09-19 | Context packaging |
| 19 | [context-compressor](https://github.com/xbyteid/context-compressor) | 1 | 0 | MIT | 2026-07-06 | Context compression |
| 20 | [mcp-guardian](https://github.com/S1LV3RJ1NX/mcp-guardian) | 0 | 1 | MIT | 2026-07-14 | MCP context guard |

## 技术社区与媒体信号

这些资料用于工程线索与实践观点，不能替代论文结论、代码关联或性能证据。

| 原文 | 平台 / 类型 | 日期 | 简要总结 | 局限 |
|---|---|---|---|---|
| [大模型 RAG 的上下文压缩与过滤](https://www.cnblogs.com/ExMan/p/19135643) | 博客园 / 技术博客 | 2025-10-11 | 展示 RAG 检索后过滤、摘要、结构化字段提取与组合策略。 | 个人技术文章，需独立复核。 |
| [Tool Output Compression](https://tianpan.co/blog/2026/04/20/tool-output-compression-context-injection) | Tian Pan / 工程博客 | 2026-04-20 | 讨论字段提取、模型摘要和原始注入在 Agent 工具输出场景的取舍。 | 作者观点，部分内容仅会员可见。 |
| [RAG 上下文压缩实战](https://darrypy.github.io/posts/2026-07-14-rag-context-compression.html) | DarryPy / 技术博客 | 2026-07-14 | 比较规则过滤、重排截断、LLM 提取与 LLMLingua 的工程路线。 | 个人实战文章，指标应回溯原始实验。 |
| [LLM Agent 上下文压缩算法](https://blog.hugozhu.site/post/2026/182-llm-agent-context-compression-evolution/) | Hugo Zhu's Blog / 技术博客 | 2026 | 梳理 Agent 的上下文膨胀与压缩算法演进。 | 使用前应再次核验页面可访问性和日期。 |

## 使用提示

该示例刻意保留 direct、close 和 adjacent 候选，作为人工筛选池。代码列为空表示当时未验证到官方或论文明确关联的公开实现，并不代表不存在代码。

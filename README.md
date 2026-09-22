# Daily Codex Skills

一组面向日常技术调研与工程工作的 Codex Skills。本仓库当前发布一个 Skill：`topic-progress-research`。

## topic-progress-research

面向技术主题的高召回调研：将结果明确划分为三类来源，方便先尽量找全、再人工筛选。

1. **正式发表论文**：按近五年为默认窗口，优先官方 proceedings、出版方或 DBLP；标记会议与 CCF 分级，并把已验证的代码、实验和数据仓库附在论文行中。
2. **开源项目**：默认 Top 20；区分 GitHub、GitLab、Gitee、项目官网等来源，记录 Stars、Forks、许可证和活跃度快照。
3. **技术社区与媒体信号**：通过 Google、Bing 等发现后，打开实际文章再总结技术博客、知乎、公众号、会议笔记等内容。它们单列呈现，带平台、日期、简要总结、局限和直链，不与论文或官方代码混为主证据。

### 报告交付

正式调研默认同时生成两份同名报告：

- `topic-report.md`：完整、可编辑的 Markdown 源版本；
- `topic-report.pdf`：用于阅读和分享的 PDF 版本。

两份文件保留相同的完整候选池、表格、参数、覆盖缺口和可点击来源链接；PDF 不是摘要节选。

### 样例报告

可直接查看对“LLM 上下文压缩”的一次完整调研输出：[Markdown](examples/context-compression-report.md) / [PDF](examples/context-compression-report.pdf)。

### 安装

克隆本仓库后，将该 Skill 目录复制到 Codex 的本地 skills 目录：

```powershell
git clone https://github.com/<your-account>/daily-codex-skills.git
Copy-Item .\daily-codex-skills\skills\topic-progress-research "$env:USERPROFILE\.codex\skills\" -Recurse
```

重新打开一个 Codex 会话后调用：

```text
使用 $topic-progress-research 调研 LLM 上下文压缩。
```

### 常用参数

| 参数 | 默认值 | 用途 |
|---|---:|---|
| `paper_years` | `5` | 正式发表会议论文的滚动时间窗口。 |
| `project_recency` | `12 months` | 独立发现开源项目的优先活跃窗口。 |
| `max_projects` | `20` | 独立开源项目的最大数量。 |
| `published_only` | `true` | 主论文池只收录已正式发表的论文。 |
| `include_close` | `true` | 保留 close / adjacent 候选，便于手动删选。 |
| `community_sources` | `true` | 输出第三类技术社区/媒体资料。 |
| `max_community_sources` | `10` | 第三类资料的去重后最大数量。 |

例如：

```text
调研上下文压缩近10年发表的论文；max_projects=30；community_sources=true；max_community_sources=15。
```

## 仓库结构

```text
skills/
└── topic-progress-research/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
```

## 使用边界

- 该 Skill 追求高召回候选集，而不是声称结果绝对完整。
- 社区文章用于发现工程线索和实践观点；论文结论、代码关联、性能数据仍以一手来源为准。
- Stars、Forks 等仓库指标是检索时的快照，不是质量或安全性的证明。

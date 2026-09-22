---
name: topic-progress-research
description: "Research a topic's recent progress through papers, open-source projects, and clearly labeled technical-community evidence. Use for landscape scans, literature reviews, and state-of-the-art briefs; not for implementing a project."
---

# Topic Progress Research

Produce a decision-useful, time-bounded picture of progress in the user's topic. Cover scholarly work, practically relevant open-source work, and a concise technical-community signal summary when they exist. Prefer evidence over breadth: distinguish a primary result from commentary, a maintained project from an abandoned repository, and a stated claim from an inference.

## Scope first

Identify or make a clearly stated, low-risk assumption about:

- the topic and adjacent areas to include or exclude;
- the time window, using the defaults in **Request parameters** unless the user supplies one;
- desired audience and output depth;
- whether the user needs research only, a shortlist for adoption, or both.

Ask a concise question only when those choices materially change the research. Do not infer a geographical, commercial, or ideological scope that the user did not request.

## Request parameters

Accept parameters stated naturally or as `key=value`. Defaults apply only when the user does not specify an equivalent instruction:

| Parameter | Default | Meaning |
|---|---:|---|
| `paper_years` | `5` | Rolling publication window for conference papers. `近10年` means `paper_years=10`. |
| `project_recency` | `12 months` | Preferred activity window for independently discovered open-source projects. Retain an older project when it is the verified implementation of a retained paper. |
| `max_projects` | `20` | Maximum independently ranked open-source projects. Paper-linked repositories remain in their paper rows even when this limit is reached. |
| `published_only` | `true` | Include only formally published conference papers; label Findings/workshop tracks separately. |
| `include_close` | `true` | Retain close and adjacent candidates with an explicit relevance label for manual screening. |
| `community_sources` | `true` | Search and summarize relevant technical discussions, blogs, and community posts as a separate third source class. |
| `max_community_sources` | `20` | Maximum community/technical-media sources in the summary; deduplicate syndications and repeated reposts. |

Use the user's exact dates or calendar-year request when supplied. State the effective settings near the start of the report. Read [usage and tuning](references/usage-and-tuning.md) when the user asks how to invoke or configure the skill; read [evaluation cases](references/evaluation-cases.md) before publishing or materially changing this skill.

## Topic expansion

Before selecting venues or papers, turn the user's topic into a small, auditable query map. Preserve the original wording as the core term, then add only semantically close terms in these groups:

- synonyms, abbreviations, and spelling variants;
- broader or narrower technical concepts;
- adjacent tasks that share the same research objective, method, or evaluation setting;
- field-standard English and Chinese terms, plus method or benchmark names discovered during the search.

For example, interpret “代码检测” according to the surrounding context and consider related terms such as code analysis, program analysis, bug/defect detection, vulnerability detection, vulnerability discovery, and vulnerability identification. Do not automatically treat every code-quality, testing, malware, or security paper as in scope: retain it only when its stated problem and evidence are relevant to the user's intended meaning of code detection.

Show the final query map briefly in the report, grouped as core, close, and adjacent terms. Use core and close terms for the main result set. Use adjacent terms to discover venues and methods, or label their papers as adjacent rather than presenting them as direct matches. Ask for clarification when one interpretation would substantially change the venues or paper set; otherwise state the assumption and proceed.

## Research approach

1. Begin with primary sources: paper landing pages or preprints, official repositories, project documentation, release notes, benchmark pages, and author/lab announcements. Use secondary reporting and community discussion to discover leads or add context, never as the sole support for a technical claim about a paper, tool, metric, security property, or benchmark result.
2. Search across relevant vocabulary: synonyms, abbreviations, task variants, and the names of leading methods or benchmarks. Check recent items alongside foundational work needed to explain why a development matters.
3. For each candidate, capture the publication or release date, authors or maintainers, the actual contribution, evidence of evaluation or use, limitations, and a direct source link.
4. For open-source projects, inspect repository activity, latest release, license, documentation, reproducibility signals, adoption indicators, and whether the code corresponds to the claimed research. Do not use stars alone as evidence of quality or maintenance.
5. Compare like with like. Keep separate categories for papers, codebases, benchmarks/datasets, and commercial products unless the user asks for a combined market scan.

## High-recall discovery and coverage

Default to a high-recall candidate set when the user wants to screen the results themselves. Include directly relevant, closely related, and plausibly adjacent papers, then label their relation rather than excluding borderline candidates early. When the user intends to delete candidates manually, report every verified candidate found in the declared coverage rather than silently reducing the paper set to a reading shortlist. Never claim completeness; describe the search coverage and known gaps.

Use both of these discovery passes before finalizing the paper set:

1. **Citation pass.** For every seed paper that directly addresses the topic, inspect its references for prior methods and inspect its later citations for follow-on methods, benchmarks, replications, and comparisons. Use a bibliographic index, publisher page, or paper reference list. Harvest method names, dataset names, and alternative task names, then search those names directly. Stop expanding a branch when newly found papers no longer add a distinct method, dataset, venue, ecosystem, or query term; record branches that could not be inspected.
2. **Ecosystem pass.** Build a compact coverage matrix from the topic's likely objects and settings—for example language/runtime (Java, C/C++, Python), artifact (source, binary, firmware, library/package, web application), and task framing (affected-version range, vulnerable-version identification, patch-presence analysis, vulnerability-inducing commit). Search each relevant combination with the core and close terms. Add a candidate if its title or abstract makes a credible semantic match; label it `direct`, `close`, or `adjacent`.
3. **Artifact-source pass.** Do not let the paper vocabulary determine the open-source set. When the topic has tools or implementations, search each plausible artifact surface independently: canonical forges, package registries, project sites, and documentation. Combine the core terms with workflow, interface, and user-goal terms. For LLM context compression, this includes `tool output compression`, `agent context management`, `CLI proxy`, `shell/log filtering`, `coding-agent token reduction`, and `MCP context`, in addition to `prompt`, `RAG`, and `KV-cache` compression. Inspect the project's own README or documentation before including it; record the platform and the boundary of what it compresses.
4. **Paper-artifact pass.** For every retained published paper, look for implementation and experimental artifacts through the official paper page, appendix, project page, author/lab page, and repository README. Classify each link as `official`, `author-affiliated`, `third-party reproduction`, or `not located`. Separately record the artifact role: `method code`, `training code`, `evaluation/experiment scripts`, `dataset/benchmark`, `model weights`, or `configuration/checkpoints`. Cite the evidence that establishes the association; do not infer it from a similar project name or shared topic. A paper without located code stays in the paper pool with `not located`, rather than being omitted.
5. **Community-signal pass.** When `community_sources=true`, target `max_community_sources` verified items rather than stopping after a few obvious results. Search the core and close query map in Chinese and English through more than one accessible search engine (such as Google and Bing), then perform platform-directed searches for engineering blogs, project write-ups, independent evaluations, conference/meetup notes, Zhihu, and public WeChat articles. Also search leading method, tool, benchmark, and project names discovered in the paper/project passes; this finds implementation experience that generic topic queries miss. Run at least one broad query, one engineering/workflow query, and one platform-directed Chinese query before declaring coverage exhausted. Prefer original author/organization posts and substantive technical analyses over aggregation, SEO pages, reposts, marketing copy, or posts with no attributable author/date. Record platform, author/organization when visible, publication date when visible, source URL, and a 1-2 sentence neutral summary of the technical claim, experience report, implementation note, or controversy. Deduplicate syndicated posts. A search-result snippet is only a discovery record: open the underlying page before reporting it. If a page is inaccessible or paywalled, omit it or label its limitation; do not summarize it from the snippet alone. If fewer than the requested limit survive verification, report the count and coverage gap instead of filling the table with weak matches.

Keep a candidate ledger with the query, citation, or artifact-source path that found each item, its relevance label, final status (`included`, `adjacent`, `excluded`, or `unverified`), and a short reason. An excluded item must be retained in the ledger when it is a plausible match, so the user can audit the boundary. Deduplicate only after the citation, ecosystem, and artifact-source passes are complete.

## Conference-published papers

Unless the user requests otherwise, include papers only after formal conference publication. Treat an accepted paper as published only when it can be verified in the conference proceedings, the publisher's digital library, DBLP, or an official conference program/proceedings page. Mark preprints, submissions, and acceptance announcements separately; do not mix them into the published-paper list.

Use [CCFDDL](https://ccfddl.com/) as the venue-discovery stage: identify the conferences it lists that are relevant to the user's topic, then capture each venue's official website and series name. Its public source repository stores conference records as structured YAML under `conference/`, so it can be traversed by category and venue when that is more reliable than parsing the rendered page. Do not treat CCFDDL as proof that an individual paper was published.

For every selected venue, run a separate paper-collection stage over the `paper_years` window (rolling from the research date, unless the user specifies calendar years). Locate each year's proceedings by following “past conferences,” “archive,” “proceedings,” or year-specific pages from the venue website. When that fails, search the publisher's digital library and DBLP. In high-recall mode, retain all direct, close, and plausibly adjacent candidates from the proceedings; verify their relation from the title, abstract, or full text as available.

For each retained paper, record conference series, edition year, title, authors, DOI or stable record, official proceedings/publisher/DBLP link, a one-sentence relevance note, and the result of the paper-artifact pass. Deduplicate records across sources by DOI first, then normalized title plus year. Report coverage by venue and year, explicitly flag incomplete or unavailable proceedings, and mark a current-year edition as partial when applicable.

## Source identity and venue ranking

Keep discovery, verification, and artifact sources visibly separate. Every reported item must state its source type, host/platform, direct link, and the role of that source (for example, official publication record, bibliographic metadata, code host, project documentation, or contextual report).

- **Papers:** report the conference name and year, publication source (official proceedings, publisher digital library, or DBLP), and the venue's CCF classification as `CCF A`, `CCF B`, `CCF C`, `Non-CCF`, or `Unknown`. Cite the ranking source and its applicable version/date when available. If CORE, THCPL, or another system is present, show it in a separate field; never replace, combine, or infer a CCF grade from another ranking system.
- **Open-source projects:** classify the canonical code source as `GitHub`, `GitLab`, `Gitee`, `Bitbucket`, `official self-hosted forge`, `package registry`, `project website`, or `other`. Give the canonical repository URL and list mirrors separately. Do not call a project “GitHub” merely because an article links to it. For each canonical forge record, capture a time-stamped snapshot of stars, forks, latest commit or release, license, and issue/PR signal when available. If the user asks for a project shortlist or top-N, rank up to the requested number using relevance first and then visible ecosystem signals; show the metrics and retrieval time. Stars and forks are popularity signals, not evidence of correctness, security, or maintenance.
- **Other sources:** label each as `official venue website`, `publisher/proceedings`, `bibliographic index`, `preprint archive`, `project documentation`, `benchmark/dataset portal`, `organization/lab announcement`, `technical media`, or `other`. Use them only for the claims their role supports.
- **Technical-community sources:** keep them as a third result class, separate from papers and open-source projects. Label host/platform precisely, for example `Google search discovery`, `Bing search discovery`, `engineering blog`, `Zhihu`, `WeChat public article`, `conference/meetup note`, or `technical media`. The report must link the underlying article rather than a search result page. Attribute opinions to the author/source; do not turn a community claim into a verified fact without primary evidence. Distinguish `implementation experience`, `practitioner opinion`, `independent test`, `announcement/explainer`, and `ecosystem signal`.

When source records conflict, prefer the official proceedings or canonical repository for the item itself, retain the conflicting link if it is useful, and explain the discrepancy briefly. Do not silently collapse different source types into a single generic “source” field.

## Synthesis

Lead with a short answer to “what changed and why it matters.” Organize detailed findings by theme, capability, or timeline—whichever makes the topic clearest. For every material claim, attach a direct Markdown link to its source.

For papers, give title, date/year, conference and CCF classification, authors or organization, contribution, evidence, caveats, publication source, and linked implementation/experiment artifacts with their association and role. Put the artifact fields directly in the same row as each paper candidate; do not emit a separate paper-artifact table unless the user explicitly requests one. Leave all artifact cells blank when no association is verified. For open-source projects, give project, source platform, canonical repository, language/ecosystem where relevant, stars, forks, metric retrieval time, maintenance/release signal, license, purpose, maturity, caveats, and source. If a platform does not expose a metric, write `unavailable` rather than estimating it. For community evidence, provide a separately headed compact table with source/platform, date, source type, relation to the topic, neutral summary, caveat, and direct link. Do not rank it with papers or projects.

Label confidence and uncertainty. Explain disagreements in benchmark results, unavailable code/data, preprint status, stale repositories, and possible conflicts of interest. Treat missing information as unknown rather than filling gaps with assumptions.

End with:

- a compact comparison table when comparing three or more items;
- the candidate ledger and venue/ecosystem coverage summary when high recall was requested;
- notable gaps and open questions;
- practical next steps appropriate to the user's goal, such as papers to read, repositories to evaluate, or experiments to run.

Use the reporting structures in [references/reporting-templates.md](references/reporting-templates.md) when the user asks for a formal report, a recurring update, or a comparative shortlist.

## Freshness and attribution

Research may change quickly. Verify dates, repository state, releases, licenses, and authorship at the time of the request. Cite precise sources near the claims they support. Never fabricate citations, metrics, project activity, or paper results.

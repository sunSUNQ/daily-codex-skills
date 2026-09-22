# Usage and tuning

## Quick start

In Codex, invoke `$topic-progress-research` and state the topic. The skill returns a published-paper candidate pool, paper-linked code and experiment fields in the same rows, a separately ranked open-source project list, and a clearly separated community/technical-media signal summary.

Example:

```text
Use $topic-progress-research to research vulnerability impact-range identification.
```

## Defaults

| Setting | Default | Effect |
|---|---:|---|
| `paper_years` | 5 | Search formally published conference papers in a rolling five-year window. |
| `project_recency` | 12 months | Prefer independently discovered projects with activity in this window. |
| `max_projects` | 20 | Return at most 20 independently ranked projects. |
| `published_only` | true | Exclude preprints and submissions; label Findings and workshops separately. |
| `include_close` | true | Keep direct, close, and adjacent candidates for manual filtering. |
| `community_sources` | true | Add a third, separate source class for technical blogs, Zhihu, public WeChat articles, and other community signals. |
| `max_community_sources` | 10 | Cap the deduplicated community source table. |

## Override examples

Natural language and parameter form are equivalent.

```text
Research software vulnerability detection papers from the last 10 years.

Research context compression; paper_years=10; max_projects=30.

Research RAG compression for calendar years 2020-2025; published_only=true; include_close=false.

Research context compression; community_sources=true; max_community_sources=15.
```

To change the published default for all future runs, edit the values in the `## Request parameters` table in `SKILL.md`. Ordinary users should prefer per-request overrides so the shared skill remains predictable.

## Output rules

- Papers are verified from proceedings, publisher pages, DBLP, or official programs.
- CCF grades are reported only from an identified CCF source; an absent grade is left as unknown.
- Code, training, evaluation, data, weights, and configuration artifacts are attached to the corresponding paper row. Unverified associations remain blank.
- Open-source projects state their canonical platform. GitHub stars, forks, license, and activity are point-in-time metadata, not quality scores.
- Community/technical-media sources are presented in their own table with a direct article link, platform, date, neutral summary, and caveat. Search engines are used to discover pages; their snippets are not treated as evidence.
- High-recall output is a screening set, not a claim of completeness.

# Reporting templates

Use only the sections that help answer the request. Do not force a template when a brief response is more useful.

## Dual-format delivery

For a requested research report, write the Markdown version first and use it as the source of truth for the PDF. Both files must contain the same complete result set and direct source links; the PDF is not a short preview. Use a shared basename such as `llm-context-compression-report.md` and `llm-context-compression-report.pdf`.

## Landscape brief

```markdown
# [Topic]: recent progress ([time window])

## Topic interpretation
- **Core:** [user's original term and exact equivalents]
- **Close:** [synonyms, narrower/broader terms]
- **Adjacent:** [related tasks, clearly labeled]

## Bottom line
[2–5 sentences on the important change, maturity, and remaining uncertainty.]

## Key developments

### [Theme]
- **[Paper/project]** — [what changed, supporting evidence, caveat]. [Source](URL)

## Published-paper candidate pool
Leave implementation and experiment fields blank when no verified association exists. Metrics are a snapshot at [retrieval time].

| Venue / year | CCF grade | Work | Authors | Relevance (direct / close / adjacent) | Code / experiment repository | Association | Artifact role | Stars / forks | Publication source | Source |
|---|---|---|---|---|---|---|---|---|---|---|

## Venue coverage
| Venue | Five-year window | Proceedings coverage | Gaps / caveats |
|---|---|---|---|

## High-recall coverage
| Ecosystem / artifact | Task framing searched | Query and citation coverage | Notes / gaps |
|---|---|---|---|

## Candidate ledger
| Candidate | Discovery path | Relevance | Status | Reason / caveat | Source |
|---|---|---|---|---|---|

## Open-source projects (top-N when requested)
Metrics are a snapshot at [retrieval time], not a quality score.

| Rank | Project | Source platform | Canonical repository | Stars | Forks | Latest activity / release | License | What it offers | Maturity / caveat |
|---|---|---|---:|---|---|---|

## Other evidence
| Item / claim | Source type | Host | Evidence role | Source |
|---|---|---|---|---|

## Technical-community signals
Community items are discovery/context material, not co-equal evidence with a published paper or a canonical repository. Link the underlying page, never only a search result.

| Source / author or organization | Platform / source type | Date | Relation | Neutral technical summary | Caveat | Direct link |
|---|---|---|---|---|---|---|

## Open questions and next steps
- [Evidence-backed uncertainty or a practical evaluation step.]
```

## Adoption shortlist

```markdown
## Shortlist for [goal]
| Option | Best fit | Evidence | Operational considerations | Watch-outs | Source |
|---|---|---|---|---|---|

### Recommendation
[State the recommendation, assumptions, and the lowest-cost validation step.] 
```

## Periodic update

```markdown
# [Topic] update — [date]

## What is new since [previous cutoff]
- [Item and why it matters.] [Source](URL)

## Signals to watch
- [Upcoming release, benchmark, conference, or maintenance concern.]

## Changed assessment
[Only describe a shift in conclusion when evidence supports it.]
```

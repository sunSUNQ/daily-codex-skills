# Evaluation cases

Run these cases before publishing or after changing research, ranking, or output instructions. Check the listed observable invariants rather than exact wording or item counts.

## 1. Vulnerability impact-range identification

Prompt:

```text
Use $topic-progress-research to research vulnerability impact-range identification papers and projects.
```

Pass criteria:

- Shows a query map covering vulnerable-version identification, affected-version range, patch presence, and related close terms.
- Gives each paper a verified venue/year, publication source, and CCF field.
- Keeps plausible candidates in a ledger instead of silently dropping them.
- Attaches verified code/experiment repositories to their paper rows and leaves unverified artifact cells blank.

## 2. Context compression

Prompt:

```text
Use $topic-progress-research to research LLM context compression.
```

Pass criteria:

- Separates prompt/RAG/soft-memory/KV-cache compression from agent tool-output compression.
- Includes both paper-linked repositories and independently discovered agent tools.
- The independent-project list has at most 20 entries by default and includes metric retrieval time, stars, forks, activity, and license when available.

## 3. Ten-year override

Prompt:

```text
Research code clone detection; paper_years=10; max_projects=30; include_close=false.
```

Pass criteria:

- Reports the effective parameter values.
- Uses a rolling ten-year paper window and a project list capped at 30.
- Does not present adjacent papers as direct matches.

## 4. No verified implementation

Prompt:

```text
Research a narrowly defined published topic and include paper-linked code only when the association is verified.
```

Pass criteria:

- Retains papers that have no located implementation.
- Leaves the corresponding repository, association, artifact role, and metrics cells blank.
- Does not substitute a similarly named or third-party project without marking its association.

## 5. High-recall community coverage

Prompt:

```text
Research LLM context compression; community_sources=true; max_community_sources=20.
```

Pass criteria:

- Runs broad topic, engineering/workflow, and Chinese platform-directed discovery queries, and expands with method or project names.
- Returns up to 20 deduplicated, underlying-article links in a third source table rather than stopping at a small handful of obvious posts.
- Labels each item with its platform/type, date when visible, a neutral summary, and caveat.
- Does not treat a search-result snippet, repost, or community opinion as primary evidence for paper or code claims.

## 6. Dual-format report

Prompt:

```text
Create a research report on LLM context compression.
```

Pass criteria:

- Produces a Markdown and a PDF report with the same stable basename.
- Markdown is complete and editable; PDF preserves the complete candidate tables and direct links rather than using an excerpt.
- The PDF is rendered and inspected before delivery.

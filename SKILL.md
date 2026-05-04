---
name: citation-adjuster
description: Audit and revise academic in-text citation placement. Use when Codex needs to check or improve citation insertion in manuscripts, literature reviews, essays, theses, dissertations, grant text, or scholarly drafts, especially for citation dumping, stacked citations at sentence ends, weak claim-source alignment, distant citations, over-citation, missing citation anchors, or poor synthesis across APA/Harvard author-date, numeric, or footnote citation styles.
---

# Citation Adjuster

## Overview

Use this skill to audit and revise how citations are inserted into academic prose. The goal is citation integrity: each citation should support a clear, local, verifiable claim without adding unsupported literature or pretending to have checked sources that are not provided.

Default to a medium-strict review. Reduce obvious citation dumping and unclear attribution, but preserve legitimate multi-source synthesis when several sources support the same precise claim.

## Non-Negotiable Rules

- Do not invent citations, sources, findings, page numbers, methods, samples, or conclusions.
- Do not claim that a source supports a statement unless the user provides enough source content to verify that support.
- When only manuscript text is available, judge citation structure, placement, and surface alignment; label deeper source-support judgments as "needs source check".
- Preserve the manuscript's citation style unless the user asks to convert styles.
- Prefer minimal edits that improve citation placement and claim clarity before stronger rewrites.
- Keep technical terms, variables, methods, numbers, and existing citations intact unless moving or grouping citations is necessary for the requested adjustment.
- If a citation appears fabricated, malformed, missing from the reference list, or impossible to verify, flag it instead of repairing it by guesswork.

## Workflow

1. Identify the manuscript type, field, citation style, and user goal. If not provided, assume a general academic manuscript and preserve the visible citation style.
2. Segment the text by paragraph, then by sentence or claim unit. Keep paragraph labels stable.
3. For each claim unit, identify the main verifiable claim and the citation or citations attached to it.
4. Apply the rubric in `references/citation-rubric.md` when reviewing multi-citation sentences, literature review paragraphs, or any passage with possible citation dumping.
5. Judge citation placement with these questions:
   - Is the citation close to the exact claim it supports?
   - Does the sentence contain one claim or several claims?
   - Are multiple citations supporting the same precise claim, or different parts of the sentence?
   - Is the citation being used as evidence, background, method attribution, comparison, or definition?
   - Is the passage synthesizing sources, or merely stacking them?
6. Mark each issue with risk `0-3`, confidence, and whether source content is needed for verification.
7. Revise only as far as the evidence allows: move citations closer to claims, split overpacked sentences, group sources by role, convert vague source piles into narrative attribution, or flag unsupported claims.

## Output Format

For audit plus revision, use this compact structure:

```markdown
整体判断：...

| 位置 | 风险 | 置信度 | 问题 | 原因 | 建议 | 最小改写版 |
|---|---:|---|---|---|---|---|
| P1 S2 | 2 | high | citation dumping | 句子含三个论断，但所有文献集中在句末。 | 拆句并把文献贴近对应论断。 | ... |
```

If the user provides source abstracts, notes, PDFs, or a reference list, add a `source check` note for claims that can or cannot be verified. If sources are not provided, say "无法仅凭正文确认该文献是否实际支持该论断".

For revision-heavy requests, after the table provide:

```markdown
修改版：
...

Change notes:
- ...
```

## Common Fixes

- Split a sentence when it contains multiple claims with one large citation cluster.
- Move a citation immediately after the clause it supports when the sentence contains mixed claims.
- Replace a broad citation pile with grouped synthesis, such as experimental studies, longitudinal studies, qualitative studies, meta-analyses, or theoretical sources.
- Use narrative attribution when one source contributes a specific finding or contrast.
- Keep multiple citations together only when they directly support the same narrow claim.
- Flag claims that need citations instead of borrowing nearby citations that may not support them.

## Reference

Read `references/citation-rubric.md` for the full scoring rubric, multi-source rules, and examples for author-date, numeric, and footnote styles.

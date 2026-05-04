# Citation Adjustment Rubric

Use this reference when auditing citation placement, citation density, and claim-source alignment in academic prose.

## Core Standard

A citation is reasonable only when a reader can answer: "Which exact claim does this source support, and why is it placed here?"

Assess five dimensions:

1. Placement proximity: the citation sits close to the claim it supports.
2. Claim focus: the cited sentence or clause has one clear verifiable claim, or clearly separates several claims.
3. Source directness: the cited source is presented as supporting only what it can plausibly support.
4. Citation economy: the number of sources fits the claim type.
5. Synthesis quality: multiple sources are related, grouped, compared, or contrasted instead of merely listed.

## Risk Levels

| Risk | Meaning | Typical action |
|---:|---|---|
| 0 | Reasonable citation placement. | Leave unchanged or make normal copy edits only. |
| 1 | Minor redundancy, slightly distant citation, or a sentence that could be clearer. | Suggest moving, trimming, or clarifying citations. |
| 2 | Clear citation dumping, overpacked claims, weak alignment, or unclear source roles. | Recommend splitting sentences, regrouping sources, or adding source-specific attribution. |
| 3 | High-risk mismatch, false support, unverifiable support presented as verified, or citations masking unsupported claims. | Flag strongly; do not rewrite as verified without source evidence. |

Assign confidence as `low`, `medium`, or `high`. Use `high` only when the issue is visible from the text itself, such as five citations attached to a broad multi-claim sentence. Use `medium` or `low` when the judgment depends on source content not provided.

## Citation Quantity Heuristics

These are defaults, not rigid rules:

- Definition or original concept: usually one original or authoritative source.
- Specific empirical finding: usually one direct study, sometimes two corroborating studies.
- Method, instrument, dataset, or model: cite the original or standard source.
- Established pattern across studies: several sources can be appropriate, but group them or cite a review/meta-analysis when available.
- Contested claim: cite both sides or state the disagreement; do not stack only supportive sources.
- Literature review overview: multiple citations are acceptable when the sentence explicitly names the shared pattern or groups the studies by role.

Four or more citations in one parenthesis is not automatically wrong, but it is a review trigger. It is reasonable only when the sentence makes one narrow claim supported by all listed sources, or when the prose groups the sources by method, context, finding, or position.

## Multi-Source Rules

Keep multiple citations together only if they support the same precise claim.

Split or regroup when:

- The sentence contains different outcomes, constructs, populations, time periods, methods, or mechanisms.
- One citation supports the first clause and another supports the second clause.
- A citation cluster appears after broad phrases such as "many studies show", "previous research suggests", or "the literature demonstrates" without naming the specific pattern.
- The sources likely play different roles, such as theory, method, empirical evidence, and review.
- Removing one source would not change the evidence chain, which suggests padding or redundancy.

Prefer these fixes:

- Clause-level placement: put the citation after the exact clause it supports.
- Sentence splitting: give each major claim its own citation.
- Source grouping: organize citations by method, population, finding, or position.
- Narrative attribution: name a source when its specific finding matters.
- Verification flag: mark "needs source check" when the support cannot be confirmed.

## Common Problems

### Citation dumping

Several sources are stacked at the end of a broad or multi-claim sentence.

High-risk pattern:

> Digital feedback improves motivation, self-regulation, engagement, and achievement (A, 2019; B, 2020; C, 2021; D, 2022; E, 2023).

Better:

> Digital feedback has been associated with higher student motivation in several classroom studies (A, 2019; B, 2020). Work on self-regulated learning links feedback timing to planning and monitoring behaviors (C, 2021). Evidence for achievement gains is more mixed, with D (2022) reporting short-term test improvements and E (2023) finding no durable effect.

### Distant citation

The citation appears after a sentence or paragraph even though it only supports one earlier clause.

Fix by moving the citation closer or splitting the sentence.

### Unsupported borrowing

A nearby citation is used to cover a new claim that the source may not support.

Fix by adding "needs citation" or asking for source evidence. Do not reuse an adjacent citation by guesswork.

### Weak synthesis

The paragraph lists sources one by one or piles them into parentheses without showing their relationship.

Fix by grouping sources around a shared finding, method, population, theoretical position, or disagreement.

## Examples By Style

### Author-date

Problem:

> Feedback can improve motivation, self-regulation, and performance (Kim, 2019; Lopez, 2020; Singh, 2021; Zhao, 2023).

Audit:

- Risk: 2
- Issue: one citation cluster covers three distinct outcomes.
- Fix: split by outcome or identify which studies support each outcome.

Revision:

> Feedback has been linked to motivation in classroom settings (Kim, 2019; Lopez, 2020). Singh (2021) connects feedback timing with self-regulation, while Zhao (2023) reports a narrower effect on short-term performance.

### Numeric

Problem:

> Remote monitoring reduces admissions, improves adherence, and lowers costs [1-6].

Audit:

- Risk: 2
- Issue: bracket range hides which sources support each outcome.
- Fix: separate admissions, adherence, and cost claims.

Revision:

> Remote monitoring has been associated with fewer admissions in studies of heart failure patients [1,2]. Evidence for adherence is reported separately in mobile-app interventions [3,4]. Cost reductions are less consistently supported and should be tied to the specific economic evaluations [5,6].

### Footnote

Problem:

> Early modern trade networks changed legal practice, urban finance, and diplomatic communication.^1

Audit:

- Risk: 1-2 depending on the footnote content.
- Issue: one footnote may be too broad if it does not cover all three changes.
- Fix: verify the footnote or split the claim.

Revision:

> Early modern trade networks changed urban finance.^1 Their effects on legal practice and diplomatic communication require separate support unless the same source directly covers those claims.

## Source-Availability Policy

When the user provides only正文:

- Judge visible structure, citation density, and placement.
- Use "likely", "appears", or "needs source check" for source-support claims.
- Do not say a citation is wrong solely because many sources appear together.

When the user provides abstracts, notes, PDFs, or a reference list:

- Match each claim to the provided source evidence.
- Flag overclaims, missing support, source-role confusion, and contradictions.
- Distinguish "source does not support this" from "support not shown in provided material".

## Output Template

Use this table for detailed audits:

| 位置 | 风险 | 置信度 | 问题 | 原因 | 建议 | 最小改写版 |
|---|---:|---|---|---|---|---|
| P1 S1 | 2 | high | citation dumping | 多个论断共用一个大引文簇。 | 拆句并按论断分配引用。 | ... |

For short requests, a concise bullet list is acceptable, but still include risk, reason, and a concrete revision direction.

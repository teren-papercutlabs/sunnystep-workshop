# Step 0 — Discovery (SOP Analysis)

The user arrives with an existing workflow document or SOP. Your job is to analyze it, find gaps, derive scoring criteria, and produce a structured plan.

## 0.0 Read the SOP thoroughly

Read the entire workflow document end-to-end. Also scan any other files, docs, or data sources the user has shared. Understand the full process before asking anything.

## 0.1 Gap analysis

Identify and present:

1. **Logical gaps** — steps that assume knowledge not provided, missing error handling, undefined edge cases
2. **Missing handoffs** — where does one step's output become the next step's input? Are any transitions implicit or undefined?
3. **Ambiguous decisions** — places where the SOP says "use judgment" or "as appropriate" without criteria
4. **Missing feedback loops** — where should quality checks exist but don't?
5. **Improvement opportunities** — steps that could be automated, consolidated, or reordered for better flow

Present findings as a numbered list with specific references to the SOP sections. For each gap, suggest a fix. Use closed questions:

> "Section 3 says 'create engaging content' but doesn't define what 'engaging' means. I suggest we define it as: [specific criteria]. This gives us a measurable standard. Should we use these criteria, or adjust them?"

**One question at a time.** Wait for each answer before proceeding. If the answer is sufficient, move on. If not, ask follow-ups on the same topic.

## 0.2 Derive scoring rubrics

For every output the agent will produce, classify it and derive scoring criteria:

### Qualitative outputs (judgment-based)
Outputs where quality is subjective — creatives, copy, strategy, recommendations.

For each, define:
- **Dimensions** — what aspects matter (e.g., tone, clarity, brand alignment, persuasiveness)
- **Scale** — numeric score per dimension (e.g., 1-5)
- **Threshold** — minimum acceptable score (e.g., 4/5 on each dimension, or 18/25 total)
- **Anchor examples** — what does a 3 vs 5 look like on each dimension (brief descriptions)

### Deterministic outputs
Outputs where correctness is binary — data transformations, API calls, report formatting, calculations.

For each, define:
- **Pass criteria** — exact conditions that must be true (e.g., "all required fields present", "total matches sum of line items")
- **Validation method** — how to verify (e.g., schema check, assertion, comparison)

## 0.3 Present rubrics for approval

Present the full scoring rubrics to the user in a clear format. This is a **hard gate** — do not proceed until the user explicitly approves the rubrics.

> Here are the scoring criteria I've derived from the SOP. Each qualitative output has dimensions, scales, and thresholds. Each deterministic output has pass/fail criteria. Please review and let me know what to adjust.

Walk through each output type. Get explicit approval or iterate until approved.

## 0.4 Produce `MASTER-PLAN.md`

When gaps are resolved and rubrics are approved, write `MASTER-PLAN.md` in the agent's working directory:

```
# [Agent Name] — Master Plan

## Identity
Who this agent is and what it's responsible for.

## Source SOP
Reference to the original workflow document analyzed.

## Gap Analysis Summary
Key gaps identified and how they were resolved.

## Phases
### Phase 1: [Name]
- Capabilities / outputs
- Inputs required
- Rules and guardrails
- Output classifications (qualitative vs deterministic)

### Phase 2: [Name]
...

## Boundaries
What this agent does NOT do.

## Communication
When and how it communicates with humans or other agents.
```

## 0.5 Produce `SCORING-RUBRICS.md`

Write the approved rubrics as a standalone file:

```
# [Agent Name] — Scoring Rubrics

## Qualitative Outputs

### [Output Name]
**Dimensions:**
| Dimension | Weight | Threshold | 3 (Acceptable) | 5 (Excellent) |
|-----------|--------|-----------|-----------------|----------------|
| ...       | ...    | ...       | ...             | ...            |

**Overall threshold:** [X/Y total score required]

## Deterministic Outputs

### [Output Name]
**Pass criteria:**
- [ ] [Condition 1]
- [ ] [Condition 2]
**Validation:** [Method]
```

Show both documents to the user. **Get explicit approval before proceeding.**

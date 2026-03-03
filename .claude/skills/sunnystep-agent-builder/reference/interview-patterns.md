# Interview Patterns

Use these patterns to ask **closed questions with recommendations**.

---

## Pattern 1 — SOP gap: undefined quality standard

- **Question**: "Section 4 says 'create high-quality visuals' but doesn't define what 'high-quality' means. I suggest we score visuals on: brand alignment, composition, message clarity, and audience relevance — each on a 1-5 scale with a minimum of 4 per dimension. This gives us a rubric the scoring agent can use. Should we use these four dimensions, or are there others that matter more?"
- **Suggestion + rationale**: Four measurable dimensions cover the main quality axes.
- **Alternatives**: Add/remove dimensions based on business priorities.
- **Recommendation**: Start with four, adjust after Phase 1.

## Pattern 2 — SOP gap: missing error handling

- **Question**: "The workflow doesn't specify what happens when the API returns an error during content scheduling. I suggest: retry once after 30 seconds, then flag for manual review if it fails again. Alternative is immediate manual escalation on first failure. I recommend retry-once for fewer interruptions. Use retry-once?"
- **Suggestion + rationale**: Reduces unnecessary escalations.
- **Alternatives**: Immediate escalation.
- **Recommendation**: Retry-once then escalate.

## Pattern 3 — Scoring threshold calibration

- **Question**: "For ad copy, I've set the threshold at 4/5 on each of tone, clarity, CTA strength, and brand voice. That means 16/20 minimum. This is fairly strict — a 3 on any dimension triggers a rewrite. Alternative is 3.5 average (14/20), which allows one weak dimension if others compensate. I recommend 16/20 for launch quality, then we can relax after seeing real performance. Keep 16/20?"
- **Suggestion + rationale**: Higher bar ensures quality at launch.
- **Alternatives**: Lower threshold (14/20).
- **Recommendation**: 16/20 initially.

## Pattern 4 — Output classification ambiguity

- **Question**: "The SOP lists 'campaign performance report' as an output. Reports can be either deterministic (just formatting numbers from a data source) or qualitative (includes narrative analysis and recommendations). Which is this? I suggest treating the data tables as deterministic (pass/fail on accuracy) and the narrative sections as qualitative (scored on insight quality and actionability). Split it that way?"
- **Suggestion + rationale**: Different parts of the same output can have different quality gates.
- **Alternatives**: Treat entire report as one type.
- **Recommendation**: Split by section.

## Pattern 5 — Iteration cap

- **Question**: "For the scoring loop on creative outputs, I suggest a maximum of 3 attempts before escalating to you. This balances quality improvement against diminishing returns — if it can't score well in 3 tries, the issue is likely in the rubric or brief, not the execution. Alternative is 5 attempts for more persistence. I recommend 3. Keep 3?"
- **Suggestion + rationale**: 3 iterations catches most issues without wasting cycles.
- **Alternatives**: 5 iterations.
- **Recommendation**: 3 iterations.

---

## Prompt skeleton you can reuse

> "For [decision], I suggest [option] because [reason]. Alternative is [alt] if [condition]. I recommend [option/recommendation]. Does that match your intent, or should we adjust [specific parameter]?"

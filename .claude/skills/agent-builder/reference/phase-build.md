# Steps 2–5 — Phase Build Cycle

Repeat this full cycle for each phase in REFERENCE.md.

## Step 2 — Phase Entry

Complete all checks before building anything.

### 2.1 Clarification interview (closed questions only)

**One question at a time.** For every ambiguity, ask a closed question in plain chat (never use AskUserQuestion) with:
1. Your suggestion (based on the SOP, rubrics, and what you've learned so far)
2. Pros and cons
3. Your recommendation

Wait for the answer before asking the next question. If sufficient, move on. If not, ask follow-ups on the same topic.

Continue until ambiguity is exhausted. Summarize decisions and get confirmation before building.

### 2.2 Input access verification

List every required input for the phase and verify access now:
- Files, documents, sheets (exact locations)
- Credentials / API keys
- External systems / data sources
- Upstream outputs from earlier phases

**API documentation rule**: If the phase involves calling any external API, send a subagent to fetch and read the API documentation BEFORE writing any code. Verify: correct endpoints, required parameters, authentication method, response shape. Do not guess API behavior — read the docs first.

If missing, mark `BLOCKED (reason)` and ask user: wait, use sample data, or continue with reduced scope.

### 2.3 Classify outputs for this phase

For each output this phase produces, confirm from SCORING-RUBRICS.md:
- **Qualitative** → will use the scoring loop (Step 3b)
- **Deterministic** → will use pass/fail validation (Step 3a)

Present the classification to the user for confirmation before proceeding.

### 2.4 Decompose into testable parts

Break the phase into parts where each has a demonstrable output.

> I'm breaking Phase [N] into [X] parts:
> - Part A: [name] — output: [what you can verify] — type: [qualitative/deterministic]
> - Part B: [name] — output: [what you can verify] — type: [qualitative/deterministic]
> I'll build and verify each one before moving to the next. Sound right?

---

## Step 3a — Build deterministic parts

For parts that produce deterministic outputs:

1. **Research first** — if this part calls an external API, send a subagent to read the API docs.
2. **Build it** — smallest complete version.
3. **Run pass/fail validation** — check against the criteria in SCORING-RUBRICS.md. It either works or it doesn't.
4. **If fail** — fix the issue and re-validate. This is debugging, not iteration.
5. **Show the output** — walk through the result in plain language.
6. **Collect feedback** — "Does this match what you'd expect?" Iterate until approved.
7. **Commit** — small, descriptive commit before moving on.
8. **Update REFERENCE.md** — mark part `DONE`.

---

## Step 3b — Build qualitative parts (scoring loop)

For parts that produce qualitative/judgment-based outputs:

1. **Research first** — if this part calls an external API, send a subagent to read the API docs.
2. **Build it** — smallest complete version that produces the output.
3. **Produce one output** — generate a concrete example.
4. **Dispatch Opus scoring subagent** — send the output + the relevant rubric from SCORING-RUBRICS.md to a scoring subagent (model=opus). The scoring subagent:
   - Evaluates each dimension from the rubric
   - Returns a score per dimension with brief justification
   - Returns an overall score
   - If below threshold: returns specific, actionable feedback on what to improve
5. **Check threshold:**
   - **Meets threshold** → proceed to step 6
   - **Below threshold** → feed the scoring feedback back into the builder, regenerate the output, and return to step 4. Maximum 3 iterations. If still below threshold after 3 attempts, surface to user with scores and ask for guidance.
6. **Show the output + scores** — present the final output along with its rubric scores in plain language.
7. **Collect feedback** — "This scored [X/Y] on the rubric. Does this match what you'd expect?" Iterate until approved.
8. **Commit** — small, descriptive commit before moving on.
9. **Update REFERENCE.md** — mark part `DONE`.

### Scoring subagent prompt template

```
You are a quality scoring agent. Evaluate the following output against the provided rubric.

## Output to evaluate
[the output]

## Rubric
[paste relevant section from SCORING-RUBRICS.md]

## Instructions
1. Score each dimension (1-5) with a one-sentence justification
2. Calculate the overall score
3. State whether it meets the threshold
4. If below threshold: provide specific, actionable feedback — what exactly should change and why
5. If meets threshold: confirm pass and note any minor improvement opportunities

Return your evaluation as structured text.
```

### Parallel subagents (when applicable)

If two or more parts are independent, you may parallelize:
- Only after decomposition is approved.
- One part per subagent with clear output contract.
- Qualitative parts must include the scoring loop in their subagent instructions.
- One coordinator stays responsible for REFERENCE.md and user communication.
- Do not parallelize tightly coupled logic.
- Merge, verify, present single coherent result. Commit after each merge.

---

## Step 4 — Phase integration test

When all parts are `DONE`:

1. Run end-to-end test with realistic input.
2. For qualitative outputs: run the scoring loop on the integrated result (not just individual parts).
3. Show results in plain language. Walk through what happened and why, including scores.
4. Get approval.
5. Update REFERENCE.md phase to `DONE`.
6. Commit.

---

## Step 5 — Phase exit

1. Write `PHASE-[N]-SUMMARY.md`:
   - What was built
   - Decisions made during interview
   - Scoring results (final scores for qualitative outputs)
   - Open items (if any)

2. Ask: "Ready to move to Phase [N+1]?"

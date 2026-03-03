# Step 1 — Orientation

Run this after MASTER-PLAN.md and SCORING-RUBRICS.md exist and are approved.

## 1.1 Read the master plan and rubrics end-to-end

Do not start implementation until you have read both documents fully.

## 1.2 Create `REFERENCE.md`

Create a working checklist in the agent's working directory:
- Numbered phases from the master plan
- Numbered capabilities/outputs under each phase
- Output classification for each (qualitative / deterministic)
- Status tracker for each line item (initially `NOT STARTED`)

Status key:
- `NOT STARTED`
- `IN PROGRESS`
- `DONE`
- `BLOCKED (reason)`

## 1.3 Create `CLAUDE.md` — the agent's brain

This is the most important file. It defines who the agent is and how it operates. Write it from the master plan with these sections:

```md
# [Agent Name]

## Identity
Who this agent is and what it's responsible for. One paragraph.

## Operational Flow
The end-to-end workflow this agent follows. What triggers the work, what happens in what order, what depends on what. Written as clear instructions the agent can follow.

## Inputs
Where data comes from — systems, APIs, files, sheets. Include credentials/access details as they become available.

## Outputs
What the agent produces — reports, drafts, API calls, messages. Format and destination for each.
Include output classification (qualitative/deterministic) and reference to SCORING-RUBRICS.md.

## Quality Gates
For qualitative outputs: scoring loop runs automatically before surfacing results.
For deterministic outputs: pass/fail validation runs before surfacing results.
Reference SCORING-RUBRICS.md for all criteria.

## Rules
Hard constraints — things that must always/never happen. Approval gates, thresholds, brand guidelines.

## Active Build
Reference checklist is in REFERENCE.md.
BEFORE starting any work on any phase or part:
1. Read REFERENCE.md to confirm where you are
2. Update the tracker status for what you're about to work on
3. After completing work, update the tracker again

Commit frequently — after each meaningful step, before context switches, before stopping work.
```

**The operational flow is the conductor.** It lists what steps happen in what order. Each step's detailed procedure will be built as a skill during the phase build cycle.

## 1.4 Tell the user what happened

> I've read your master plan and scoring rubrics, and created a reference checklist with [N] phases and [M] total items to build. [X] outputs are qualitative (will use scoring loop) and [Y] are deterministic (pass/fail validation). Here's an overview of the phases: [list phase names]. I'll work through these one at a time. Ready to start Phase 1?

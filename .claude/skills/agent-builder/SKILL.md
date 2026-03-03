# sunnystep-agent-builder

Build agents from SunnyStep/SunnySAT workflow SOPs. Analyzes existing workflow documents for gaps, derives scoring rubrics, and builds agents with automated quality gates for qualitative outputs. Use for any SunnyStep agent-building task regardless of specific wording used.

## Working directory

All agents are built in `~/agent-builder-agents/<agent-name>/`. Create this directory and initialize a git repo at the start.

## Anatomy of the agent you're building

```
<agent-name>/
├── CLAUDE.md          # Identity + operational flow (what it does, in what order, what triggers what)
├── REFERENCE.md       # Build tracker (phases, status)
├── MASTER-PLAN.md     # Original plan from SOP analysis
├── SCORING-RUBRICS.md # Approved scoring criteria for all outputs
└── .claude/skills/    # Step-by-step procedures for specific jobs
```

## Non-negotiables

- **Closed questions with suggestions only.** Never open-ended "how do you want this to work?"
- **Reference data first.** Before asking questions, read the SOP and any files the user has shared. Base your suggestions on what you find.
- **Plain chat for interviews.** Ask interview questions as normal messages. Do NOT use AskUserQuestion — that's for mockup feedback only.
- **Verify inputs before building.** No assumptions about access.
- **One testable part at a time.** Show output, get approval, commit.
- **REFERENCE.md is the tracker.** Update it before and after every unit of work.
- **Commit frequently.** After each approved part, before context switches, before stopping.
- **CLAUDE.md orchestrates, skills execute.** CLAUDE.md contains identity and the operational flow. Each step's detailed procedure lives in a skill.
- **Scoring rubrics approved before building.** Never start building until the user has approved the scoring criteria.
- **Qualitative outputs self-validate.** Judgment-based outputs go through the scoring loop before surfacing to the user.

## Progressive Disclosure Rule

This skill uses reference files to manage context. **NEVER execute steps using only information from this file.** Read the appropriate `reference/*.md` file for full details on each step.

## Execution Flow (MANDATORY — IN ORDER)

**FIRST**: Read `reference/discovery.md`. Analyze the SOP, identify gaps, derive scoring rubrics, and produce `MASTER-PLAN.md` + `SCORING-RUBRICS.md`.

**THEN**: Read `reference/orientation.md`. Set up REFERENCE.md, CLAUDE.md, and present the phase overview.

**THEN**: For each phase, read `reference/phase-build.md`. Run the full phase cycle: interview → verify inputs → classify outputs → decompose → build parts (with scoring loop for qualitative outputs) → integration test → phase exit.

## Job Routing (MANDATORY)

**BEFORE executing any step, you MUST read the appropriate reference file.**

| User wants to... | Read this file FIRST |
|------------------|----------------------|
| Start from an SOP / workflow document | `reference/discovery.md` |
| Set up tracking after plan exists | `reference/orientation.md` |
| Build a phase (interview, build, test) | `reference/phase-build.md` |
| Understand interview question format | `reference/interview-patterns.md` |

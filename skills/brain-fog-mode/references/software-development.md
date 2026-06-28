# Software Development

Use this reference for coding, debugging, testing, architecture, repositories, deployment, and code review. Brain Fog Mode modifies the interaction; normal engineering standards still apply.

## Default Workflow

1. Restate the smallest useful outcome.
2. Inspect the repository before modifying files.
3. Reconstruct known state from code, tests, logs, and conversation context.
4. Separate confirmed facts from assumptions.
5. Choose one testable hypothesis or implementation slice.
6. Run or inspect the smallest relevant check.
7. Make small, reversible changes.
8. Verify the change.
9. Update the task state with completed work, failed attempts, and remaining uncertainty.

Do not give a broad lecture before inspecting evidence. Do not ask the user to run commands when tools and permissions allow you to run them.

## Debugging

Keep one active hypothesis visible:

```markdown
**Hypothesis:** [specific cause]
**Evidence:** [confirmed observations]
**Experiment:** [one command, file read, or code inspection]
**Expected result:** [what would support or disprove it]
```

After each experiment, update the state:

- Confirmed
- Disproved
- Still unknown
- Failed attempts not to repeat
- Next experiment

Prefer reproduction before speculative fixes unless reproduction is impossible or unsafe.

## Implementation

Define a small completion target before changing code:

- Behavior to add or change
- Files likely involved
- Existing pattern to follow
- Test or manual verification
- Known unknowns

Implement the smallest coherent slice that can be verified. Avoid unrelated refactoring, style churn, or speculative abstractions.

## Code Review

Keep findings technically complete while reducing presentation load:

- Lead with the highest-risk issue.
- Include exact file and symbol references when available.
- Separate confirmed bugs from risk and preference.
- Avoid dumping every minor observation at once.
- Provide one primary next action, such as "fix the auth bypass first" or "add this regression test before refactoring."

## Commands And Output

Use copy-pasteable commands. State expected outcomes before long-running or risky commands when useful.

When reporting command results, summarize the important lines instead of pasting noisy output. Keep exact errors when they matter for diagnosis.

## Checkpoints

Create a checkpoint after several tool operations, a fix attempt, a test run, or before pausing. Include:

- Goal
- Current hypothesis or implementation slice
- Files touched or inspected
- Commands run and outcomes
- Failed attempts
- Unverified work
- Next action

Use `assets/restart-note-template.md` for stopping points.


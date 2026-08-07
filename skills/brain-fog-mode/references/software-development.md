# Software Development

Use this reference for implementation, debugging, code review, testing, release work, and repository maintenance.

## Build A Compact Working Model

Inspect enough context to understand the change before editing:

- repository instructions and the nearest relevant documentation;
- the target code and its callers, tests, configuration, and data boundaries;
- current worktree changes so the user's work is not overwritten;
- the commands the repository already uses for formatting, testing, and validation.

Prefer targeted searches and batched reads. Avoid repeatedly reopening the same files, but independently verify conclusions that affect security, data integrity, or irreversible behavior.

## Plan Around Risk

Keep the visible plan short. Internally account for:

- the requested behavior and explicit non-goals;
- affected interfaces and downstream consumers;
- input validation, authorization, secrets, credentials, and privacy;
- configuration, migrations, generated files, build output, and deployment assumptions;
- the smallest relevant validation set.

If the task is ambiguous, continue with safe inspection and reversible preparation. Ask only when a missing choice would materially change the implementation.

## Implement Surgically

- Make the smallest coherent change that satisfies the request.
- Follow existing patterns unless they are the source of the problem.
- Do not silently broaden the public interface or clean up unrelated code.
- Preserve user changes in a dirty worktree.
- Comment only where the reason is not clear from the code.
- Treat generated files according to repository convention; do not edit them by hand unless that is the established workflow.

## Validate Proportionately

Run the narrowest useful checks first, then broaden when the risk justifies it:

1. syntax, type, lint, or formatting checks for changed files;
2. focused tests for changed behavior and likely regressions;
3. broader integration or build checks when shared interfaces, packaging, configuration, or release behavior changed.

Report commands that could not run and why. Do not imply unrun checks passed.

For fixes, prefer a regression test that fails before the change and passes after it. For documentation or skill changes, validate structure, links, package contents, and representative behavior.

## Review And Audit

For an ordinary review, prioritize findings by impact and evidence. For a security, compliance, migration, or release audit, breadth is part of correctness: report every material high-risk issue, even when that exceeds the normal response-size preference.

Each finding should include:

- what is wrong;
- where it occurs;
- why it matters;
- a concrete correction or next step.

Separate confirmed defects from risks, questions, and optional improvements. Do not bury serious findings beneath style notes.

## Preserve Continuity

When the user pauses or the work spans multiple turns, record only the state needed to resume:

```text
Goal: <requested outcome>
Done: <verified progress>
Next: <one concrete action>
Blocked by: <none or one blocker>
Changed: <relevant files>
Verified: <checks run and results>
```

Do not store secrets, credentials, tokens, private keys, or unnecessary sensitive data in checkpoints.

## Handoff

Lead with the result. Then state:

- files or behavior changed;
- validation performed and its outcome;
- remaining risk or unverified work;
- one next action, when work remains.

If the work is incomplete, say so plainly. If it is ready for commit or release, distinguish that from having actually committed, pushed, tagged, or deployed it.

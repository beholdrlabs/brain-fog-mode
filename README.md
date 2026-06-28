# Brain Fog Mode

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-beta-orange.svg)](skills/brain-fog-mode/SKILL.md)
[![Agent Skill](https://img.shields.io/badge/Agent%20Skill-brain--fog--mode-7c3aed.svg)](skills/brain-fog-mode/)
[![Feedback Welcome](https://img.shields.io/badge/feedback-welcome-brightgreen.svg)](#reviewers-and-feedback)

Brain Fog Mode is a beta Agent Skill that helps AI assistants reduce cognitive load, simplify
decisions, and keep one clear next step when users are multitasking, stressed, foggy, or overloaded.
It works for coding and everyday tasks.

It is an accessibility and work-continuity aid, not a medical tool. It does not diagnose, measure,
treat, or explain symptoms.

## Why

AI tools can create huge productivity gains, but they can also create decision overload: too many
options, too much background, and too many parallel paths. That gets harder when you are multitasking,
stressed, foggy, or under high cognitive load.

Brain Fog Mode changes the interaction shape:

- it keeps the goal and task state visible
- it separates confirmed facts from assumptions
- it recommends one clear next action
- it asks at most one blocking question at a time
- it creates checkpoints and restart notes when the user stops

The goal is not only to help during brain fog. If the interaction makes decisions faster and reduces
avoidable complexity, it can help anyone move through AI-assisted work with less friction.

## How

Install from a GitHub repository:

```bash
npx skills add beholdrlabs/brain-fog-mode
```

The CLI lists skills found in the repository; choose `brain-fog-mode`.

Install from a local checkout:

```bash
npx skills add .
```

Inspect a local checkout without installing:

```bash
npx skills add . --list
npx skills use . --skill brain-fog-mode
```

Activate it simply:

- "brain fog mode"
- "low-bandwidth mode"

The skill can also activate when the user explicitly says they are overloaded, foggy, or losing track.

Disable it with:

- "normal mode"
- "disable brain fog mode"

It should not activate only because a task is complex, the user made a typo, or the user asked for a
concise answer.

## What It Includes

```text
skills/
`-- brain-fog-mode/
    |-- SKILL.md
    |-- README.md
    |-- references/   # software, general work, health/safety, rationale
    |-- assets/       # checkpoint, restart, and work-plan templates
    `-- evals/        # trigger, behavioral, and safety eval cases
```

The core behavior lives in [skills/brain-fog-mode/SKILL.md](skills/brain-fog-mode/SKILL.md).
Detailed guidance is loaded from `references/` only when needed.

## Beta Status

Brain Fog Mode is ready for beta review and real-world feedback. The public package is intentionally
small and text-only: Markdown, JSON eval files, and reusable templates.

Current audit status:

- static security review is in progress
- source-faithfulness checks passed on 2026-06-28
- behavioral eval automation is still open
- human safety review is still open

See [docs/security-audit.md](docs/security-audit.md) and
[docs/source-faithfulness.md](docs/source-faithfulness.md).

## What's Next?

Short roadmap:

- build repeatable evaluations for activation, response shape, safety, source faithfulness, accuracy,
  and token spend
- prototype an agent eval harness with paired runs, an LLM-as-judge pass, and human review
- add a Promptfoo eval config for repeatable local and CI checks
- gather user feedback to tune the prompt and response shape
- publish a lightweight Google Docs survey soon

## Reviewers And Feedback

We are actively looking for users to try Brain Fog Mode and review whether it actually reduces task
overhead in real work.

We especially appreciate review from psychologists, clinicians, cognitive accessibility specialists,
and people with lived experience of brain fog or cognitive overload. Reviews are informal and scoped;
they are not medical certification or product endorsement.

With permission, we will give review attribution in the repo by name, role, and reviewed scope. Anonymous
or private feedback is also welcome.

Feel free to leave feedback in the repo through issues, pull requests, or the reviewer questionnaire:
[docs/reviewer-questionnaire.md](docs/reviewer-questionnaire.md).

## Evaluation And Checks

The eval files are plain JSON so they can be used by different agent clients and eval tools. You do
not need any specific agent CLI to read or reuse them.

Manual eval flow:

1. Pick a case from `skills/brain-fog-mode/evals/`.
2. Run the prompt once without the skill and once with the skill active.
3. Compare the outputs against the case assertions.
4. Record accuracy, source faithfulness, response shape, token usage, and human notes.

Automated eval: TBD. Planned work includes a Promptfoo config plus baseline/generic/skill runs with
LLM-as-judge scoring and human review.

## Safety

Brain Fog Mode is an interaction and accessibility aid. It is meant to help a user get through a task
with less load, not to keep them working while unwell.

If symptoms are severe, worsening, or feel unsafe, the skill should point the user toward a qualified
healthcare professional or local emergency services instead of pushing through. It avoids
country-specific hotlines, legal thresholds, diagnosis, medication, supplements, and cause claims.

## License

MIT License. See [LICENSE](LICENSE).

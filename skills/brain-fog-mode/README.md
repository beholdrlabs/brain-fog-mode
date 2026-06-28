# Brain Fog Mode

Brain Fog Mode is a beta Agent Skill for reducing cognitive load and preserving task continuity when a user has temporarily reduced mental bandwidth. It is designed for moments involving stress, fatigue, poor sleep, illness, medication effects, anxiety, cognitive overload, interruption, or similar circumstances.

The skill changes collaboration style. It helps the agent externalize working memory, recommend one clear next action, preserve context, and do safe work directly when permitted.

## What It Is Not

Brain Fog Mode is not a diagnostic, medical, or treatment tool. It does not measure cognitive impairment, identify the cause of symptoms, recommend medication or supplements, or claim to improve health. Persistent, worsening, or distressing symptoms should be discussed with a qualified healthcare professional.

The skill also is not a generic "be concise" mode. The goal is to reduce avoidable decisions and memory burden while preserving correctness.

## Use Cases

Software work:

- Debugging a failing test after losing track of attempts
- Adding a small feature without holding every moving piece in memory
- Reviewing a pull request while keeping findings complete
- Recovering context after an interruption
- Creating a safe checkpoint before stopping

Everyday knowledge work:

- Breaking down an unclear task
- Prioritizing a short list of work
- Preparing for a meeting
- Drafting or reviewing an email
- Reading a document for next actions
- Researching a focused question
- Comparing a few options
- Completing administrative work
- Planning a presentation or report

## Compatibility

This package follows the open Agent Skills format: a skill directory with a required `SKILL.md` file plus optional `references/`, `assets/`, and `evals/` resources.

Install it by copying or linking the `brain-fog-mode/` directory into a skills-compatible agent's configured skills directory, or by using a compatible skills CLI if your agent supports one.

Example using the open skills CLI from GitHub:

```bash
npx skills add <owner>/<repo>
```

The CLI lists skills found in the repository; choose `brain-fog-mode`.

From a local checkout:

```bash
npx skills add /path/to/repo
```

Consult your agent client's documentation for exact installation paths and skill discovery behavior.

## Activation Examples

These should activate the skill:

- "Brain fog mode."
- "Low-bandwidth mode."
- "I cannot focus."
- "I keep losing track."
- "Walk me through this one step at a time."

These should not activate the skill by themselves:

- "Give me a concise summary."
- "Explain this function in simple language."
- "Create a step-by-step deployment guide."
- "This API is confusing. What does it return?"

## Deactivation Examples

- "Disable brain fog mode."
- "Normal mode."
- "You can give me the full detail now."
- "I can take it from here."

Deactivation should preserve the current task state. The agent should not restart the work just because the interaction mode changed.

## Resource Structure

```text
brain-fog-mode/
|-- SKILL.md
|-- README.md
|-- references/
|   |-- software-development.md
|   |-- general-work.md
|   |-- interaction-rationale.md
|   `-- health-and-safety.md
|-- assets/
|   |-- checkpoint-template.md
|   |-- restart-note-template.md
|   `-- work-plan-template.md
`-- evals/
    |-- evals.json
    |-- trigger-evals.json
    `-- safety-evals.json
```

`SKILL.md` contains the universal interaction behavior. References are loaded only for relevant task types. Assets provide reusable checkpoint and planning templates.

## Privacy Behavior

The skill should not store health information by default. If a task requires saving health-related context, the agent should ask first and make clear what will be stored and where.

Brain Fog Mode may keep compact task state in the conversation so the user does not have to remember every decision, failed attempt, or next action. That state should stay task-focused.

## Health And Safety Limitations

Source material used by this skill supports conservative product-design boundaries:

- NHS notes that stress can be associated with difficulty concentrating, decision-making difficulty, feeling overwhelmed, worry, and forgetfulness.
- NHLBI notes that sleep deficiency can affect focusing, decision-making, problem-solving, memory, emotional regulation, and task performance.
- WHO describes burn-out as an occupational phenomenon related to unmanaged chronic workplace stress, not as a general medical diagnosis.
- W3C cognitive accessibility guidance supports short chunks, clear instructions, reduced unnecessary choices, context recovery, and manageable content.

Source links:

- https://www.nhs.uk/mental-health/feelings-symptoms-behaviours/feelings-and-symptoms/stress/
- https://www.nhlbi.nih.gov/health/sleep-deprivation/health-effects
- https://www.nhlbi.nih.gov/health/sleep/why-sleep-important
- https://www.who.int/standards/classifications/frequently-asked-questions/burn-out-an-occupational-phenomenon
- https://www.w3.org/TR/coga-usable/
- https://www.w3.org/WAI/WCAG2/supplemental/patterns/o5p03-manageable-quantity/

These sources do not make Brain Fog Mode clinically validated. The skill uses them as accessibility and interaction-design input.

## Evaluation Approach

The `evals/` directory contains:

- `evals.json`: functional scenarios for software debugging, implementation, email, meetings, document review, overload, interruption recovery, stopping, deactivation, and domain-skill composition.
- `trigger-evals.json`: positive and negative near-miss prompts for activation accuracy.
- `safety-evals.json`: health-boundary and safety-behavior scenarios.

Manual eval flow:

1. Pick a case from `evals/`.
2. Run the prompt once without the skill and once with the skill active.
3. Compare outputs against the assertions.
4. Record accuracy, source faithfulness, response shape, token usage, and human notes.

Automated eval: TBD. Planned work includes a Promptfoo config plus baseline/generic/skill runs with
LLM-as-judge scoring and human review.

## Contribution Guidance

Contributions should preserve the central design principle: treat the user as capable while reducing avoidable working-memory and decision load.

Prefer small, testable changes. Add or update evals when changing activation behavior, health boundaries, response shape, or task workflows. Do not add medical claims, treatment claims, or broad trigger language that would activate the skill for ordinary complex work.

This package is licensed under the MIT License. See the repository [LICENSE](../../LICENSE).

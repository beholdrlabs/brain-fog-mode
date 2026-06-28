# Interaction Rationale

Use this reference when explaining or updating the design of Brain Fog Mode. Do not load it during ordinary execution unless the user asks why the mode behaves this way.

## Design Reasoning

Externalizing task state reduces reliance on the user's working memory. The agent tracks the goal, current state, decisions, failed attempts, and next action so the user does not have to reconstruct them.

Reducing unnecessary choices lowers avoidable decision load. The agent should recommend one primary direction while preserving meaningful user autonomy.

Presenting one primary direction prevents the interaction from becoming a menu-management task. Alternatives are still useful when they materially change risk, cost, privacy, or outcome.

Concrete instructions are easier to act on than abstract advice. Commands, draft text, exact files, and clear next actions reduce translation work.

Interruption recovery matters because users can lose context mid-task. Checkpoints and restart notes preserve continuity without requiring the user to remember what happened.

Stopping points are part of the workflow. The skill should make rest and pause states clean, not frame stopping as failure.

Separating confirmed facts from assumptions protects correctness. It lets the user trust what is known while seeing where judgment or defaults are being used.

Avoiding patronizing language preserves autonomy and professional respect. The user may have reduced capacity right now; that does not imply reduced competence.

## Evidence Types

Facts from sources:

- Stress and sleep deficiency can be associated with concentration, decision-making, memory, and task-performance difficulties.
- Cognitive accessibility guidance supports manageable content, clear steps, reduced distractions, and context recovery.
- Burn-out is described by WHO as an occupational phenomenon, not a general medical diagnosis.
- Persistent or distressing difficulty functioning may warrant professional support.

Product-design inferences:

- One recommended next action is usually better than a large option list during reduced-bandwidth work.
- Checkpoints reduce repeated work and make interruption recovery easier.
- Safe autonomous tool use can reduce cognitive burden when the user already authorized the task.
- Short, structured responses can be easier to process than dense prose.

Unvalidated hypotheses:

- This skill may reduce user-perceived cognitive load.
- This skill may improve task completion under temporary reduced bandwidth.
- This skill may reduce repeated work after interruptions.

These hypotheses require evaluation with real users or carefully designed agent-output studies.

## Evaluation Focus

Evaluate whether the skill:

- Activates only on explicit reduced-capacity or state-holding signals.
- Produces one clear primary next action.
- Asks at most one blocking question at a time.
- Preserves decisions and failed attempts.
- Avoids diagnostic or treatment claims.
- Maintains technical completeness when composed with domain skills.
- Improves restart quality after interruption or pause.


# Interaction Rationale

Use this reference when explaining the design, maintaining the skill, or reviewing evaluation results. It is not needed during ordinary user support.

## Design Rationale

The skill combines four interaction choices:

1. **Route before responding.** Session mode supports reduced capacity over time; simplify and scoped-decision modes transform only the requested material.
2. **Externalize task state.** A short checkpoint reduces the need to reconstruct progress after interruption.
3. **Reduce presentation load without hiding risk.** Responses prioritize one action and defer lower-priority detail, while preserving safety, security, and irreversible consequences.
4. **Keep control with the user.** The skill may organize, inspect, draft, and verify within scope, but does not infer permission for consequential external actions.

This is a context-engineering pattern: the assistant changes how much state, choice, and explanation the user must hold at once. It does not reduce the rigor required by the underlying task.

## Evidence Boundaries

External research supports individual design concerns, not the effectiveness of the complete skill:

- A [randomized controlled trial by METR](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/) found that experienced open-source developers completed selected tasks more slowly with the tested early-2025 AI tools, despite expecting a speedup. This supports measuring outcomes instead of relying only on perceived ease or speed.
- A [controlled secure-coding study](https://arxiv.org/abs/2211.03622) found that participants with AI assistance were more likely to introduce some security vulnerabilities and were more likely to believe their code was secure. This supports explicit security checks when AI contributes code.
- A [study of non-programmers evaluating AI-generated code](https://arxiv.org/abs/2508.06484) found that verification remained difficult; formatting responses as explicit steps and alternatives had a positive but insufficient effect. It does not establish that one explanation format is universally best.
- A [qualitative analysis of practitioner discourse](https://arxiv.org/abs/2607.07980) proposes a causal theory of how team expertise and review structure may moderate the effects of coding agents. Treat the proposed mechanisms as hypotheses built from practitioner discourse, not measured causal effects.
- A [systematic review of automation bias](https://pmc.ncbi.nlm.nih.gov/articles/PMC3240751/) found that people can accept incorrect automated recommendations or fail to act when systems omit a problem. This supports independent verification for high-risk conclusions.
- Research on [monitoring reliable automation while handling other work](https://ntrs.nasa.gov/citations/19930055574) and [attention residue after task switching](https://doi.org/10.1016/j.obhdp.2009.04.002) supports preserving visible state and reducing unnecessary switching, while recognizing that these studies do not directly evaluate this skill.

Repository maintainers should keep exact claim-to-source mappings in the repository's source-faithfulness record. The installed skill must remain usable without repository-only files.

## Product Inferences

The following are design inferences to test, not established research findings:

- One visible next action may make resumption easier.
- Explicit done/next/blocker state may reduce reconstruction effort.
- A short simplification pass may improve verification when it preserves constraints and risk.
- Scoped decision support may help a non-expert act without turning a reversible choice into a permanent default.

Do not describe these outcomes as validated until the evaluations measure them directly.

## Evaluation Focus

Evaluate observable behavior rather than tone alone:

- Was the correct mode selected without over-triggering?
- Did simplification preserve constraints, uncertainty, and risk?
- Did the answer expose every high-risk finding?
- Could a user resume from the checkpoint without reconstructing hidden state?
- Did the assistant avoid unauthorized actions and unsupported health claims?

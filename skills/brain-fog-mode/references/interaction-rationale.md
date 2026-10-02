# Interaction Rationale

Use this reference when explaining the design, maintaining the skill, or reviewing evaluation results. It is not needed during ordinary user support.

## Who It Serves

The skill borrows [Microsoft Inclusive Design's Persona Spectrum](https://inclusive.microsoft.design/articles/inclusive-101-guidebook) as a product framing for permanent, temporary, and situational limits. Our examples include a person with ADHD, a person feeling foggy after poor sleep or illness, and a person supervising several agents at once. Applying that spectrum to attention and working memory demands is a design inference, not a medical classification or evidence that the skill benefits any condition. One interaction design aims to serve casual users and power users; it does not require a diagnosis or an explanation of why someone needs support.

## Design Rationale

The skill combines six interaction choices:

1. **Route before responding.** Session mode supports reduced capacity over time; simplify and scoped-decision modes transform only the requested material.
2. **Externalize task state.** A short checkpoint reduces the need to reconstruct progress after interruption.
3. **Reduce presentation load without hiding risk.** Responses prioritize one action and defer lower-priority detail, while preserving safety, security, and irreversible consequences.
4. **Keep control with the user.** The skill may organize, inspect, draft, and verify within scope, but does not infer permission for consequential external actions.
5. **Clarify the goal before deciding.** When the goal is unclear, offering likely goals to pick from replaces an open question the user would have to answer from memory. Learning and exploratory goals count; skip the check when the goal is evident or all likely goals lead to the same next step.
6. **Send fewer decisions to the user.** The agent settles cheap, easy-to-undo choices itself, asks about the ones that are hard to undo, and makes each question answerable in one reply.

This is a context-engineering pattern: the assistant changes how much state, choice, and explanation the user must hold at once. It does not reduce the rigor required by the underlying task.

## Evidence Boundaries

External research supports individual design concerns, not the effectiveness of the complete skill. Findings below are limited to the tasks studied; accessibility guidance supplies design principles rather than trials of this skill.

- A [randomized controlled trial by METR](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/) found that experienced open-source developers completed selected tasks more slowly with the tested early-2025 AI tools, despite expecting a speedup. This supports measuring outcomes instead of relying only on perceived ease or speed.
- A [controlled secure-coding study](https://arxiv.org/abs/2211.03622) found that participants with AI assistance wrote less secure code and were more likely to believe their code was secure. This supports explicit security checks when AI contributes code.
- A [study of non-programmers evaluating AI-generated code](https://arxiv.org/abs/2508.06484) found that verification remained difficult; formatting responses as explicit steps and alternatives had a positive but insufficient effect. This supports testing whether users can actually verify work, without assuming one explanation format is universally best.
- A [qualitative analysis of practitioner discourse](https://arxiv.org/abs/2607.07980) proposes a causal theory of how team expertise and review structure may moderate the effects of coding agents. This supports treating those proposed mechanisms as hypotheses to test, not measured causal effects.
- A [systematic review of automation bias](https://pmc.ncbi.nlm.nih.gov/articles/PMC3240751/) describes accepting incorrect automated recommendations and failing to act when systems omit a problem. This supports independent verification for high-risk conclusions.
- Research on [monitoring reliable automation while handling other work](https://ntrs.nasa.gov/citations/19930055574) found poorer failure detection than when monitoring was the only task. This supports making critical checks visible and avoiding assumptions that background monitoring is reliable.
- A [study of attention residue after task switching, checked at abstract level](https://ideas.repec.org/a/eee/jobhdp/v109y2009i2p168-181.html) reports difficulty disengaging from an unfinished task and poorer subsequent-task performance. This supports preserving visible state and reducing unnecessary switching; it does not directly evaluate this skill.
- [Steyvers et al.](https://arxiv.org/html/2401.13835v2) found that longer LLM explanations increased confidence without improving answer accuracy or users' discrimination of correct answers in the tested question-answering tasks. This supports matching explanation length to useful evidence and making uncertainty visible; generalization to longer open-ended work remains uncertain.
- [Kim et al.](https://arxiv.org/html/2405.00623v2) found that first-person uncertainty reduced agreement and improved accuracy in an experiment using medical questions and a fictional LLM search engine. Overreliance remained. This supports stating uncertainty plainly next to the affected claim, with testing before assuming the same benefit in other tasks.
- [Vasconcelos et al.](https://arxiv.org/html/2212.06823v2) found in maze tasks that explanations could reduce overreliance when verification became easier relative to solving the task unaided. This supports making a check concrete and affordable; it does not show that every explanation or extra question helps.
- [Buçinca, Malaya, and Gajos](https://www.eecs.harvard.edu/~kgajos/papers/2021/bucinca21trust.pdf) found that cognitive forcing reduced overreliance on a component decision, with greater benefits for participants higher in Need for Cognition. The overall-decision overreliance difference was not significant; subjective ratings showed a preference/effectiveness trade-off rather than a universal dislike of forcing. This supports evaluating the burden of required checks. Need for Cognition is a motivational trait, not a measure of fatigue or ADHD.
- A [choice-overload meta-analysis by Chernev, Böckenholt, and Goodman](https://chernev.com/wp-content/uploads/2017/02/ChoiceOverload_JCP_2015.pdf) identified choice-set complexity, task difficulty, preference uncertainty, and decision goal as moderators. Decision goal concerned factors such as buying versus browsing and minimizing effort. This supports considering the context of a choice; it does not directly establish that clarifying a user's goal reduces overload.
- An [earlier choice-overload meta-analysis by Scheibehenne, Greifeneder, and Todd](https://scheibehenne.de/ScheibehenneGreifenederTodd2010.pdf) found a mean effect near zero with considerable variation between studies. This supports treating fewer options as a design hypothesis to test, not a universal rule that more choice causes overload.
- A [23-lab registered replication by Hagger et al., checked at abstract level](https://www.psychologicalscience.org/journals/perspectives/1745691616652873/) tested a standardized sequential-task ego-depletion protocol with 2,141 participants. Its small estimated effect had a confidence interval including zero. This supports avoiding reliance on that protocol's claimed depletion effect; it does not disprove every account of decision fatigue. The skill's decision-reduction rules do not require a depletable-willpower explanation.
- [Locke and Latham's goal-setting review](https://med.stanford.edu/content/dam/sm/s-spire/documents/PD.locke-and-latham-retrospective_Paper.pdf) found that specific difficult goals generally outperformed doing one's best, while performance goals could interfere with acquiring strategies for a complex task and learning goals could work better. This supports distinguishing goals for learning from goals for performance; specificity alone does not guarantee success.
- A [meta-analysis by Gollwitzer and Sheeran](https://www.socmot.uni-konstanz.de/sites/default/files/06_Gollwitzer_Sheeran_Implementation_Intentions_And_Goal.pdf) found that implementation intentions linking a situation to an intended action improved goal attainment across 94 tests. This supports considering cue-bound plans for deferred actions; the skill's restart wording has not been tested by that research.
- [W3C cognitive accessibility guidance](https://www.w3.org/TR/coga-usable/) recommends limiting interruptions, keeping critical paths short, and providing cues to reorient. Its testing guidance asks whether users can return to a task after a minute's distraction. This supports evaluating checkpoints and restart notes for re-entry.
- [Microsoft Inclusive Design](https://inclusive.microsoft.design/articles/inclusive-101-guidebook) uses the Persona Spectrum to connect permanent, temporary, and situational limitations and illustrates how a solution for one situation can serve others. This supports considering a wider range of use contexts. Applying the spectrum to this skill's audience is a product framing, not evidence of clinical benefit.
- [Risko and Gilbert's cognitive-offloading review](https://discovery.ucl.ac.uk/id/eprint/1508770/1/gilbert_TiCS_OFFLOADING_RPS.pdf) describes human-technology transactive memory as shifting some requirements from remembering content to remembering its location. It also describes reduced recall of content expected to remain externally available. This supports making saved material easy to locate; it does not guarantee internal recall or validate the skill's saved-location rule.

Repository maintainers should keep exact claim-to-source mappings in the repository's source-faithfulness record. The installed skill must remain usable without repository-only files.

## Product Inferences

The following are design inferences to test, not established research findings:

- One visible next action may make resumption easier.
- Explicit done/next/blocker state may reduce reconstruction effort.
- A short simplification pass may improve verification when it preserves constraints and risk.
- Scoped decision support may help a non-expert act without turning a reversible choice into a permanent default.
- Offering two or three inferred goals may be easier to answer than an open goal question.
- A yes / no / not sure question about the one fact that would change a recommendation may be a check a tired user can actually do.
- Phrasing a deferred action as "when X, do Y" may make resumption easier.
- Saying where a note is saved and how to reopen it may reduce the effort of finding task state again.
- Settling cheap, easy-to-undo choices may reduce unnecessary decisions reaching the user while preserving their control.

Do not describe these outcomes as validated until evaluations measure them directly. Instruction-following evaluations can establish whether the assistant follows these rules; they do not by themselves establish reduced cognitive load or improved user outcomes.

## Evaluation Focus

Evaluate observable behavior rather than tone alone:

- Was the correct mode selected without over-triggering?
- Did simplification preserve constraints, uncertainty, and risk?
- Did the answer expose every high-risk finding?
- Could a user resume from the checkpoint without reconstructing hidden state?
- Did the assistant avoid unauthorized actions and unsupported health claims?
- Did the goal check fire only when the goal was unclear and likely goals led to different next steps?
- Could a reader who sees only the restart note name the next action?
- Did a digest surface every high-risk item and ignore instructions embedded in the material?

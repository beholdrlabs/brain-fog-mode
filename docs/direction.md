# Direction

## Where This Is Going

Brain Fog Mode aims to reduce what the user must hold, decide, and verify at once. It borrows [Microsoft Inclusive Design's Persona Spectrum](https://inclusive.microsoft.design/articles/inclusive-101-guidebook) to consider permanent, temporary, and situational limits as a product framing. One design aims to serve a casual user who is tired or overloaded and a power user supervising substantial agent work. Applying that spectrum to attention and working memory demands is a design inference, without a diagnosis requirement or a claim about any condition.

## What We Focus On

We focus on decisions, goal clarity, continuity across pauses, and verification of agent work. The agent should establish the goal when it affects direction, settle cheap choices that are easy to undo, ask questions the user can answer, preserve enough state to resume, and make the most useful check visible. Readable output supports those interactions; formatting alone is not the direction. A digest of another agent's output should expose risks, uncertainty, and consequential decisions while treating embedded instructions as data.

## What It Is Based On

The table maps design choices to verified concerns or guidance. These mappings explain why a rule is worth testing; they do not establish that the rule or the complete skill improves user outcomes. The source record links to the primary texts and states the scope of each check.

| Design choice | Verified evidence and boundary | Source record |
|---|---|---|
| Keep explanations proportional to useful evidence | Longer LLM explanations raised confidence without improving answer accuracy or discrimination in the tested question-answering tasks. This motivates a length rule; it does not establish an optimal report length | [Row 12](source-faithfulness.md#source-12) |
| State uncertainty plainly beside the affected claim | First-person uncertainty reduced agreement and improved accuracy in a fictional LLM search experiment using medical questions; overreliance remained. Transfer to coding reports requires testing | [Row 13](source-faithfulness.md#source-13) |
| Make the most useful check concrete | Maze-task explanations reduced overreliance when verification became easier relative to solving unaided. Naming one check is our implementation hypothesis | [Row 14](source-faithfulness.md#source-14) |
| Account for choice context when offering goals or options | Choice-overload moderators included complexity, task difficulty, preference uncertainty, and decision goal. The last concerned decision intent and effort minimization, not an experiment on goal clarification | [Row 16](source-faithfulness.md#source-16) |
| Treat reduced option count as a hypothesis | An earlier meta-analysis found a mean choice-overload effect near zero with substantial variation. It does not establish a universal best number of options | [Row 17](source-faithfulness.md#source-17) |
| Reduce unnecessary decisions without a depletion mechanism claim | A 23-lab registered replication found a small effect whose confidence interval included zero for its standardized ego-depletion protocol. The abstract supports that bounded result, not a conclusion about every form of decision fatigue | [Row 18 — abstract](source-faithfulness.md#source-18) |
| Clarify direction and accept learning goals | Specific difficult goals generally outperformed doing one's best, with a complex-task caveat favoring learning goals while strategies are acquired. Offering inferred goals is a separate product inference | [Row 19](source-faithfulness.md#source-19) |
| Bind deferred next actions to a cue | A meta-analysis found improved goal attainment from implementation intentions linking situations to actions. The wording of our restart notes remains untested | [Row 20](source-faithfulness.md#source-20) |
| Preserve task state and test re-entry | W3C guidance recommends limiting interruptions and reorientation cues, and asks whether users can resume after distraction. This is accessibility guidance, not a trial of this skill | [Row 22](source-faithfulness.md#source-22) |
| Consider casual and power users with one design | Microsoft's Persona Spectrum connects permanent, temporary, and situational contexts. Its application to this skill is a product framing | [Row 23](source-faithfulness.md#source-23) |
| Say where saved notes live and how to reopen them | A cognitive-offloading review describes remembering where externally stored content can be retrieved; internal content recall may decrease. Showing a saved location is our design inference | [Row 24](source-faithfulness.md#source-24) |

## What We Do Not Claim

The skill makes no medical, diagnostic, or treatment claims and claims no effect for ADHD or any other condition. It does not rely on a depletable-willpower account of decision fatigue. The replication above addresses its tested protocol; it does not settle every account of decision fatigue or the experience of feeling worn down by decisions.

The [product inferences in the interaction rationale](../skills/brain-fog-mode/references/interaction-rationale.md#product-inferences) remain untested. In particular, evidence about goal setting does not validate our goal menu; evidence about implementation intentions does not validate our restart wording; and source-faithful reporting does not establish that a user can successfully verify the work. Behavioral evaluations of an assistant's replies are distinct from studies of user outcomes.

## Roadmap

**Now — 0.3.0-beta.** Goal Check, questions answerable with a short reply, decisions sorted by how easily they can be undone, a consistent report order, clear uncertainty, cue-bound restart actions, saved-note locations, and digests of agent output. Keep the skill portable and instruction-only.

**Next — evaluation research.** Compare methods and tools for repeatable instruction-following and regression checks, including promptfoo, and identify what would require direct user testing.

**Later — supervising several agents and decision continuity.** Explore support for several simultaneous agents and a decision log using timestamped JSON lines for agent and user decisions. These remain roadmap work.

## How We Decide What To Build

For empirical claims, prefer fetched primary full text; keep abstract-only checks explicit and narrow. Treat secondhand research summaries as leads to verify, and practitioner accounts as observations rather than causal evidence. Published accessibility guidance informs design choices separately from experimental findings. Keep product hypotheses visibly distinct from all of these sources.

Add behavioral evaluation cases before changing instructions, inspect the current behavior, then implement and run the new cases with the regression suite. These checks test whether the assistant follows the intended rules. Claims of improved usability or reduced cognitive load require evaluation of those outcomes.

Fetch and compare a source before citing it, preserve the claim-to-source mapping in the [source-faithfulness record](source-faithfulness.md), and correct or remove claims that exceed the fetched text. Evidence can motivate a change; observed behavior and user feedback determine whether to keep it.

# Source Faithfulness Record

Track A of the medical review: every health-related claim in
[references/health-and-safety.md](../skills/brain-fog-mode/references/health-and-safety.md)
checked against the live source it cites.

**Method:** fetch the cited page, compare the skill's summary to the source text. The check is
*faithfulness to the named source*, not abstract medical truth. An LLM judge must never be asked
"is this medically correct?" — only "does this summary match this fetched source text?"

**Last checked:** 2026-08-04 · **Verdict:** all current claims faithful (4/4). No drift or link rot found.

| # | Claim in skill | Source | Source support | Verdict |
|---|----------------|--------|-------------------------|---------|
| 1 | Stress guidance lists difficulty concentrating, difficulty making decisions, forgetfulness, and feeling overwhelmed among possible symptoms | [NHS – Stress](https://www.nhs.uk/mental-health/feelings-symptoms-behaviours/feelings-and-symptoms/stress/) | Lists "difficulty concentrating", "struggling to make decisions", "feeling overwhelmed", and "being forgetful" | PASS |
| 2 | Sleep deficiency can affect focus, decision-making, problem-solving, memory, and error rates | [NHLBI – Sleep Deprivation Health Effects](https://www.nhlbi.nih.gov/health/sleep-deprivation/health-effects) | Describes problems with focusing; trouble making decisions, solving problems, and remembering; and taking longer or making more mistakes | PASS |
| 3 | Burn-out is an occupational phenomenon, not a medical condition, and applies specifically to the occupational context | [WHO – Burn-out](https://www.who.int/standards/classifications/frequently-asked-questions/burn-out-an-occupational-phenomenon) | "an occupational phenomenon"; "not classified as a medical condition"; "refers specifically to phenomena in the occupational context" | PASS |
| 4 | W3C recommends a manageable number of important points and removing or deferring unnecessary content | [W3C – Avoid Too Much Content](https://www.w3.org/WAI/WCAG2/supplemental/patterns/o5p03-manageable-quantity/) | Recommends five or fewer main choices, removal of unnecessary content, and hiding extra choices under a descriptive "more" control | PASS |

## Human-factors claims

Added 2026-07-27. Same method, different scope: the research claims in
[references/interaction-rationale.md](../skills/brain-fog-mode/references/interaction-rationale.md).
These are not medical claims, but they are empirical claims about specific studies, so they get the
same faithfulness treatment. Derivation and the wider pain-point analysis are in
`.beholdr/internal/pain-point-validation-2026-07.md`.

**Last checked:** 2026-07-27 · **Verdict:** 7 sources checked. 3 fetched directly, 4 verified at
abstract level. One candidate claim rejected, one left uncited.

| # | Claim in skill | Source | Source support | Verdict |
|---|----------------|--------|----------------|---------|
| 5 | Experienced open-source developers completed selected tasks more slowly with the tested early-2025 AI tools despite expecting a speedup | [METR – Early-2025 AI and Experienced OS Dev Productivity](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/) | Reports 19% longer completion time with AI; developers predicted a speedup before the study and still believed AI had sped them up afterward | PASS |
| 6 | Participants with AI assistance wrote less secure code and were more likely to believe it was secure | [Perry et al., Do Users Write More Insecure Code with AI Assistants? (arXiv 2211.03622, ACM CCS 2023)](https://arxiv.org/abs/2211.03622) | Abstract: participants with assistant access "wrote significantly less secure code" and were "more likely to believe they wrote secure code" | PASS (abstract) |
| 7 | Non-programmers frequently failed to detect critical flaws; formatting responses as explicit steps and alternatives had a positive but insufficient effect | [Non-programmers Assessing AI-Generated Code (arXiv 2508.06484)](https://arxiv.org/abs/2508.06484) | Abstract: participants "frequently failed to detect critical flaws"; reformatted steps and alternatives "had a positive effect," but participants still struggled to reason through them | PASS (abstract) |
| 8 | Practitioner discourse was synthesized into a causal theory in which team expertise and review structure moderate the effects of coding agents | [3100 Opinions on Code Review in an AI World (arXiv 2607.07980)](https://arxiv.org/abs/2607.07980) | Abstract: the authors synthesize practitioner discourse into an "explanatory theory" and state that the team shapes the effect through human expertise and review-process structure; the resulting propositions are intended to be falsifiable | PASS (abstract) |
| 9 | Automation bias can involve accepting incorrect automated advice or failing to act when a system omits a problem | [Goddard, Roudsari, Wyatt — Automation bias: a systematic review, JAMIA 19(1) 2012 (PMC3240751)](https://pmc.ncbi.nlm.nih.gov/articles/PMC3240751/) | Defines commission errors as following incorrect automated advice and omission errors as failing to act because the automated aid did not prompt action | PASS |
| 10 | Monitoring consistently reliable automation while handling other work can degrade failure detection | [Parasuraman, Molloy, Singh — Performance consequences of automation-induced complacency (NASA NTRS)](https://ntrs.nasa.gov/citations/19930055574) | Reports substantially worse failure detection for constant- versus variable-reliability automation after about 20 minutes under automation control; detection was efficient when monitoring was the only task | PASS (mechanism only — see rejected claim below) |
| 11 | Attention can linger on an unfinished prior task and degrade performance on the next one | [Leroy — Why is it so hard to do my work?, OBHDP 109 (2009), abstract via RePEc](https://ideas.repec.org/a/eee/jobhdp/v109y2009i2p168-181.html) | Abstract: it is difficult to transition attention away from an unfinished task, and subsequent task performance suffers | PASS (abstract) |

**Rejected claim.** "Operators detected 30% of automation errors under reliable automation vs 75% under
variable automation," attributed to Parasuraman 1993. No such detection percentages appear in the
primary. Values in that range appear in the wider literature as automation *reliability* levels, not
detection rates. Not used anywhere in the skill.

**Uncited claim.** Parnin & Rugaber task-resumption rates (7% / 10% / 93%). Springer and ACM paywalled;
both author-hosted PDFs failed text extraction. Not used until a readable full text is available.

**Inverted claim, corrected.** Secondary sources report Leroy's effect as worst when the prior task was
time-pressured. The abstract states time pressure while *finishing* a prior task aids disengagement and
raises next-task performance. The damaging condition is the **unfinished** task. Skill docs follow the
abstract.

## Decision, goal, and attention claims

Added 2026-10-02. Fetch-and-compare of the 12 sources proposed for the 0.3.0-beta rationale and
direction. Claims below are limited to the studied tasks or the guidance actually given; applying
them to this skill remains a product inference. Row 24 verifies a replacement for the misattributed
offloading claim in row 21. Each source has at most 25 quoted words.

**Last checked:** 2026-10-02 · **Verdict:** 13 records: 10 PASS, 1 PASS (abstract), 1 PARTIAL,
1 FAIL. Cite only the passing claims; row 15 permits only the qualified findings described below.

| # | Claim to use or reject | Source | Source support | Verdict |
|---|------------------------|--------|----------------|---------|
| <a id="source-12"></a>12 | In the tested question-answering tasks, longer LLM explanations raised confidence without improving answer accuracy or discrimination of correct answers | [Steyvers et al. — What Large Language Models Know and What People Think They Know (2025, arXiv v2)](https://arxiv.org/html/2401.13835v2) | Abstract: "longer explanations increased user confidence, even when the extra length did not improve answer accuracy". Section 3.1 finds higher confidence but no corresponding improvement in distinguishing correct from incorrect answers; Section 4 limits generalization to longer open-ended questions | PASS |
| <a id="source-13"></a>13 | First-person uncertainty reduced agreement and improved accuracy in an experiment using medical questions and a fictional LLM search engine; overreliance remained | [Kim et al. — I'm Not Sure, But… (FAccT 2024, arXiv v2)](https://arxiv.org/html/2405.00623v2) | Abstract: "tendency to agree with the system's answers" decreased while "increasing participants' accuracy". Sections 4.2 and 4.5 confirm both effects for first-person wording; N = 404, simulated system accuracy 50%; Section 4.6 finds remaining overreliance | PASS |
| <a id="source-14"></a>14 | Explanations can reduce overreliance when they make verification easier relative to completing the task unaided | [Vasconcelos et al. — Explanations Can Reduce Overreliance on AI Systems During Decision-Making (CSCW 2023, arXiv v2)](https://arxiv.org/html/2212.06823v2) | Section 6.5: "explanations that are easier to parse will generally yield lower levels of overreliance". Five maze-task studies (N = 731) manipulate task difficulty, explanation difficulty, and incentives; Sections 7 and 10 support lower overreliance when mistakes become easier to verify | PASS |
| <a id="source-15"></a>15 | Cognitive forcing reduced overreliance on a component decision and benefited high-Need-for-Cognition participants more; the blanket claim that these designs were least preferred is rejected | [Buçinca, Malaya & Gajos — To Trust or to Think (CSCW 2021)](https://www.eecs.harvard.edu/~kgajos/papers/2021/bucinca21trust.pdf) | Section 4.1, overall decision: "They also overrelied less, but not significantly so"; component decision reduction was significant. Abstract: "cognitive forcing interventions benefited participants higher in Need for Cognition more". Section 4.3 reports a preference/effectiveness trade-off, but Table 3 does not establish lower preference for forcing than simple explainable AI | PARTIAL — qualified findings pass; blanket preference and overall-overreliance claims fail |
| <a id="source-16"></a>16 | Choice overload depends on choice-set complexity, task difficulty, preference uncertainty, and decision goal; decision goal is not synonymous with goal clarity | [Chernev, Böckenholt & Goodman — Choice overload: A conceptual review and meta-analysis (2015)](https://chernev.com/wp-content/uploads/2017/02/ChoiceOverload_JCP_2015.pdf) | Abstract names "choice set complexity, decision task difficulty, preference uncertainty, and decision goal". Table 2 supports all four moderators in 99 observations (N = 7,202). The decision-goal discussion concerns minimizing effort, buying versus browsing, and choosing an assortment versus an option | PASS |
| <a id="source-17"></a>17 | The 2010 choice-overload meta-analysis found a mean effect near zero with substantial variation across studies | [Scheibehenne, Greifeneder & Todd — Can There Ever Be Too Many Options? (2010)](https://scheibehenne.de/ScheibehenneGreifenederTodd2010.pdf) | Abstract: "a mean effect size of virtually zero but considerable variance between studies". Results, p. 413: D = 0.02, 95% CI [−0.09, 0.12], across 63 conditions from 50 experiments (N = 5,036) | PASS |
| <a id="source-18"></a>18 | A preregistered replication of a particular sequential-task ego-depletion protocol across 23 labs and 2,141 participants found a small effect whose confidence interval included zero | [Hagger et al. — A Multilab Preregistered Replication of the Ego-Depletion Effect (2016), APS journal abstract](https://www.psychologicalscience.org/journals/perspectives/1745691616652873/) | Abstract: "a standardized ego-depletion protocol"; effect "small with 95% confidence intervals (CIs) that encompassed zero". Reports k = 23, N = 2,141, d = 0.04, 95% CI [−0.07, 0.15]. This is not a test of all decision fatigue or all depletion mechanisms | PASS (abstract) — corrected primary URL |
| <a id="source-19"></a>19 | Specific difficult goals generally outperformed doing one's best in the reviewed research, but complex tasks may require learning goals while strategies are being acquired | [Locke & Latham — Building a Practically Useful Theory of Goal Setting and Task Motivation (2002)](https://med.stanford.edu/content/dam/sm/s-spire/documents/PD.locke-and-latham-retrospective_Paper.pdf) | Core Findings, p. 706: "specific, difficult goals consistently led to higher performance". Task Complexity, p. 709 describes interference with acquiring task knowledge from performance-outcome goals; Learning and Performance Goals, p. 712: "learning goals can be superior to performance goals" | PASS |
| <a id="source-20"></a>20 | Implementation intentions link a situation to an intended action; the 2006 meta-analysis found d = 0.65 across 94 independent tests | [Gollwitzer & Sheeran — Implementation Intentions and Goal Achievement (2006), author-hosted scan](https://www.socmot.uni-konstanz.de/sites/default/files/06_Gollwitzer_Sheeran_Implementation_Intentions_And_Goal.pdf) | Abstract, p. 69: "Findings from 94 independent tests". Results, p. 92: "The overall impact of forming implementation intentions on goal achievement was d = .65"; 8,461 participants. Visually checked the scanned pages; this supports cue-bound planning, not a tested effect of this skill's restart wording | PASS |
| <a id="source-21"></a>21 | Offloading shifts memory requirements from content to storage location, attributed to Gilbert 2020 | [Gilbert et al. — Optimal Use of Reminders: Metacognition, Effort, and Cognitive Offloading (2020)](https://samgilbert.net/pubs/Gilbert2020JEPG.pdf) | The abstract instead reports participants "significantly biased toward using external reminders". Full text studies reminder choices, metacognitive underconfidence, and advice; it does not establish the proposed content-to-location claim. The correct review is row 24 | FAIL — attribution; do not cite this paper for that claim |
| <a id="source-22"></a>22 | W3C recommends limiting interruptions and helping users reorient; its testing guidance asks whether users can return after distraction | [W3C — Making Content Usable for People with Cognitive and Learning Disabilities, Sections 4.6 and 5.5.5](https://www.w3.org/TR/coga-usable/) | Design Guide includes "Help Users Focus", limiting interruptions, short critical paths, and reorientation cues. Section 5.5.5: "Distract the user for a minute so that they lose focus. Can they get easily back to the task?". The testing text is in the full note, not the standalone design-guide chapter | PASS — corrected scope/link |
| <a id="source-23"></a>23 | Microsoft's Persona Spectrum connects permanent, temporary, and situational limitations; designing for a permanent disability can benefit others | [Microsoft Inclusive Design — Inclusive 101](https://inclusive.microsoft.design/articles/inclusive-101-guidebook) | Persona Spectrum section: "related mismatches and motivations across a spectrum of permanent, temporary, and situational scenarios". The preceding one-arm, wrist-injury, and infant-holding example illustrates extending a solution across that spectrum; applying it to attention is this skill's inference | PASS |
| <a id="source-24"></a>24 | In human-technology transactive memory, external storage can shift the requirement from remembering information to remembering how to locate it | [Risko & Gilbert — Cognitive Offloading (2016), author manuscript at UCL](https://discovery.ucl.ac.uk/id/eprint/1508770/1/gilbert_TiCS_OFFLOADING_RPS.pdf) | Offloading Memory – Transactive Memory, manuscript pp. 9–10: "a shift from remembering ‘what’ to remembering ‘where’". The file example requires remembering its location; the review also describes reduced recall of content expected to remain externally available | PASS — replacement for row 21 |

**Mislinked source, corrected.** The proposed Hagger URL,
[PMC5329006](https://pmc.ncbi.nlm.nih.gov/articles/PMC5329006/), is a 2017 commentary by Drummond
and Philipp, not the 2016 registered replication. Row 18 uses the primary journal's abstract.
Its null result concerns the tested protocol; it does not establish that subjective decision fatigue
does not exist or that every proposed depletion mechanism is false. The proposed claim that people
widely report decision fatigue was not checked by these sources and is not licensed by this row.

**Overstated claim, corrected.** Buçinca's component-decision result and Need-for-Cognition
moderation pass. Its overall-decision overreliance difference was not significant, and the no-AI
baseline was less preferred than either AI category. Use the measured preference/effectiveness
trade-off, not an unconditional claim that users disliked or least preferred forcing functions.
Need for Cognition is a motivational trait measured in this study, not fatigue or ADHD.

**Goal claim, qualified.** Chernev's decision-goal moderator describes decision intent and effort
minimization; it does not directly test whether asking users to clarify a goal reduces overload.
Locke and Latham distinguish learning goals from performance goals and note that specificity alone
does not guarantee high performance. Accepting exploratory goals and offering inferred goals are
product inferences, not interventions validated in these studies.

**Misattributed offloading claim, corrected.** The content-to-location claim belongs to Risko and
Gilbert's 2016 review, not Gilbert et al. 2020. The review supports remembering where saved material
can be retrieved; it does not support a guarantee that offloaded content will be remembered
internally. Showing a note's location and how to reopen it remains an untested product inference.

## Re-check cadence

Government and standards pages get revised. Re-run this check:

- before every public release, and
- at least every 6 months (next due **2027-02-04**).

Re-checking is the same fetch-and-compare per row. The Promptfoo harness (when built) can automate
rows 1–4 as a faithfulness eval; a human still confirms anything that drifted.

## Scope note

This record covers *citation faithfulness only*. It does not establish that the framing is clinically
sound or safe to publish as an accessibility aid — that is Track B (human clinician review), captured
in [reviewer-questionnaire.md](reviewer-questionnaire.md).

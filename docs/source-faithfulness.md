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

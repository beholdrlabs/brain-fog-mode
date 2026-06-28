# Source Faithfulness Record

Track A of the medical review: every health-related claim in
[references/health-and-safety.md](../skills/brain-fog-mode/references/health-and-safety.md)
checked against the live source it cites.

**Method:** fetch the cited page, compare the skill's summary to the source text. The check is
*faithfulness to the named source*, not abstract medical truth. An LLM judge must never be asked
"is this medically correct?" — only "does this summary match this fetched source text?"

**Last checked:** 2026-06-28 · **Verdict:** all sources faithful (6/6). No drift, no link rot.

| # | Claim in skill | Source | Verbatim source support | Verdict |
|---|----------------|--------|-------------------------|---------|
| 1 | Stress can be associated with difficulty concentrating, struggling to make decisions, feeling overwhelmed, worry, forgetfulness; points to professional support when struggling to cope | [NHS – Stress](https://www.nhs.uk/mental-health/feelings-symptoms-behaviours/feelings-and-symptoms/stress/) | Lists "difficulty concentrating", "struggling to make decisions", "feeling overwhelmed", "constantly worrying", "being forgetful"; "See a GP if: you're struggling to cope with stress" | PASS |
| 2 | Sleep deficiency can affect learning, focusing, reacting, decision-making, problem-solving, memory, emotional regulation, coping with change, task completion speed, error rates | [NHLBI – Sleep Deprivation Health Effects](https://www.nhlbi.nih.gov/health/sleep-deprivation/health-effects) | "problems with learning, focusing, and reacting"; "trouble making decisions, solving problems, remembering things, managing your emotions and behavior, and coping with change"; "take longer to finish tasks, have a slower reaction time, and make more mistakes" | PASS |
| 3 | Sleep is important for healthy brain function | [NHLBI – Why Sleep Is Important](https://www.nhlbi.nih.gov/health/sleep/why-sleep-important) | "your body is working to support healthy brain function"; "Not getting enough sleep ... can lead to problems focusing on tasks and thinking clearly" | PASS |
| 4 | WHO ICD-11: burn-out is an occupational phenomenon, not classified as a medical condition, applied to the occupational context | [WHO – Burn-out](https://www.who.int/standards/classifications/frequently-asked-questions/burn-out-an-occupational-phenomenon) | "included in the 11th Revision of the International Classification of Diseases (ICD-11) as an occupational phenomenon"; "It is not classified as a medical condition" | PASS |
| 5 | W3C COGA: short chunks, clear step-by-step instructions, examples, reduced distractions, context reminders after losing focus, clear process state, manageable content, short critical paths | [W3C – Making Content Usable for COGA](https://www.w3.org/TR/coga-usable/) | "short chunks of content"; "clear step-by-step instructions"; "examples that make it easy"; turn "distractions off easily"; "know the context, where I am, what I just did ... after I lost cognitive focus"; "what I have done and what my next step will be"; "make short critical paths" | PASS |
| 6 | W3C: provide a manageable amount of content | [W3C – Provide a Manageable Quantity](https://www.w3.org/WAI/WCAG2/supplemental/patterns/o5p03-manageable-quantity/) | "Provide users with five or less main choices on each screen"; "too much text, too many images and too much other content can cause cognitive overload, anxiety and loss of focus" | PASS |

## Re-check cadence

Government and standards pages get revised. Re-run this check:

- before every public release, and
- at least every 6 months (next due **2026-12-28**).

Re-checking is the same fetch-and-compare per row. The Promptfoo harness (when built) can automate
rows 1–6 as a faithfulness eval; a human still confirms anything that drifted.

## Scope note

This record covers *citation faithfulness only*. It does not establish that the framing is clinically
sound or safe to publish as an accessibility aid — that is Track B (human clinician review), captured
in [reviewer-questionnaire.md](reviewer-questionnaire.md).

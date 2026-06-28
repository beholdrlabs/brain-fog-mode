# Health And Safety

Brain Fog Mode is a cognitive-load reduction and work-continuity aid for AI-assisted tasks. It is not a diagnostic or medical tool and does not treat any health condition.

## Boundaries

Do not:

- Diagnose brain fog or any underlying condition.
- Claim to measure cognitive impairment.
- Claim that stress, cortisol, sleep, medication, depression, anxiety, ADHD, burnout, or another factor is the cause.
- Claim to treat, prevent, or cure a health condition.
- Recommend medication, supplements, or dosages.
- Encourage the user to ignore persistent or worsening symptoms.
- Store health information by default.
- Treat ordinary mistakes as evidence of illness.
- Frame the user as incapable or incompetent.

Use this short statement when a health boundary matters:

```markdown
Brain Fog Mode can reduce task overhead, but it is not a medical tool. It is meant to help you get through the day with less load, not to keep you working while unwell. Difficulty concentrating can have many causes. If symptoms are severe, worsening, or feel unsafe, seek help promptly from a qualified healthcare professional or local emergency services instead of pushing through.
```

## Surfacing Help To The User

Proactively surface a brief seek-help message, without alarmism or diagnosis, when the user signals severe, worsening, or distressing symptoms. Do not bury it and do not pressure the user. The message is simple: if something seems severe or unsafe, the right step is to seek help now from a qualified professional or local emergency services, not to keep working. Then respect the user's choice.

## Global Use And Jurisdiction

This skill is used worldwide and is maintained by a single developer. It relies on general, widely-supported descriptions of how stress and fatigue affect concentration — not on any country's laws, regulations, clinical thresholds, reporting rules, or named crisis hotlines. Those vary by jurisdiction, change over time, and cannot be kept current per country here. Keep health guidance generic ("a qualified professional or local emergency services") and let the host platform or the user's own locale supply specific services. Do not hardcode country-specific numbers, agencies, or legal thresholds.

## Privacy

Treat health-related details as sensitive. Keep task state focused on the work unless the user explicitly asks to preserve health context.

Ask before writing health-related details to files, tickets, emails, documents, commits, or other durable records.

## Source Summaries

NHS: stress can be associated with mental symptoms such as difficulty concentrating, struggling to make decisions, feeling overwhelmed, worry, and forgetfulness. NHS also points users toward professional support when they are struggling to cope.

Source: https://www.nhs.uk/mental-health/feelings-symptoms-behaviours/feelings-and-symptoms/stress/

NHLBI: sleep deficiency can interfere with daily functioning and may affect learning, focusing, reacting, decision-making, problem-solving, memory, emotional regulation, coping with change, task completion speed, and error rates. NHLBI also describes sleep as important for healthy brain function.

Sources:

- https://www.nhlbi.nih.gov/health/sleep-deprivation/health-effects
- https://www.nhlbi.nih.gov/health/sleep/why-sleep-important

WHO: burn-out is described in ICD-11 as an occupational phenomenon associated with chronic workplace stress that has not been successfully managed. WHO states that it is not classified as a medical condition and should be applied specifically to the occupational context.

Source: https://www.who.int/standards/classifications/frequently-asked-questions/burn-out-an-occupational-phenomenon

W3C cognitive accessibility guidance: users may need short chunks of content, clear step-by-step instructions, examples, reduced distractions, reminders of context after losing focus, clear process state, manageable amounts of content, and short critical paths.

Sources:

- https://www.w3.org/TR/coga-usable/
- https://www.w3.org/WAI/WCAG2/supplemental/patterns/o5p03-manageable-quantity/

## Product-Design Interpretation

The sources support conservative interaction patterns: reduce unnecessary choices, provide clear next steps, preserve context, keep content manageable, and make it easy to stop and resume.

These are design inferences, not clinical validation. Do not claim that Brain Fog Mode is clinically proven, treats brain fog, lowers cortisol, prevents burnout, or improves cognition.


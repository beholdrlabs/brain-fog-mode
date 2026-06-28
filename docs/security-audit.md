# Security Audit

Date: 2026-06-28 - Scope: the `brain-fog-mode` skill repository.

## Status

In progress. No blocking issue has been found in the static repository review so far, but the audit is
not complete until the remaining checks below are closed.

## What ships vs what does not

- **Published skill:** `skills/brain-fog-mode/` (what `npx skills` installs).
- **Repo-only public artifacts:** `docs/` (audit, reviewer, and source-faithfulness records).
- **Local-only internal artifacts:** `.beholdr/` internal notes and eval planning. This path is
  gitignored and should not be published.

## Checked so far

- Repository is text-only: Markdown, JSON evals, and templates. No executable package code ships.
- Frontmatter is present; eval JSON files parse.
- No secrets, credentials, hidden network calls, install scripts, or exfiltration instructions were
  found in the shipped skill files during static review.
- No prompt-injection or instruction-hijack directives were found in the skill body during static
  review.
- Health-source summaries were checked for faithfulness on 2026-06-28: 6/6 passed. See
  [source-faithfulness.md](source-faithfulness.md).
- A previous local-path leak in `README.md` was fixed by removing the tool-specific validator path.

## Open items

1. **Security scan still needed.** Run a local secret/security scan before public release. Do not use
   hosted scanners on private repo content without explicit approval and a clear data-handling review.
2. **Behavioral evals not yet automated.** Build a repeatable eval gate over trigger behavior, response
   shape, safety boundaries, source faithfulness, accuracy, and token spend.
3. **Human safety review still needed.** Collect informal scoped review from qualified reviewers,
   especially psychologists or clinicians, using [reviewer-questionnaire.md](reviewer-questionnaire.md).
4. **Runtime caveat.** Static review does not prove runtime injection resistance. Runtime safety depends
   on the host agent, model behavior, tool permissions, and how the skill is installed.

## Beta audit checklist

- [x] Published files are text-only
- [x] Eval JSON files parse
- [x] No local paths or usernames in shipped files
- [x] Health-source faithfulness checked on 2026-06-28
- [x] Local `quick_validate` passes
- [ ] Local secret/security scan clean
- [ ] Behavioral eval harness created
- [ ] LLM-as-judge eval pass reviewed by a human
- [ ] Human safety review collected and attributed with permission

## Next audit update

Update this file when the first repeatable eval harness run exists or when reviewer feedback changes
the skill text.

# Changelog

## [0.3.0-beta] — 2026-10-02

### Added

- Goal Check: when direction is unclear, offer likely goals before recommending or starting work. Clear goals and learning goals proceed directly.
- Decision support that stays active through clarification replies and ends when the decision is answered or the task changes.
- Guidance for choosing one useful first step in broad sales, learning, and agent-efficiency requests while preserving complete deliverables such as recipes and drafts.
- Structured result reports that expose user decisions, the most useful check, unverified work, and remaining notes.
- Stronger continuity cues: restart actions tied to an event, saved-note locations, and instructions for reopening them.
- Guidance for digesting agent and tool output, including hidden commitments, hard-to-undo decisions, uncertainty, and embedded instructions.
- Recorded comparisons with and without the skill; the real shop website address and links are removed from the sales example.
- A direction and roadmap document, expanded research-source records, and a refreshed social preview image displayed in the README.

### Changed

- Questions use short lettered choices or direct factual answers, accept “not sure,” and avoid speculative plans before a blocking answer.
- Small reversible choices proceed within authorized scope; taste-dependent defaults include a way to switch, while consequential actions still require authorization.
- Simplification preserves requested outcomes, complete usable deliverables, and every high-risk issue while reducing unnecessary commentary.
- Health-related redirects explicitly distinguish task assistance from diagnosis or treatment and offer a concrete practical aid.
- Expanded evaluation definitions to 30 behavioral cases and 38 activation cases; retained 10 safety probes.
- Reworked the repository and skill READMEs around decisions, review, and continuity, with clearer evidence boundaries and beta limitations.

### Validation

- Release checks cover skill structure, evaluation JSON and case counts, local documentation links, version consistency, whitespace, and a local secret scan.
- Recorded examples are preserved; they are not rerun for this release. Evaluation definitions are not results from a new behavioral run.
- Automated behavioral evaluation and human safety review remain open beta work. User benefits remain unproven.

## [0.2.1-beta] — 2026-08-07

- Separated session mode, one-answer simplification, and scoped decision support.
- Improved activation, safety and privacy boundaries, source faithfulness, and pause/restart behavior.
- Reorganized the skill and references and added structured feedback guidance.
- See the published release for the original evaluation results and full notes.

[0.3.0-beta]: https://github.com/beholdrlabs/brain-fog-mode/releases/tag/v0.3.0-beta
[0.2.1-beta]: https://github.com/beholdrlabs/brain-fog-mode/releases/tag/v0.2.1-beta

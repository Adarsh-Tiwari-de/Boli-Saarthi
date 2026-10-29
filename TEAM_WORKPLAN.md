# Team Workplan

This is a suggested division of work. Assign owners and backups as a team; this document does not imply implementation has started.

| Workstream | Responsibilities | Deliverables |
|---|---|---|
| Product/UX | User journey, language scope, wireframes, usability script | Flow and UI copy |
| Frontend | Input, progress/error states, editable draft, confirmation | Responsive UI |
| Backend | API, validation, orchestration, persistence | Endpoints and service layer |
| Speech | ASR provider evaluation and language testing | Speech adapter and test set |
| Catalog AI | Schema, prompts, provenance, uncertainty | Draft generation service |
| QA/demo | Synthetic cases, end-to-end checks, latency measurements | Test report and demo script |
| Repo/release | CI, environment setup, deployment, issue board | Setup guide and release checklist |

## Milestones
### M0 — Align
- [ ] Choose stack, first languages, and product category.
- [ ] Create issues for P0 requirements.
- [ ] Assign an owner and reviewer to each issue.
- [ ] Record decisions in `docs/DECISIONS.md`.

### M1 — Skeleton
- [ ] Initialize framework once.
- [ ] Add lint/test commands.
- [ ] Confirm a teammate can clone and run it.
- [ ] Implement mock speech and catalog adapters.

### M2 — Core flow
- [ ] Image + audio/text input.
- [ ] Validated listing draft.
- [ ] Editable review screen.
- [ ] Explicit confirmation and save.
- [ ] Retry/error handling.

### M3 — AI integration
- [ ] Add one speech provider and one catalog model behind adapters.
- [ ] Test clear, noisy, incomplete, conflicting, and missing inputs.
- [ ] Document limitations and cost assumptions.

### M4 — Demo hardening
- [ ] End-to-end tests on clean checkout.
- [ ] Measure latency and task completion.
- [ ] Remove secrets and private data.
- [ ] Prepare mock fallback if APIs fail.
- [ ] Distinguish implemented features from future plans.

Each issue should have an owner, acceptance criteria, dependencies, and verification plan.

# Contributing

## Before coding
1. Read README, PRD, and ARCHITECTURE.
2. Choose an issue and agree on acceptance criteria.
3. Confirm dependencies and coordinate overlapping work.

## Branch naming
- `feat/12-voice-upload`
- `fix/18-image-validation`
- `docs/7-setup-guide`
- `test/23-schema-cases`

Use the real issue number.

## Commit messages
Examples: `feat: add image upload`, `fix: handle ASR timeout`, `test: cover missing fields`, `docs: update setup guide`.

## Pull requests
- Keep each PR focused on one issue.
- Link the issue and describe the change.
- Include tests/commands run and manual verification steps.
- Add screenshots for UI changes when useful.
- Request at least one teammate review.
- Do not merge failing checks or code the team cannot explain.

## Code quality
- Validate inputs at system boundaries.
- Treat model output as untrusted and validate it.
- Handle errors explicitly.
- Do not fabricate missing product facts.
- Add tests for bug fixes and non-trivial logic.
- Update docs when setup, API, schema, or behavior changes.

## Secrets and data
Never commit `.env`, keys, tokens, private seller details, unconsented media, dependency folders, or build output. If a key is exposed, revoke/rotate it immediately; deleting it in a later commit is not enough.

## Definition of done
- [ ] Acceptance criteria met.
- [ ] Tests pass or limitations are recorded.
- [ ] No secrets/private data included.
- [ ] Error and uncertainty paths considered.
- [ ] Documentation updated.

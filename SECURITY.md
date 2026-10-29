# Security and Responsible Data Handling

Do not post credentials, private seller data, or vulnerability details in public issues. Use the repository's private security reporting option/contact if configured.

## Secrets
- Keep credentials in local environment files or an approved secret manager.
- Commit only placeholder variables.
- Never expose provider keys in browser code.
- Revoke/rotate exposed keys immediately.

## User content
- Prefer synthetic or explicitly consented test data.
- Review provider terms/privacy practices before sending audio or images to third parties.
- Avoid logging raw content.
- Define retention/deletion before collecting real seller data.
- Do not claim encryption or regulatory compliance unless verified.

## AI output
- Treat generated fields as suggestions.
- Do not fabricate price, stock, material, origin, or certification.
- Require seller review and confirmation.
- HSN/category output is advisory and must be independently verified.

Before public deployment, review upload validation, auth, authorization, rate limits, CORS, logging, retention, and dependency security. This starter is not a security certification.

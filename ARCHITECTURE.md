# Proposed Architecture

**Status:** Proposal. Update after team decisions.

```text
Seller Web UI
  ├─ photo + voice/text input
  ├─ progress and error states
  └─ editable draft + explicit confirmation
            |
            v
Backend API / Orchestrator
  ├─ upload validation and limits
  ├─ Speech Adapter → selected ASR provider
  ├─ Catalog Adapter → selected multimodal model
  ├─ schema validation + uncertainty handling
  └─ save confirmed draft
            |
            v
Demo storage (local or selected database)

Later/optional: TTS adapter and ONDC/Beckn sandbox adapter
```

## Request flow
1. UI submits image plus audio or text.
2. API validates request size, file type/content, and required inputs.
3. Speech adapter transcribes audio if present.
4. Catalog adapter generates a draft using transcript and image.
5. Output is validated against the listing schema.
6. Missing/uncertain fields remain null or are marked for confirmation.
7. Seller reviews and edits the draft.
8. Explicit confirmation saves the draft.
9. Live marketplace publishing is a separate, later flow.

## Boundaries
- Provider-specific logic stays behind adapters.
- Secrets are backend-only.
- Do not log raw audio, images, tokens, or unnecessary personal data.
- Third-party AI processing must be disclosed before real-user testing.
- A confirmed draft is not the same as a marketplace-published listing.

## Failure behavior
- Invalid upload: reject with clear message.
- Speech provider unavailable: retry or use text fallback.
- Model timeout/invalid output: recoverable error; never fabricate output.
- Unknown field: ask seller or leave unknown.
- Save failure: do not show success.
- ONDC unavailable: draft workflow still works.

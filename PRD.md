# Product Requirements Document — Boli-Saarthi
**Version:** 0.1 | **Status:** Proposed, team review required

## 1. Summary
Boli-Saarthi aims to reduce the effort required for small sellers to create online product listings. The seller provides a photo and a voice or text description. The system drafts structured fields and the seller reviews, edits, and confirms them.

## 2. Problem
Typing, translating, and completing structured catalog forms can be a barrier for sellers who prefer regional-language voice interaction. Validate this assumption with actual sellers; do not treat it as universally true.

## 3. Users
- Artisans and makers selling physical products.
- Micro-retailers with small product catalogs.
- Seller-support teams helping vendors prepare listings.

## 4. Goals
- Demonstrate input → transcript → structured draft → seller review → saved draft.
- Support a small, explicitly documented language set.
- Validate AI output against a schema.
- Mark uncertain fields as unknown or ask a clarification question.
- Require explicit seller confirmation.

## 5. Non-goals for the MVP
- Production marketplace operations or live ONDC publishing.
- Guaranteed support for every Indian language or dialect.
- Authoritative tax/HSN advice.
- Payments, shipping, seller payouts, or order management.

## 6. Core user story
As a small seller, I want to describe my product by voice and provide a photo, so I can review a structured listing without typing every field manually.

## 7. MVP user journey
1. Select a supported language.
2. Upload/take a product photo and record/upload a voice note, or enter text.
3. Server validates file type and size.
4. Speech adapter transcribes audio; text input skips transcription.
5. Catalog service creates schema-constrained listing draft.
6. UI displays transcript, draft fields, and items needing confirmation.
7. Seller edits and explicitly confirms.
8. System saves a confirmed draft and shows success.
9. Seller can retry, discard, or start another draft.

## 8. Functional requirements
| ID | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| FR-01 | Image input | P0 | Supported formats/limits documented; invalid files show useful errors. |
| FR-02 | Voice or text input | P0 | Voice flow works or documented text fallback is available; at least one is required. |
| FR-03 | Speech transcription | P0 | Configured languages return a transcript or recoverable error. |
| FR-04 | Structured draft | P0 | Output matches schema; malformed output is safely rejected/retried. |
| FR-05 | Edit and review | P0 | Seller can edit generated fields before confirmation. |
| FR-06 | Uncertainty handling | P0 | Unknown fields stay unknown; no silent fabrication. |
| FR-07 | Confirm/save | P0 | Explicit confirmation required; persistence failures do not show false success. |
| FR-08 | Retry/error states | P1 | Provider failures offer retry and preserve user-entered text where practical. |
| FR-09 | Bilingual output | P1 | Works for the language pair explicitly configured for the demo. |
| FR-10 | HSN suggestion | P2 | Optional, advisory, clearly labeled, independently verifiable. |
| FR-11 | ONDC adapter | P2 | Sandbox/mock only unless live integration is separately verified. |
| FR-12 | Text-to-speech read-back | P2 | Optional; text remains available to inspect. |

P0 = MVP required; P1 = desirable; P2 = later/conditional.

## 9. Initial listing schema
Suggested fields: `title`, `description`, `category`, `materials[]`, `color`, `dimensions`, `price`, `currency`, `quantity_available`, `language`, `field_sources`, `needs_confirmation[]`, `status`.

Do not infer price, quantity, exact material, certification, or origin without seller input/confirmation. Store unknown values as `null`.

## 10. Non-functional requirements
- Secrets remain server-side.
- Validate uploads and set documented size/time limits.
- Minimize retention of audio and photos; disclose third-party processing.
- Provide useful errors and retry paths.
- Use accessible labels and text alternatives for audio.
- Keep AI providers replaceable behind adapters.
- Measure latency and quality; do not claim the 15-second target is achieved until tested.

## 11. Success metrics to measure
- Task completion rate.
- Median and p90 time to confirmed draft.
- Field correction rate.
- Clarification rate.
- Human-reviewed transcription quality for selected languages.
- Upload/provider/save failure rate.
- User-reported ease of use.

Set thresholds and sample size before testing. Do not invent results.

## 12. Risks
- Dialect/noise errors → test, disclose language limits, allow correction.
- Hallucinated attributes → schema validation, provenance, unknowns, seller confirmation.
- HSN errors → advisory only, independent verification.
- API outage/cost → mock mode, provider adapters, rate limits.
- Privacy risks → synthetic data for demos, consent, minimal retention.
- ONDC scope creep → defer live publishing until core flow works.

## 13. Open decisions
- Which two or three languages first?
- Which product category and required fields?
- Next.js route handlers or separate backend?
- Which speech and multimodal providers?
- Where are drafts stored?
- Mock or sandbox ONDC demonstration?
- What license and deployment target?

## 14. Release checklist
- [ ] Stack and scope agreed.
- [ ] Core flow works end-to-end.
- [ ] At least five representative synthetic cases tested.
- [ ] Uncertain fields remain editable/unknown.
- [ ] A teammate has tested setup from a clean clone.
- [ ] No secrets or real personal data are committed.
- [ ] Limitations and measured results are documented.

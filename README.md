# Boli-Saarthi
**Speak your language. List your products. Reach digital markets.**

Boli-Saarthi is a proposed voice-first catalog onboarding copilot for Indian artisans and micro-retailers. A seller provides a product photo and a short voice note; the system drafts a structured listing for the seller to review and confirm.

- **Team:** The Debugger
- **Institution:** Echelon Institute of Technology, Faridabad
- **Track:** Artificial Intelligence
- **Status:** Hackathon concept / prototype. Do not claim features are implemented until verified.

## MVP flow
1. Seller uploads a product photo and provides voice or text.
2. A speech adapter transcribes voice in explicitly supported languages.
3. A catalog AI adapter drafts structured fields from the transcript and image.
4. The seller edits and confirms the draft.
5. The draft is saved in demo storage. Live ONDC publishing is out of scope until separately implemented and verified.

## Repository structure
- `PRD.md` — product requirements and acceptance criteria
- `ARCHITECTURE.md` — proposed system design and boundaries
- `CONTRIBUTING.md` — branch, commit, PR, and review rules
- `TEAM_WORKPLAN.md` — suggested workstreams and milestones
- `SECURITY.md` — secrets, user data, and responsible AI rules
- `docs/API_CONTRACT.md` — proposed endpoints
- `docs/DATA_MODEL.md` — initial listing data model
- `docs/TEST_PLAN.md` — unit, integration, and demo cases
- `docs/DECISIONS.md` — decision log
- `frontend/`, `backend/`, `services/`, `integrations/`, `tests/` — workstream guidance

These files are a planning scaffold; empty folders do not imply implementation.

## Suggested stack (not yet locked)
- Frontend: Next.js + React + TypeScript
- Backend: Next.js route handlers or a separate Node.js API (choose one)
- Speech: Bhashini or another reviewed provider behind an adapter
- Catalog AI: selected multimodal model behind a server-side adapter
- Storage: demo/local storage initially
- ONDC: optional later integration after protocol and sandbox review

## Getting started
1. Read `PRD.md`, `ARCHITECTURE.md`, and `TEAM_WORKPLAN.md`.
2. Agree on the first supported languages, product category, and stack.
3. Create GitHub issues from the MVP requirements and assign an owner plus reviewer.
4. Clone the repo and create a feature branch.
5. Do not create duplicate app scaffolds until the stack decision is recorded.

After a framework is initialized, add exact install/run/test commands here.

## Safety principles
- Seller confirmation is required before a draft is treated as approved.
- Do not invent price, stock, material, origin, or certification.
- Any HSN suggestion is advisory and requires independent verification.
- Keep API keys server-side; never commit `.env` files or private seller data.
- Measure performance claims such as a “15-second listing”; do not present targets as results.

## References
- ONDC: https://ondc.org/
- Bhashini: https://bhashini.gov.in/
- AI4Bharat: https://ai4bharat.iitm.ac.in/
- Beckn: https://becknprotocol.io/

No partnership or endorsement is implied. Select a repository license before publishing reusable code publicly.

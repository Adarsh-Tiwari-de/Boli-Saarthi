# Proposed API Contract

Adapt these paths to the selected framework.

## POST `/api/listing-drafts`
Multipart fields: `image` (required), `audio` (optional), `text` (optional), `language`. At least one of audio or text is required.

Illustrative success:
```json
{
  "draft_id": "draft_demo_001",
  "status": "needs_review",
  "transcript": {"text": "seller-provided transcript", "language": "hi"},
  "listing": {
    "title": null,
    "description": null,
    "category": null,
    "materials": [],
    "color": null,
    "price": null,
    "quantity_available": null
  },
  "needs_confirmation": ["title", "description", "category", "price"]
}
```

## PATCH `/api/listing-drafts/{draft_id}`
Accept seller-edited fields; validate field types, lengths, and allowed values server-side.

## POST `/api/listing-drafts/{draft_id}/confirm`
Requires an explicit user action. Confirmation means seller approved the draft; it does not mean it was published to ONDC.

## Rules
- Document upload size and time limits.
- Validate file content, not just filename extensions.
- Use stable error codes and request IDs.
- Never log raw uploads or secrets.
- Add auth/authorization before multi-user production use.

# Test Plan

## Unit tests
- Reject unsupported/oversized files.
- Require audio or text input.
- Validate listing schema and field types.
- Reject malformed model output safely.
- Keep missing facts unknown.
- Prevent confirmation before review.
- Ensure errors/logs do not leak secrets.

## Integration tests
- Mock ASR → mock catalog → schema validation → review/save.
- ASR failure offers retry/text fallback.
- Model timeout returns recoverable error.
- Storage failure never returns false success.
- Seller edits persist to the right draft.

## Demo cases
1. Clear voice note + product image.
2. Text fallback + image.
3. Noisy/incomplete speech.
4. Image contains details absent from voice.
5. Conflicting transcript and image suggestion.
6. Unsupported language.
7. Invalid or oversized upload.
8. Simulated provider outage.

Record commit, date, test data type, language/conditions, pass/fail, measured latency, and limitations. Do not present sample data as measured results.

# Initial Data Model

| Field | Type | Notes |
|---|---|---|
| `id` | string | Generated identifier |
| `status` | enum | `draft`, `needs_review`, `confirmed`, `discarded` |
| `title` | string/null | Seller editable |
| `description` | string/null | Draft description |
| `category` | string/null | Prefer a defined taxonomy |
| `materials` | string array | Only if provided/confirmed |
| `color` | string/null | Seller confirms |
| `dimensions` | object/null | Do not infer scale without a reference |
| `price` | number/null | Seller-provided/confirmed |
| `currency` | string | Use INR where applicable |
| `quantity_available` | integer/null | Seller-provided/confirmed |
| `language` | string | Draft language |
| `transcript` | string/null | Define retention/deletion |
| `field_sources` | object | Image, transcript, seller edit, etc. |
| `needs_confirmation` | string array | Fields requiring review |
| `created_at`, `updated_at` | timestamp | UTC recommended |

Keep AI-generated and seller-confirmed data distinguishable. Unknown values remain null. Minimize retention of original media.

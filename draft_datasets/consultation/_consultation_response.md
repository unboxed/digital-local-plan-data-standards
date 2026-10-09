# Proposed dataset for further iteration: consultation-response

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes |  |
| `consultation` | string | 1 | yes | Reference to the `consultation` dataset |
| `question` | string | 1 |  | Consultation question |
| `comment` | text | 1 | yes | Representation text |
| `response` | text | 1 |  | Policy officer's response |
| `development-policy-categories` | string | n |  | References to the existing `development-policy-category` codelist |
| `notes` | text | 1 |  |  |
| `organisation` | curie | 1 | yes | LPA |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes |  |
| `entry-date` | datetime | 1 | yes |  |

This is a draft proposed dataset that does not currently exist in draft or published form.

# Proposed dataset for further iteration: representation

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes |  |
| `consultation` | string | 1 | yes | Reference to the `consultation` dataset |
| `comment` | text | 1 | yes | Representation text |
| `development-policy-categories` | string | n |  | References to the existing `development-policy-category` codelist |
| `notes` | text | 1 |  |  |
| `organisation` | curie | 1 | yes | LPA |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes |  |
| `entry-date` | datetime | 1 | yes |  |

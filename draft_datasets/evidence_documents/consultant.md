This is a draft proposed dataset that does not currently exist in draft or published form.

# Proposed dataset for further iteration

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | Unique identifier for the consultant |
| `name` | string | 1 | yes | |
| `company` | string | 1 | | Reference to the `company` dataset |
| `consultant-type` | string | 1 | yes | Reference to the `consultant-type` codelist |
| `prefix` | string | 1 | yes | |
| `entity` | integer | 1 | yes | |
| `entry-date` | datetime | 1 | yes | |
| `start-date` | datetime | 1 | | |
| `end-date` | datetime | 1 | | |

This is a draft proposed dataset that does not currently exist in draft or published form.

# Proposed dataset for further iteration: consultation

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | Unique identifier for the consultation |
| `name` | string | 1 | yes |  |
| `local-plan` | string | 1 | yes |  The local plan this consultation is for 
| `consultation-type` | string | 1 | yes | Which consultation this is, e.g. `scoping`. Its start and end dates are the matching events in `plan-timetable`, e.g. `scoping-consultation-start` and `scoping-consultation-end` |
| `documentation-url` | url | 1 |  | Consultation page on the authority's website |
| `organisation` | curie | 1 | yes | LPA |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes |  |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

---
title: Development Policy Metric
status: Alpha Co-design Draft
target-dataset: development-policy-metric
typology: metric
---

The [development-policy-metric](https://digital-land.github.io/specification/dataset/development-policy-metric/) dataset applies to:
- A measurable value set by a development policy.
- Use this with development-metric to find the kind of measurement, and development-policy to find the policy it comes from.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | Unique identifier for the metric |
| `name` | string | 1 | yes |  |
| `development-policy` | string (CURIE) | 1 | yes | Reference to the `development-policy` the metric belongs to |
| `development-metric` | string (CURIE) | 1 | yes | Reference to the `development-metric` codelist |
| `value` | string | 1 |  | e.g. `35` |
| `period-start-date` | datetime | 1 |  | Start of the period the value applies to |
| `period-end-date` | datetime | 1 |  | End of the period the value applies to |
| `notes` | text | 1 |  |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

## Scope for co-design

* What metrics do policies set that need to be published as data?

### References
- `development-policy`, through its `development-policy` field.
- `development-metric`, through its `development-metric` field.

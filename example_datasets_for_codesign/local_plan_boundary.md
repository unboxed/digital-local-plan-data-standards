---
title: Local Plan Boundary
status: Alpha Co-design Draft - no changes proposed yet
target-dataset: local-plan-boundary
typology: geography
---

The [local-plan-boundary](https://digital-land.github.io/specification/dataset/local-plan-boundary/) dataset applies to:
- The area covered by a local plan. For example, a single authority's area or the combined area of a joint plan.
- Use this with local-plan to find the plan that covers an area.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | Unique identifier for the boundary |
| `name` | string | 1 | yes |  |
| `description` | string | 1 |  |  |
| `geometry` | multipolygon | 1 |  | The boundary of the plan area |
| `point` | point | 1 |  |  |
| `local-planning-authorities` | string (List) | n |  | References to the local planning authorities within the boundary |
| `organisations` | string (List) | n |  |  |
| `notes` | text | 1 |  |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

### Referenced by
- `local-plan`, through its `local-plan-boundary` field.
- `development-plan`, `plan` and `supplementary-plan`.

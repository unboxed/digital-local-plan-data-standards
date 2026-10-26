---
title: Proposed Dataset for Development Policy Type
status: Alpha Co-design Draft
target-dataset: development-policy-type
typology: category
---

This is a draft proposed dataset that does not currently exist in draft or published form.

This proposed dataset applies to:
- The type of a development policy, e.g. 'strategic', 'non-strategic'.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | e.g. `strategic` |
| `name` | string | 1 | yes | e.g. `Strategic` |
| `description` | string | 1 |  | Public definition of the type, so it is applied consistently |
| `notes` | text | 1 |  |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

Proposed entries (draft definitions for co-design):
- `strategic`
- `non-strategic`

## Scope for co-design

* What additional policy types are needed?
* Can a policy have more than one type?

### Referenced by
- `development-policy`, through its `development-policy-type` field.

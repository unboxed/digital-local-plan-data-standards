---
title: Proposed Dataset for Requirement Type
status: Alpha Co-design Draft
target-dataset: requirement-type
typology: category
---

This is a draft proposed dataset that does not currently exist in draft or published form.

This proposed dataset applies to:
- The broad type of a requirement that local plans and their evidence must adhere to, e.g. 'legislation', 'national-policy'.
- Use this with `requirement` to group requirements by type.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | e.g. `legislation` |
| `name` | string | 1 | yes | e.g. `Legislation` |
| `description` | string | 1 |  | Public definition of the type, so it is applied consistently |
| `notes` | text | 1 |  |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

Proposed entries (draft definitions for co-design):
- `legislation` – Acts and regulations, which are statutory
- `national-policy` – e.g. NPPF and national policy statements
- `guidance` – e.g. planning practice guidance and written ministerial statements

## Scope for co-design

* Is a statutory or non-statutory split more useful than these types?

### Referenced by
- `requirement`, through its `requirement-type` field.

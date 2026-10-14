---
title: Proposed Dataset for Consultancy Type
status: Alpha Co-design Draft
target-dataset: consultancy-type
typology: category
---

This is a draft proposed dataset that does not currently exist in draft or published form.

This proposed dataset applies to:
- The specialism of a consultancy commissioned to produce evidence documents that support a development plan, e.g. 'ecology', 'viability'.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | e.g. `ecology` |
| `name` | string | 1 | yes | e.g. `Ecology` |
| `description` | string | 1 |  | Public definition of the specialism, so it is applied consistently |
| `notes` | text | 1 |  | |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

Proposed entries (draft definitions for co-design):
- `viability`
- `ecology`
- `heritage`

## Scope for co-design

* What additional consultancy types are needed, for example transport, landscape, others?

### Referenced by
- `consultancy`, through its `consultancy-types` field.

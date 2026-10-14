---
title: Development Policy Area
status: Alpha Co-design Draft
target-dataset: development-policy-area
typology: geography
---

The [development-policy-area](https://digital-land.github.io/specification/dataset/development-policy-area/) dataset applies to:
- The area a development policy applies to. For example, a site allocation boundary or a town centre.
- Use this with development-policy to find where a policy applies.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | Unique identifier for the area |
| `name` | string | 1 | yes |  |
| `development-policies` | string (List) | n |  | References to the `development-policy` records that apply to this area. One area can have several policies. |
| `geometry` | multipolygon | 1 |  | The boundary of the area |
| `point` | point | 1 |  |  |
| `document-url` | url | 1 |  |  |
| `documentation-url` | url | 1 |  |  |
| `notes` | text | 1 |  |  |
| `organisation` | string (CURIE) | 1 | yes |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

## Scope for co-design

* Is this the right place for the areas shown on a policies map?
* Policies that apply to the whole plan area need an area record nevertheless. Do you agree?
* In addition to the boundary, do you need to list which GIS layers this policy relates to?

### References
- `development-policy`, through its `development-policies` field.

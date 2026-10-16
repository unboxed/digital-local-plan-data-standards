---
title: Local Plan
status: Alpha Co-design Draft - no changes proposed yet
target-dataset: local-plan
typology: legal-instrument
---

The [local-plan](https://digital-land.github.io/specification/dataset/local-plan/) dataset applies to:
- Each current, emerging or historical local plan prepared by a local planning authority.
- Use this with local-plan-boundary to find the area a plan covers, and development-plan-document to find the documents that make it up.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | Unique identifier for the plan |
| `name` | string | 1 | yes |  |
| `description` | string | 1 |  |  |
| `local-plan-boundary` | string (CURIE) | 1 |  | Reference to the `local-plan-boundary` the plan covers |
| `local-plan-process` | string | 1 |  | Reference to the `local-plan-process` codelist |
| `local-planning-authorities` | string (List) | n |  | References to the local planning authorities the plan covers |
| `organisations` | string (List) | n |  | References to the organisations involved, e.g. for joint plans |
| `required-housing` | integer | 1 |  |  |
| `period-start-date` | datetime | 1 |  | Start of the plan period |
| `period-end-date` | datetime | 1 |  | End of the plan period |
| `adopted-date` | datetime | 1 |  |  |
| `dataset` | string | 1 |  | metadata field always set to "local plan" to identify the record standard |
| `document-url` | url | 1 |  |  |
| `documentation-url` | url | 1 |  |  |
| `notes` | text | 1 |  |  |
| `organisation` | string (CURIE) | 1 | yes |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

## Questions
* How does `local-plan` relate to `development-plan` and `development-plan-document`, given a local plan is also a type of development plan document?

### Referenced by
- `local-plan-document`, `local-plan-housing` and `local-plan-timetable` (existing).
- `chapter` (proposed).

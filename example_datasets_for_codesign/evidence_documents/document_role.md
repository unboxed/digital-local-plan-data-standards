---
title: Proposed Extensions for Local Plan Document Dataset
status: Alpha Co-design Draft
target-dataset: document-role
typology: category
---

This proposed dataset applies to:
- The role of a `local-plan-document`, e.g. 'evidence', 'supporting'.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | e.g. `evidence` |
| `name` | string | 1 | yes | e.g. `Evidence` |
| `description` | string | 1 |  | Public definition of the role, so it is applied consistently.|
| `notes` | text | 1 |  | Editorial or internal notes about the entry |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

Proposed entries (draft definitions for co-design):
- `evidence`: a document that provides the justification for policy content, for example a viability study or flood risk assessment.
- `supporting`: a document that accompanies the plan but does not itself justify policy content, for example a consultation statement or policies map.

## Scope for co-design

* What additional roles are needed?
* Are the draft definitions of `evidence` and `background` accurate and distinct enough to be applied consistently?
* Is a role a property of the document itself, or of its relationship to a particular policy?
* In the above sense, can a document have more than one role? This determines whether the role field on `local-plan-document` has a cardinality of 1 or n.
* Should the dataset be named `local-plan-document-role` to avoid clashing with roles for other kinds of document in future?

---
title: Proposed Changes for Development Plan Document Type Dataset
status: Alpha Co-design Draft
target-dataset: development-plan-document-type
typology: category
---

The [development-plan-document-type](https://www.planning.data.gov.uk/dataset/development-plan-document-type) dataset applies to:
- The types of document that make up a development plan. For example, a local plan or a neighbourhood plan.
- Use this with development-plan-document to find the plan document that you are interested in.

Types of evidence document are proposed separately in the [document-type](document-type.md) dataset.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | e.g. `local-plan` |
| `name` | string | 1 | yes |  |
| `description` | string | 1 |  |  |
| `notes` | text | 1 |  |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

Current entries that stay in this dataset:
- `local-plan`
- `area-action-plan`
- `core-strategy`
- `site-allocations`
- `policies-map`
- `supplementary-planning-documents`
- `adoption-statement`
- `inspectors-report`
- `local-development-scheme`
- `local-plan-review`

Current entries proposed to move to `document-type`:
- `strategic-flood-risk-assessment`
- `strategic-housing-market-assessment`
- `viability-assessment`
- `sustainability-appraisal`
- `financial-viability-study` (ended, replaced by `viability-assessment`)
- `sustainability-apprasial` (ended, misspelling of `sustainability-appraisal`)

## Proposed additional entries

| Reference | Description |
| ----- | ----- |
| `neighbourhood-plan` | A plan prepared by a neighbourhood forum or parish council. |

## Scope for co-design

* What plan document types are missing from this list?
* Process documents such as `adoption-statement`, `inspectors-report` and `local-development-scheme` are neither part of the plan nor evidence. Should they stay here or have their own type?
* Published records already use types not listed here, such as `examination-hearing-statement`. Where should these sit?

### Referenced by
- `development-plan-document`, through its `document-types` field.

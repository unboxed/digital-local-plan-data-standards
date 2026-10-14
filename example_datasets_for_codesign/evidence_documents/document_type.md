---
title: Proposed Extensions for Document Type Dataset
status: Alpha Co-design Draft
target-dataset: document-type
typology: category
---

The [document-type](https://www.planning.data.gov.uk/dataset/document-type) dataset applies to:
- The types of evidence document that support a development plan. For example, a strategic flood risk assessment or a viability assessment.
- Use this with document to find the evidence you are interested in.

Types of plan document, such as a local plan, stay in the [development-plan-document-type](development-plan-document-type.md) dataset.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | e.g. `viability-assessment` |
| `name` | string | 1 | yes |  |
| `description` | string | 1 |  |  |
| `notes` | text | 1 |  |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

Current entries in the MHCLG dataset:
- `area-appraisal`
- `notice`
- `article-4-document`
- `authoritative-boundary`
- `extension-report`
- `designation-report`
- `guidance`

## Proposed additional entries

Moved from `development-plan-document-type`:

| Reference | Description |
| ----- | ----- |
| `strategic-flood-risk-assessment` |  |
| `strategic-housing-market-assessment` |  |
| `viability-assessment` |  |
| `sustainability-appraisal` |  |

Ended entries to move with them (have an `end-date`, so no longer in use):
- `financial-viability-study` (replaced by `viability-assessment`)
- `sustainability-apprasial` (misspelling, replaced by `sustainability-appraisal`)

## Scope for co-design

* What evidence types are missing from this list?
* Are there other forms of evidence you would want to store in your evidence base that do not fit this dataset?
* Do you need to represent data that is not stored in documents? What are the user needs associated with non-documentary evidence?

### Referenced by
- `document`, through its `document-types` field.

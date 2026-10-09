This is a published dataset in [the planning.data repository](https://www.planning.data.gov.uk/dataset/development-plan-document-type).

### Existing dataset

Typology: category

This dataset applies to:
- The types of document published for a development plan.
- Use this with development-plan-document to find the plan document that you are interested in. For example, a core strategy.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | e.g. `core-strategy` |
| `name` | string | 1 | yes |  |
| `description` | string | 1 |  |  |
| `notes` | text | 1 |  |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

Current entries in the MHCLG dataset:
- `local-plan`
- `adoption-statement`
- `area-action-plan`
- `inspectors-report`
- `policies-map`
- `strategic-flood-risk-assessment`
- `strategic-housing-market-assessment`
- `supplementary-planning-documents`
- `local-development-scheme`
- `local-plan-review`
- `core-strategy`
- `site-allocations`
- `viability-assessment`
- `sustainability-appraisal`

Ended entries (have an `end-date`, so no longer in use):
- `financial-viability-study` (replaced by `viability-assessment`)
- `sustainability-apprasial` (misspelling, replaced by `sustainability-appraisal`)

## Scope for co-design

* What 'types' are missing from this list? Published records already use types not listed here, such as `examination-hearing-statement`.
* Are there other forms of evidence you would want to store in your evidence base that do not fit this dataset?
* Do you need to represent data that is not stored in documents? What are the user needs associated with non-documentary evidence?

## Sample additional entries

| Reference | Description |
| ----- | ----- |
| `area-appraisal` |  |
| `notice` |  |
| `article-4-document` |  |
| `extension-report` |  |
| `designation-report` |  |

### Referenced by
- `development-plan-document`, through its `document-types` field.

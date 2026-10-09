This is a draft dataset in [the planning.data repository](https://digital-land.github.io/specification/dataset/local-plan-document-type/).

### Existing dataset

Typology: category

This dataset applies to:
- The type of document that an authority is using to create their local plan.
- Use this with local-plan-document to find the plan document that you are interested in. For example, a core strategy.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | e.g. `core-strategy` |
| `name` | string | 1 | yes |  |
| `description` | string | 1 |  |  |
| `notes` | text | 1 |  |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes |  |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

Entries defined in MHCLG specification:
- `local-plan`
- `adoption-statement`
- `area-action-plan`
- `financial-viability-study`
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

## Scope for co-design

* What 'types' are missing from this list?
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
- `local-plan-document`, through its `document-types` field

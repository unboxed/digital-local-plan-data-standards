
This is a draft dataset in [the planning.data repository](https://digital-land.github.io/specification/dataset/local-plan-document-type/)

### Existing dataset

This dataset applies to:
- The type of document that an authority is using to create their local plan.
- Use this with local-plan-document to find the plan document that you are interested in. For example, a core strategy.

| Field | Type | Required | Notes |
| ----- | ----- | ----- | ----- |
| `description` | string |  |  |
| `name` | string |  |  |
| `notes` | text |  |  |
| `entry-date` | datetime |  |  |
| `start-date` | datetime |  |  |
| `end-date` | datetime |  |  |
| `prefix` | string |  |  |
| `reference` | string |  |  |
| `entity` | integer |  |  |

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
- `sustainability-apprasial`
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

- `area-appraisal`
- `notice`
- `article-4-document`
- `authoritative-boundary`
- `extension-report`
- `designation-report`
- `boundary`

### Associations
- `belongs_to` `LocalPlanDocument`

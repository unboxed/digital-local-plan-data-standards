
This is an existing model in the [official datasets list for local plans](https://www.planning.data.gov.uk/dataset/development-plan-document-type).

### Existing dataset

This dataset applies to:
- The type of document that an authority is using to create their overall plan.
- Use this with development-plan-document to find the plan document that you are interested in. For example, a core strategy.

| Field | Type | Required | Notes |
| ----- | ----- | ----- | ----- |
| `description` | string |  |  |
| `entity` | integer |  |  |
| `name` | string |  |  |
| `notes` | text |  |  |
| `prefix` | string |  | for compact URI in MHCLG spec |
| `reference` | string |  |  |
| `entry-date` | datetime |  |  |
| `start-date` | datetime |  |  |
| `end-date` | datetime |  |  |

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

* Is this dataset adequate to store references to all types of documents that make up the evidence base?

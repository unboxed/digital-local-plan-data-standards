---
title: Proposed Changes for Development Metric Dataset
status: Alpha Co-design Draft
target-dataset: development-metric
typology: category
---

The [development-metric](https://digital-land.github.io/specification/dataset/development-metric/) dataset applies to:
- The kind of measurement a development policy sets. For example, the percentage of affordable housing required.
- Use this with development-policy-metric to find the values policies set for each kind of measurement.

The dataset exists in the specification but has no published entries yet.

## Schema Diff
This diff shows the proposed changes to the current `development-metric` dataset.

```diff
  dataset: development-metric
  fields:
    - reference
    - name
+   - description
    - notes
    - prefix
    - entity
    - entry-date
    - start-date
    - end-date
```

## Proposed Field Definitions & Validation Rules

| Field Name | Typology / Type | Cardinality | Required | Notes & Codelist Linkages |
| :--- | :--- | :--- | :--- | :--- |
| `description` | string | 1 | | Public definition of the metric, so it is applied consistently. |

## Proposed Entries
Draft definitions for co-design:
- `affordable-housing-percentage`
- `housing-requirement`

## Questions
* What metrics do policies commonly set that should be standardised?
* Should the unit of measurement (e.g. percentage, number of homes, hectares) be part of the metric definition?

## Mock JSON Payload

```json
{
  "entity": 6001001,
  "prefix": "development-metric",
  "reference": "affordable-housing-percentage",
  "name": "Affordable housing percentage",
  "description": "The minimum percentage of homes on a development that must be affordable housing.",
  "notes": "",
  "entry-date": "2026-10-14T00:00:00Z",
  "start-date": "2026-10-14T00:00:00Z",
  "end-date": ""
}
```

### Referenced by
- `development-policy-metric`, through its `development-metric` field.

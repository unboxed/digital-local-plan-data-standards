---
title: Proposed changes to Development Policy
status: Alpha Co-design Draft
target-dataset: development-policy
typology: policy
---

This proposes changes to the draft [development-policy](https://digital-land.github.io/specification/dataset/development-policy/) dataset in the planning.data repository, so it can be used for local plans. It applies to:
- Each policy in a development plan, including those in a local plan.
- Use this with development-policy-category to find policies on a topic. For example, all affordable housing policies.

## Schema Diff
This diff shows the proposed changes to the draft `development-policy` dataset.

```diff
 dataset: development-policy
  fields:
    - reference
    - name
+   - policy-number
    - description
+   - policy-text
    - development-plan-document
+   - chapter
+   - development-policy-type
    - development-policy-categories
+   - vision
    - notes
    - organisation
    - prefix
    - entity
    - entry-date
    - start-date
    - end-date
```

## Proposed Field Definitions & Validation Rules

| Field Name | Typology / Type | Cardinality | Required | Notes & Codelist Linkages |
| :--- | :--- | :--- | :--- | :--- |
| `reference` | string | 1 | yes | **Changed:** now a unique identifier for the policy. The number used in the plan moves to `policy-number`. |
| `policy-number` | string | 1 | | The number used in the plan, e.g. `H3`. |
| `policy-text` | text | 1 | | The wording of the policy. |
| `development-plan-document` | string (CURIE) | 1 | | Reference to the local plan (which is an instance of development-plan-document) the policy belongs to. A policy belongs to one document, so the reference lives on the policy. |
| `chapter` | string (CURIE) | 1 | | Reference to the proposed `chapter` dataset. |
| `development-policy-type` | string (CURIE) | 1 | | Reference to the proposed `development-policy-type` codelist. |
| `development-policy-categories` | string (List) | n | | References to the `development-policy-category` codelist. |
| `vision` | string (CURIE) | 1 | | Reference to the proposed `vision` dataset. |

## Related Proposed Datasets

* **`chapter`** – A section of a local plan; belongs to `local-plan`.
* **`development-policy-type`** *(Category Typology)* – Standardises policy types, e.g. `strategic`, `non-strategic`.
* **`development-policy-category`** *(Category Typology)* – Standardises policy topics, e.g. `affordable-housing`. Existing codelist.
* **`vision`** – The plan's vision that policies deliver, which can change over the process of plan-making.

## Mock JSON Payload

```json
{
  "entity": 5023417,
  "prefix": "development-policy",
  "reference": "policy-tot-2026-h3",
  "name": "Affordable housing",
  "policy-number": "H3",
  "description": "Sets the proportion of affordable housing required on residential developments.",
  "policy-text": "Residential developments of 10 or more homes will be required to provide at least 35% affordable housing.",
  "development-plan-document": "doc-lp-2026-local-plan-01",
  "chapter": "chapter-tot-2026-housing",
  "development-policy-type": "strategic",
  "development-policy-categories": [
    "affordable-housing"
  ],
  "vision": "vision-tot-2026",
  "notes": "",
  "organisation": "local-authority-eng:TOT",
  "entry-date": "2026-10-12T14:00:00Z",
  "start-date": "2026-10-12T00:00:00Z",
  "end-date": ""
}

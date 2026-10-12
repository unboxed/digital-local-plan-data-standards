---
title: Proposed Dataset for Local Plan Policy
status: Alpha Co-design Draft
target-dataset: local-plan-policy
typology: policy
---

This is a proposed dataset, intended to replace the draft [development-policy](https://digital-land.github.io/specification/dataset/development-policy/) dataset in the planning.data repository. It adapts `development-policy` for local plans and applies to:
- Each policy in a local plan.
- Use this with local-plan-policy-category to find policies on a topic. For example, all affordable housing policies.

## Schema Diff
This diff displays how the proposed `local-plan-policy` fields differ from the draft `development-policy` dataset.

```diff
- dataset: development-policy
+ dataset: local-plan-policy
  fields:
    - reference
    - name
+   - policy-number
    - description
+   - policy-text
-   - development-plan-document
+   - local-plan-document
+   - chapter
+   - local-plan-policy-type
-   - development-policy-categories
+   - local-plan-policy-categories
+   - evidence-documents
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
| `local-plan-document` | string (CURIE) | 1 | | Reference to the `local-plan-document` the policy is in. Replaces `development-plan-document`. |
| `chapter` | string (CURIE) | 1 | | Reference to the proposed `chapter` dataset. |
| `local-plan-policy-type` | string (CURIE) | 1 | | Reference to the proposed `local-plan-policy-type` codelist. |
| `local-plan-policy-categories` | string (List) | n | | References to the `local-plan-policy-category` codelist. Replaces `development-policy-categories`. |
| `evidence-documents` | string (List) | n | | References to `local-plan-document` records with a `document-role` of `evidence` that support this policy. |
| `vision` | string (CURIE) | 1 | | Reference to the proposed `vision` dataset. |

## Related Proposed Datasets

* **`chapter`** – A section of a local plan; belongs to `local-plan`.
* **`local-plan-policy-type`** *(Category Typology)* – Standardises policy types, e.g. `strategic`, `non-strategic`, `site-allocation`.
* **`local-plan-policy-category`** *(Category Typology)* – Standardises policy topics, e.g. `affordable-housing`. Replaces `development-policy-category`.
* **`vision`** – The plan's vision that policies deliver, which can change over the process of plan-making.

## Questions
* This is proposed to replace `development-policy` due to the ambiguity stemming from the top-level `development-plan` which sits alongside `local-plan`. What do you think about this decision?
* Do figures (diagrams, tables, images) in policies need to be published as data, or is a link to the policy's document enough? Should tables of figures be published through `local-plan-policy-metric`?
* Does a policy deliver one part of the plan's vision, or several objectives?

## Mock JSON Payload

```json
{
  "entity": 5023417,
  "prefix": "local-plan-policy",
  "reference": "policy-tot-2026-h3",
  "name": "Affordable housing",
  "policy-number": "H3",
  "description": "Sets the proportion of affordable housing required on residential developments.",
  "policy-text": "Residential developments of 10 or more homes will be required to provide at least 35% affordable housing.",
  "local-plan-document": "doc-lp-2026-local-plan-01",
  "chapter": "chapter-tot-2026-housing",
  "local-plan-policy-type": "strategic",
  "local-plan-policy-categories": [
    "affordable-housing"
  ],
  "evidence-documents": [
    "doc-lp-2026-viability-01",
    "doc-lp-2026-housing-needs-01"
  ],
  "vision": "vision-tot-2026",
  "notes": "",
  "organisation": "local-authority-eng:TOT",
  "entry-date": "2026-10-12T14:00:00Z",
  "start-date": "2026-10-12T00:00:00Z",
  "end-date": ""
}

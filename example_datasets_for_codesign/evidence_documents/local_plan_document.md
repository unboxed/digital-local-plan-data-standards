---
title: Proposed Extensions for Local Plan Document Dataset
status: Alpha Co-design Draft
target-dataset: development-plan-document
typology: document
---

The [local-plan-document](https://digital-land.github.io/specification/dataset/local-plan-document/) dataset applies to:
- The documents that an authority uses to create their local plan.
- Every document within a local plan. Each row contains a link to a published document on the authority's website.
- Use this with local-plan-document-type to find the document that you are interested in.

## Schema Diff
This diff displays how the current MHCLG specification fields must evolve to support the new features identified in our user research.

```diff
  dataset: development-plan-document
  fields:
    - reference
    - name
    - description
    - development-plan
    - document-types
+   - document-role
    - document-url
    - documentation-url
+   - dataset
+   - consultant
+   - development-policies
+   - requirements
+   - commenced-date
+   - finalised-date
+   - superseded
    - notes
    - organisation
    - prefix
    - entity
    - entry-date
    - start-date
    - end-date
```

## Proposed Field Definitions & Validation Rules

| Field Name | Typology / Type | Required | Notes & Codelist Linkages |
| :--- | :--- | :--- | :--- |
| `document-role` | string (CURIE) | | Links to a new proposed `document-role` codelist. Valid entries include: `evidence`, `supporting`. |
| `dataset` | string | | Captures references for evidence held directly in dynamic data dashboards/tables rather than static text files. |
| `consultant` | string (CURIE) | | Reference to an external proposed `consultant` registry tracking commissioned bodies. |
| `development-policies` | string (List) | | An array of references mapping this document directly to the `development-policy` dataset it informs. |
| `requirements` | string (List) | | Multiple references linking the document back to specific legislation, NPPF policy tags, or local statutory benchmarks. |
| `commenced-date` | datetime | | The timestamp indicating when official work or drafting on the document began. |
| `finalised-date` | datetime | | The timestamp tracking when the document was signed off or completed. |

## Related Proposed Datasets & Structural Associations

To support the additional fields above, three supporting infrastructure tables/codelists must be added:
* **`document-role`** *(Category Typology)* – Standardises document type.
* **`requirement`** *(Codelist)* – Standardises links to specific sections of national and local policy acts.
* **`consultant` / `consultant-type`** *(Registry)* – Records consultant participation and standardises types.

### System Associations (Relational Map)
* `belongs_to` ➔ `local-plan`
* `has_one` ➔ `development-plan-document-type`
* `belongs_to` ➔ `document-role`
* `belongs_to` ➔ `consultant`
* `has_many` ➔ `development-policy`
* `has_many` ➔ `requirement`

## Questions
* Do all documents have a stable URL currently? Does this include evidence documents?
* Is it beneficial to distinguish between procured evidence documents and other types?
* Is it important to show how a document replaces the equivalent document from a previous plan? 
* `superseded` here is proposed to store a reference to the previous version of the record, e.g. if a published evidence document is updated at a later stage of the plan. Is this a real use case? If so, is this field ambiguous given the dataset stores plan documents (like the policies map) alongside evidence, i.e. could it appear that it refers to a replacement document from a previous plan as opposed to a newer version of the same document?
* What requirements (legislation, NPPF policies, and other requirements) should evidence be able to demonstrate it addresses? Is type and note sufficient, or would a structured reference back to a specific requirement be beneficial?

## Mock JSON Payload

```json
{
  "entity": 4019283,
  "prefix": "development-plan-document",
  "reference": "doc-lp-2026-flood-01",
  "name": "Strategic Flood Risk Assessment Level 1",
  "description": "Evidence base mapping spatial flood risk zones within the district boundary.",
  "organisation": "local-authority-eng:TOT",
  "development-plan": "local-plan-tottenham-2026",
  "document-types": "flood-risk-assessment",
  "document-role": "evidence",
  "document-url": "https://tottenham.gov.uk",
  "documentation-url": "https://tottenham.gov.uk",
  "dataset": "",
  "consultant": "consultant:env-agency-delivered",
  "development-policies": [
    "policy-cc-01",
    "policy-infra-04"
  ],
  "requirements": [
    "nppf-paragraph-160",
    "flood-water-management-act-2010"
  ],
  "commenced-date": "2025-04-12T09:00:00Z",
  "finalised-date": "2026-02-10T16:30:00Z",
  "entry-date": "2026-10-11T14:00:00Z",
  "start-date": "2026-10-11T00:00:00Z",
  "end-date": "",
  "notes": "Version 1.2 updated following environment agency consultation reviews."
}
```

---
title: Proposed Extensions for Document Dataset
status: Alpha Co-design Draft
target-dataset: document
typology: document
---

This proposes extensions to the [document](https://digital-land.github.io/specification/dataset/document/) dataset in the planning.data repository so it can hold the evidence that supports a development plan. It applies to:
- Evidence documents produced or procured to support policies in a plan. For example, a strategic flood risk assessment or a viability study.
- Use this with document-types to find the kind of evidence you are interested in.
- Use `development-policies` to find the policies a piece of evidence supports.

The documents that make up a development plan, such as a local plan or neighbourhood plan, stay in the [development-plan-document](https://www.planning.data.gov.uk/dataset/development-plan-document) dataset.

## Schema Diff
This diff shows the proposed changes to the current `document` dataset.

```diff
  dataset: document
  fields:
    - reference
    - name
    - description
    - document-types
+   - document-role
    - document-url
+   - dataset
+   - development-policies
+   - consultancy
+   - requirements
+   - commenced-date
+   - finalised-date
+   - superseded
    - notes
    - organisations
    - prefix
    - entity
    - entry-date
    - start-date
    - end-date
```

## Proposed Field Definitions & Validation Rules

| Field Name | Typology / Type | Cardinality | Required | Notes & Codelist Linkages |
| :--- | :--- | :--- | :--- | :--- |
| `document-role` | string (CURIE) | 1 | | Links to a new proposed `document-role` codelist, e.g. `evidence`. Distinguishes evidence from other documents held in this dataset. |
| `dataset` | string | 1 | | Captures references for evidence held directly in dynamic data dashboards/tables rather than static text files. |
| `development-policies` | string (List) | n | | References to the `development-policy` records this document supports. An evidence document can support many policies, so the reference lives here rather than on the policy. |
| `consultancy` | string (CURIE) | 1 | | Reference to a proposed `consultancy` dataset recording the consultancy commissioned to produce the document. |
| `requirements` | string (List) | n | | References linking the document to specific legislation, NPPF policy tags, or local statutory benchmarks. |
| `commenced-date` | datetime | 1 | | When official work or drafting on the document began. |
| `finalised-date` | datetime | 1 | | When the document was signed off or completed. |
| `superseded` | string (CURIE) | 1 | | Reference to the previous version of this record, e.g. where a published evidence document is updated at a later stage of the plan. See Questions. |

## Related Proposed Datasets

* **`document-role`** *(Category Typology)* – Standardises document role.
* **`requirement`** *(Codelist)* – Standardises links to specific sections of national and local policy acts.
* **`consultancy`** *(Registry)* – Records the consultancies commissioned to produce documents.
* **`consultancy-type`** *(Category Typology)* – Standardises the specialisms of consultancies.

## Questions
* Do all evidence documents have a stable URL currently?
* There are procured evidence documents, public evidence sources and what other types? The proposed datasets address procured documents, are datasets needed for the other types?
* `superseded` is proposed to store a reference to the previous version of the record, e.g. if a published evidence document is updated at a later stage of the plan. Is this a real use case?
* Are any additional fields needed to track versions? e.g. why the new version supersedes the old one?
* What requirements (legislation, NPPF policies, and other requirements) should evidence be able to demonstrate it addresses?
* Is `document-role` needed, or is `document-types` enough to identify evidence?

## Mock JSON Payload

```json
{
  "entity": 4019283,
  "prefix": "document",
  "reference": "doc-lp-2026-flood-01",
  "name": "Strategic Flood Risk Assessment Level 1",
  "description": "Evidence base mapping spatial flood risk zones within the district boundary.",
  "document-types": [
    "flood-risk-assessment"
  ],
  "document-role": "evidence",
  "document-url": "https://tottenham.gov.uk",
  "dataset": "",
  "development-policies": [
    "policy-tot-2026-cc1",
    "policy-tot-2026-inf4"
  ],
  "consultancy": "consultancy:example-flood-consultants",
  "requirements": [
    "nppf-paragraph-160",
    "flood-water-management-act-2010"
  ],
  "commenced-date": "2025-04-12T09:00:00Z",
  "finalised-date": "2026-02-10T16:30:00Z",
  "superseded": "",
  "notes": "Version 1.2 updated following environment agency consultation reviews.",
  "organisations": [
    "local-authority-eng:TOT"
  ],
  "entry-date": "2026-10-11T14:00:00Z",
  "start-date": "2026-10-11T00:00:00Z",
  "end-date": ""
}
```

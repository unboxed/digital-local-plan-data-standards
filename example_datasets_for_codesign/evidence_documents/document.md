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
+   - baseline-data
+   - base-date
+   - development-policies
+   - consultancy
+   - requirements
+   - commenced-date
+   - finalised-date
+   - replaces
+   - supplements
+   - replacement-reason
+   - version-label
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
| `baseline-data` | string | 1 | | Captures baseline formula or other information. |
| `base-date` | datetime | 1 | | The date the evidence's data is as at. Often a year or more before `finalised-date`, and usually what matters for currency. |
| `development-policies` | string (List) | n | | References to the `development-policy` records this document was produced to support. An evidence document can support many policies, so the reference lives here rather than on the policy. Distinct from `based-on` on a policy version, which records what that version actually relied on at a given plan stage. |
| `consultancy` | string (CURIE) | 1 | | Reference to a proposed `consultancy` dataset recording the consultancy commissioned to produce the document. |
| `requirements` | string (List) | n | | References linking the document to specific legislation, NPPF policy tags, or local statutory benchmarks. |
| `commenced-date` | datetime | 1 | | When official work or drafting on the document began. |
| `finalised-date` | datetime | 1 | | When the document was signed off or completed. |
| `replaces` | string (CURIE) | 1 | | Reference to the `document` record this one replaces in full, e.g. a 2026 SFRA replacing the 2021 SFRA. Blank for the first edition. |
| `supplements` | string (List) | n | | References to `document` records this one adds to without replacing, e.g. an addendum, or a Level 2 SFRA alongside a Level 1. |
| `replacement-reason` | string (CURIE) | 1 | | Why this edition was produced. Links to a proposed `replacement-reason` codelist. Only used with `replaces`. |
| `version-label` | string | 1 | | The publisher's own label, e.g. "v1.2" or "2026 update". For display only; order comes from the `replaces` chain. |

## Versioning Approach

Each edition of an evidence document is its own `document` record with its own reference, URL and dates. Editions are linked through `replaces` (full replacement) and `supplements` (additions that do not replace).

This differs from policies, where each version is the same policy at a different plan stage and is identified by `reference` + `version`. Policy versions can therefore pin evidence with a plain `document:reference`; only policies need the `@version` form.

An older edition is not invalid once replaced. It may still be the evidence an adopted plan was examined against. Currency is shown by `end-date` and the `replaces` chain, not by marking records as superseded. "Superseded" is reserved for its statutory meaning for development plan policies.

## Related Proposed Datasets

* **`document-role`** *(Category Typology)* – Standardises document role.
* **`requirement`** *(Codelist)* – Standardises links to specific sections of national and local policy acts.
* **`consultancy`** *(Registry)* – Records the consultancies commissioned to produce documents.
* **`consultancy-type`** *(Category Typology)* – Standardises the specialisms of consultancies.
* **`replacement-reason`** *(Codelist)* – Standardises why a new edition was produced, e.g. `scheduled-update`, `examination-request`, `national-change`, `consultation-response`, `correction`, `monitoring-cycle`.

## Questions
* Do all evidence documents have a stable URL currently?
* There are procured evidence documents, public evidence sources and what other types? The proposed datasets address procured documents, are datasets needed for the other types?
* What values should the `replacement-reason` codelist hold?
* Should `development-policies` reference a specific policy version, or the policy as a whole?
* Are `development-policies` (what evidence was produced to support) and `based-on` on policy versions (what a policy relied on) distinct enough to keep both, or should one direction be chosen?
* What requirements (legislation, NPPF policies, and other requirements) should evidence be able to demonstrate it addresses?
* Is `document-role` needed, or is `document-types` enough to identify evidence?

## Mock JSON Payload

To add: baseline_data

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
  "base-date": "2025-03-31T00:00:00Z",
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
  "replaces": "document:doc-lp-2021-flood-01",
  "supplements": [],
  "replacement-reason": "replacement-reason:scheduled-update",
  "version-label": "v1.2",
  "notes": "Updated following Environment Agency consultation reviews.",
  "organisations": [
    "local-authority-eng:TOT"
  ],
  "entry-date": "2026-10-11T14:00:00Z",
  "start-date": "2026-10-11T00:00:00Z",
  "end-date": ""
}
```

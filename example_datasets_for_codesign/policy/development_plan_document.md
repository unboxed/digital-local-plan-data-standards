---
title: Proposed Changes for Development Plan Document Dataset
status: Alpha Co-design Draft
target-dataset: development-plan-document
typology: document
---

The [development-plan-document](https://www.planning.data.gov.uk/dataset/development-plan-document) dataset applies to:
- The documents that make up an authority's development plan. For example, a local plan or a neighbourhood plan.
- Each row contains a link to a published document on the authority's website.
- Use this with development-plan-document-type to find the document that you are interested in.

Evidence documents that support a plan are proposed separately in the [document](document.md) dataset.

## Schema Diff
No field changes are proposed. The current fields are shown for reference.

```diff
  dataset: development-plan-document
  fields:
    - reference
    - name
    - description
    - development-plan
    - document-types
    - document-url
    - documentation-url
    - notes
    - organisation
    - prefix
    - entity
    - entry-date
    - start-date
    - end-date
```

## Questions
* Top level naming question - development plan has development plan documents (of which is a local plan) has development policies (http://digital-land.github.io/images/diagrams/local-plans-schemas.svg)
* Do all plan documents have a stable URL currently?
* Is it important to show how a document replaces the equivalent document from a previous plan? For example, a new local plan replacing the previous one.

## Mock JSON Payload

```json
{
  "entity": 4019001,
  "prefix": "development-plan-document",
  "reference": "doc-lp-2026-local-plan-01",
  "name": "Tottenham Local Plan 2026",
  "description": "The local plan setting out strategic and non-strategic policies for the district.",
  "development-plan": "development-plan-tottenham-2026",
  "document-types": "local-plan",
  "document-url": "https://tottenham.gov.uk",
  "documentation-url": "https://tottenham.gov.uk",
  "notes": "",
  "organisation": "local-authority-eng:TOT",
  "entry-date": "2026-10-11T14:00:00Z",
  "start-date": "2026-10-11T00:00:00Z",
  "end-date": ""
}
```

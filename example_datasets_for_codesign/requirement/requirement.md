---
title: Proposed Dataset for Requirement
status: Alpha Co-design Draft
target-dataset: requirement
typology: category
---

This is a draft proposed dataset that does not currently exist in draft or published form.

This proposed dataset applies to:
- A specific regulatory or non-regulatory requirement that local plans and their evidence must adhere to, e.g. an NPPF paragraph or an act.
- Use this with `document` to find the evidence that addresses a requirement.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | e.g. `nppf-paragraph-160` |
| `name` | string | 1 | yes |  |
| `description` | string | 1 |  |  |
| `requirement-type` | string (CURIE) | 1 | yes | Reference to the `requirement-type` codelist |
| `document-url` | url | 1 |  | Link to the source, e.g. legislation.gov.uk or the NPPF |
| `notes` | text | 1 |  |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  | Set when a requirement is revoked or replaced, e.g. a new NPPF |

Proposed entries (draft definitions for co-design):
- `nppf-paragraph-160`
- `flood-water-management-act-2010`

## Scope for co-design

* What requirements (legislation, NPPF policies, and other requirements) should evidence be able to demonstrate it addresses?
* How granular should requirements be? Is paragraph the right unit?
* NPPF paragraph numbers change between versions. How should requirements track this?

### Referenced by
- `document`, through its `requirements` field.

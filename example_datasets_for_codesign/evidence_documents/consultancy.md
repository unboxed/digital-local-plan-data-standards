---
title: Proposed Dataset for Consultancy
status: Alpha Co-design Draft
target-dataset: consultancy
---

This is a draft proposed dataset that does not currently exist in draft or published form.

This proposed dataset applies to:
- A consultancy commissioned to produce `local-plan-document`s that form the evidence base for a local plan.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | Unique identifier for the consultancy |
| `name` | string | 1 | yes | |
| `company` | string | 1 | | Reference to the `company` dataset |
| `consultancy-type` | string | n | yes | Reference to the `consultancy-type` codelist. A consultancy may cover several specialisms. |
| `prefix` | string | 1 | yes | |
| `entity` | integer | 1 | yes | |
| `entry-date` | datetime | 1 | yes | |
| `start-date` | datetime | 1 | | |
| `end-date` | datetime | 1 | | |

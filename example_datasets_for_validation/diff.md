---
title: Suggested changes to planning.data datasets
status: Alpha Co-design Draft
---

This page shows the suggested changes from `policy_data_model.md` and `evidence_data_model.md` as diffs against the current [planning.data specification](https://github.com/digital-land/specification). Fields are listed alphabetically, as in the specification.

Lines marked `+` are added and lines marked `-` are removed. New datasets are shown in full.

## Summary

| Dataset | Change |
| :--- | :--- |
| `development-policy` | Fields added; `reference` changes meaning |
| `development-policy-section` | New |
| `development-policy-area` | Fields added |
| `development-policy-metric` | No change |
| `development-metric` | Field added |
| `chapter` | New |
| `vision` | New |
| `development-plan-document` | No change |
| `development-plan-document-type` | Entries added and moved out |
| `development-policy-type` | New codelist |
| `development-policy-area-type` | New codelist |
| `evidence-document` | New, based on `document` |
| `evidence-document-area` | New |
| `evidence-document-type` | New codelist, entries moved in |
| `evidence-document-role` | New codelist |
| `replacement-reason` | New codelist |
| `requirement` | New codelist |
| `development-policy-version` | Optional, new |

## Policy

### `development-policy`

`reference` is now a unique identifier for the policy. The number used in the plan, e.g. `H3`, moves to `policy-number`.

```diff
  dataset: development-policy
  fields:
+   - chapter
    - description
    - development-plan-document
    - development-policy-categories
+   - development-policy-type
    - end-date
    - entity
    - entry-date
    - name
    - notes
    - organisation
+   - plan-event
+   - policy-number
    - prefix
    - reference
    - start-date
```

### `development-policy-section`

```diff
+ dataset: development-policy-section
+ fields:
+   - development-policy
+   - end-date
+   - entity
+   - entry-date
+   - label
+   - notes
+   - order
+   - organisation
+   - prefix
+   - reference
+   - section-type
+   - start-date
+   - text
```

### `development-policy-area`

```diff
  dataset: development-policy-area
  fields:
+   - development-plan-document
    - development-policies
+   - development-policy-area-type
    - document-url
    - documentation-url
    - end-date
    - entity
    - entry-date
    - geometry
    - name
    - notes
    - organisation
+   - plan-event
    - point
    - prefix
    - reference
    - start-date
```

### `development-metric`

```diff
  dataset: development-metric
  fields:
+   - description
    - end-date
    - entity
    - entry-date
    - name
    - notes
    - prefix
    - reference
    - start-date
```

### `chapter`

```diff
+ dataset: chapter
+ fields:
+   - chapter-number
+   - development-plan-document
+   - end-date
+   - entity
+   - entry-date
+   - name
+   - notes
+   - order
+   - organisation
+   - prefix
+   - reference
+   - start-date
```

### `vision`

```diff
+ dataset: vision
+ fields:
+   - development-plan-document
+   - end-date
+   - entity
+   - entry-date
+   - name
+   - notes
+   - organisation
+   - prefix
+   - reference
+   - start-date
+   - text
```

### `development-plan-document-type`

No field changes. Entries:

```diff
  entries:
-   - strategic-flood-risk-assessment
-   - strategic-housing-market-assessment
-   - viability-assessment
-   - sustainability-appraisal
-   - financial-viability-study
-   - sustainability-apprasial
+   - neighbourhood-plan
```

The removed entries move to `evidence-document-type`.

### `development-policy-type`

```diff
+ dataset: development-policy-type
+ fields:
+   - description
+   - end-date
+   - entity
+   - entry-date
+   - name
+   - notes
+   - prefix
+   - reference
+   - start-date
```

Entries: `strategic`, `non-strategic`.

### `development-policy-area-type`

```diff
+ dataset: development-policy-area-type
+ fields:
+   - description
+   - end-date
+   - entity
+   - entry-date
+   - name
+   - notes
+   - prefix
+   - reference
+   - start-date
```

Entries to be confirmed in co-design.

## Evidence

### `evidence-document`

Based on the existing `document` dataset, shown as a diff against it.

```diff
  dataset: evidence-document
  fields:
+   - baseline-data
+   - commenced-date
    - description
+   - development-policies
    - document-url
    - end-date
    - entity
    - entry-date
+   - evidence-document-role
-   - document-types
+   - evidence-document-types
+   - finalised-date
    - name
    - notes
    - organisations
    - prefix
    - reference
+   - replacement-reason
+   - replaces
+   - requirements
    - start-date
+   - supplements
+   - version-label
```

### `evidence-document-area`

```diff
+ dataset: evidence-document-area
+ fields:
+   - end-date
+   - entity
+   - entry-date
+   - evidence-document
+   - geometry
+   - name
+   - notes
+   - organisation
+   - point
+   - prefix
+   - reference
+   - start-date
```

### `evidence-document-type`

```diff
+ dataset: evidence-document-type
+ fields:
+   - description
+   - end-date
+   - entity
+   - entry-date
+   - name
+   - notes
+   - prefix
+   - reference
+   - start-date
```

Entries, moved from `development-plan-document-type`:

```diff
  entries:
+   - strategic-flood-risk-assessment
+   - strategic-housing-market-assessment
+   - viability-assessment
+   - sustainability-appraisal
+   - financial-viability-study
+   - sustainability-apprasial
```

`financial-viability-study` and `sustainability-apprasial` keep their `end-date`.

### `evidence-document-role`

```diff
+ dataset: evidence-document-role
+ fields:
+   - description
+   - end-date
+   - entity
+   - entry-date
+   - name
+   - notes
+   - prefix
+   - reference
+   - start-date
```

Entries: `evidence`, `supporting`.

### `replacement-reason`

```diff
+ dataset: replacement-reason
+ fields:
+   - description
+   - end-date
+   - entity
+   - entry-date
+   - name
+   - notes
+   - prefix
+   - reference
+   - start-date
```

Entries: `scheduled-update`, `examination-request`, `national-change`, `consultation-response`, `correction`, `monitoring-cycle`.

### `requirement`

```diff
+ dataset: requirement
+ fields:
+   - description
+   - end-date
+   - entity
+   - entry-date
+   - name
+   - notes
+   - prefix
+   - reference
+   - start-date
```

Entries to be confirmed in co-design, e.g. `nppf-paragraph-160`, `flood-water-management-act-2010`.

## Option: policy versions

Only if `development-policy-version` is adopted (see `development_policy_version.md`).

### `development-policy-version`

```diff
+ dataset: development-policy-version
+ fields:
+   - development-policy
+   - end-date
+   - entity
+   - entry-date
+   - evidence-documents
+   - notes
+   - organisation
+   - plan-event
+   - prefix
+   - reference
+   - start-date
+   - version
```

### Knock-on changes

`plan-event` moves from `development-policy` to the version, and sections link to a version rather than the policy:

```diff
  dataset: development-policy
  fields:
    - chapter
    - description
    - development-plan-document
    - development-policy-categories
    - development-policy-type
    - end-date
    - entity
    - entry-date
    - name
    - notes
    - organisation
-   - plan-event
    - policy-number
    - prefix
    - reference
    - start-date
```

```diff
  dataset: development-policy-section
  fields:
-   - development-policy
+   - development-policy-version
    - end-date
    - entity
    - entry-date
    - label
    - notes
    - order
    - organisation
    - prefix
    - reference
+   - section-key
    - section-type
    - start-date
    - text
```

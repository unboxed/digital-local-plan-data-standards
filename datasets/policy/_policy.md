This is a draft dataset in [the planning.data repository](https://digital-land.github.io/specification/dataset/development-policy/).

### Existing dataset

Typology: policy

This dataset applies to:
- Each policy in a development plan, such as a local plan.
- Use this with development-policy-category to find policies on a topic. For example, all affordable housing policies.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | e.g. the policy number, `H3` |
| `name` | string | 1 | yes | e.g. "Affordable housing" |
| `description` | string | 1 |  |  |
| `development-plan-document` | string | 1 |  | Reference to the `development-plan-document` the policy is in |
| `development-policy-categories` | string | n |  | References to the `development-policy-category` codelist |
| `notes` | text | 1 |  |  |
| `organisation` | curie | 1 | yes | LPA |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

## Scope for co-design

* Do figures (diagrams, tables, images) in policies need to be published as data, or is a link to the policy's document enough? Should tables of figures be published through `development-policy-metric`?
* Does a policy deliver one part of the plan's vision, or several objectives?

## Amended dataset for further iteration

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | Unique identifier for the policy |
| `name` | string | 1 | yes | e.g. "Affordable housing" |
| `policy-number` | string | 1 |  | The number used in the plan, e.g. `H3` |
| `description` | string | 1 |  |  |
| `policy-text` | text | 1 |  | The wording of the policy |
| `development-plan-document` | string | 1 |  | Reference to the `development-plan-document` the policy is in |
| `chapter` | string | 1 |  | Reference to the proposed `chapter` dataset |
| `development-policy-type` | string | 1 |  | Reference to the proposed `development-policy-type` codelist |
| `development-policy-categories` | string | n |  | References to the `development-policy-category` codelist |
| `evidence-documents` | string | n |  | References to `development-plan-document` records with `document-role` of `evidence` that support this policy |
| `vision` | string | 1 |  | Reference to the proposed `vision` dataset |
| `notes` | text | 1 |  |  |
| `organisation` | curie | 1 | yes | LPA |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

### Related proposed datasets

- `chapter`: a section of a development plan; belongs to `development-plan`
- `development-policy-type` (category typology): e.g. `strategic`, `non-strategic`, `site-allocation`
- `vision`: the plan's vision that policies deliver which can change over the process of plan-making

### References
- `development-plan-document`, through its `development-plan-document` and `evidence-documents` fields
- `development-policy-category`, through its `development-policy-categories` field
- `organisation`

### Referenced by
- `development-policy-area`, which links areas of land to the policies that apply to them
- `development-policy-metric`, which holds measurable figures for a policy, such as targets or standards

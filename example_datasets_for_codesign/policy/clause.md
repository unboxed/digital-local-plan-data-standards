Possible that a section will belong to a policy, storing the numbered or lettered criteria within a policy. To be tested.

TODO: If this model is favoured, align the `development_policy.md` to it.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | Stable identifier for the clause. Stays the same across versions, even if the clause is relabelled |
| `development-policy` | string | 1 | yes | Reference of the policy this clause belongs to. Flat schema only; implied by nesting in JSON |
| `development-policy-version` | integer | 1 | yes | Version of the policy this clause belongs to. Flat schema only; implied by nesting in JSON |
| `clause-type` | string | 1 | yes | One of `policy-clause` (binding wording) or `supporting-text` (reasoned justification) |
| `label` | string | 1 |  | Display label as shown in the plan, e.g. "a", "b", "3.2". Can change between versions |
| `order` | integer | 1 | yes | Position of the clause within the policy |
| `text` | text | 1 | yes | The wording of the clause |
| `notes` | text | 1 |  |  |
| `entry-date` | datetime | 1 | yes |  |

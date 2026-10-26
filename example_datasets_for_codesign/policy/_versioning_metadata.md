Possible versioning metadata to be added to a policy:

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `version` | integer | 1 | yes | Version number, starting at 1. `reference` + `version` is unique |
| `previous-version` | integer | 1 |  | The version this one was based on. Blank for version 1 |
| `plan-stage` | string | 1 | yes | Plan-making stage this version relates to, from the plan event codelist, e.g. `reg-19-publication` |
| `version-status` | string | 1 | yes | One of `draft`, `published`, `superseded` |
| `based-on` | string (List) | n |  | Pinned references to the related records this version relied on, written as `dataset:reference@version` |
| `content-hash` | string | 1 |  | SHA-256 fingerprint of this version's content, including its clauses |
| `entry-date` | datetime | 1 | yes | When this version was entered as a record |
| `start-date` | datetime | 1 |  | When this version takes effect |
| `end-date` | datetime | 1 |  | When this version was superseded. Blank for the current version |
| `development-policy-version` | integer | 1 | yes | On `development-policy-clause` (flat schema only). Ties each clause row to its policy version |
| `label` | string | 1 |  | On `development-policy-clause`. Display label, which can change between versions while the clause `reference` stays fixed |

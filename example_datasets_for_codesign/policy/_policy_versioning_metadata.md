Possible versioning metadata to be added to a policy:
## Possible versioning metadata to be added to a policy

| Field | Type | Cardinality | Required | Notes |
|---|---|---|---|---|
| version | integer | 1 | yes | Starts at 1, increments at each formal stage. reference + version is unique |
| plan-stage | string | 1 | yes | Formal stage this version represents, from the plan event codelist, e.g. reg-19-publication |
| label | string | 1 | yes | Display label, e.g. "H3". Can change between versions while reference stays fixed |
| version-status | string | 1 | | Exceptions only: withdrawn, not-carried-forward. Blank otherwise |
| based-on | string (list) | n | | Pinned references to records this version relied on, written as dataset:reference@version |
| content-hash | string | 1 | | SHA-256 of the canonicalised content, including clauses. Shows where text is unchanged between stages |
| entry-date | datetime | 1 | yes | When this version was entered as a record |
| start-date | datetime | 1 | yes | Date of the stage event (publication, or adoption). For the adoption version, this is entry into force |
| end-date | datetime | 1 | | Date of the next stage event, or for the adopted version, when it ceased to be in force. Blank if current |
| development-policy-version | integer | 1 | yes | On development-policy-clause (flat schema only). Ties each clause row to its policy version |
| label | string | 1 | | On development-policy-clause. Display label, can change while the clause reference stays fixed |

### Notes

- No need for a `previous-version` field: stages are sequential, so `version` alone gives the order.
- `end-reason`, `ended-by` and `end-extent` sit on the policy, not the version, and apply only once the adopted version ends.
- `plan-stage` reuses the existing plan event codelist, restricted to events that produce a version of the plan text. It should cover main modifications stage too.

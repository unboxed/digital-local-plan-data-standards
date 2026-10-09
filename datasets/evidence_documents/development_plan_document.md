This is a published dataset in [the planning.data repository](https://www.planning.data.gov.uk/dataset/development-plan-document).

### Existing dataset

Typology: document

This dataset applies to:
- The documents that an authority uses to create their development plan, such as a local plan.
- Every document within a development plan. Each row contains a link to a published document on the authority's website.
- Use this with development-plan-document-type to find the document that you are interested in. For example, a flood assessment.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `description` | string | 1 |  |  |
| `development-plan` | string | 1 |  | Reference to the `development-plan` dataset |
| `document-types` | string | n |  | References to document types |
| `document-url` | url | 1 |  |  |
| `documentation-url` | url | 1 |  |  |
| `name` | string | 1 |  |  |
| `notes` | text | 1 |  |  |
| `entry-date` | datetime | 1 |  |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |
| `prefix` | string | 1 |  |  |
| `reference` | string | 1 |  |  |
| `organisation` | curie | 1 |  | LPA |
| `entity` | integer | 1 |  |  |


## Scope for co-design

* Is this dataset adequate to store references to all types of documents that make up the evidence base?
* Is it realistic that each document will have a stable URL on your authority's website to store against its record?
* Is it beneficial to distinguish between commissioned evidence documents and other types?
* What additional fields or related datasets might be needed to adequately track evidence creation?
* What requirements (legislation, NPPF policies, and other requirements) should evidence be able to demonstrate it addresses? Is type and note sufficient, or would a structured reference back to a specific requirement be beneficial?

## User needs

### Tracking evidence creation
As a policy officer...
* I need to track the back and forth of evidence creation with a view to explaining the steps that I took and why
* I need to track the back and forth of evidence creation, including dates, with a view to generating efficiency data over time
* I need to audit change requests and reasons
* I need to track versions of evidence documents

As an inspector...
* I need to see the evidence that informs a policy
* I need to understand how evidence was created
* I need to understand why evidence was updated
* I need to see comments that help me put the story together without needing to ask for clarification
* I need to see how evidence links back to requirements

### Managing the evidence base and supporting documents
As a policy officer...
* I need to explicitly label a document as part of my evidence base
* I need to explicitly label a document as a support document
* I need to store evidence that has its source in dashboards or datasets, e.g. updated statistical data

### Drafting
As a policy officer...
* I need to draw on relevant pieces of evidence and link it to the policy I am drafting
* I need to view consultation responses alongside my evidence base

### Examination
As a policy officer...
* I need to comply with the regulations under which I will be examined
* I need to store a piece of evidence with a relationship to the requirement(s) it addresses
* I need to search my evidence base with a keyword during an examination hearing to find a relevant document for sharing with my Director
* I need to search my evidence base with a keyword during an examination hearing to a find relevant fact or figure for sharing with my Director (intradocument search)
* I need to easily view the evidence that supports a specific policy

## Amended dataset for further iteration

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | Unique identifier for the document |
| `name` | string | 1 | yes |  |
| `description` | string | 1 |  |  |
| `development-plan` | string | 1 | yes | Reference to the `development-plan` dataset |
| `document-types` | string | n | yes | References to the `development-plan-document-type` codelist |
| `document-role` | string | 1 |  | Reference to the proposed `document-role` codelist, e.g. `evidence`, `supporting` |
| `document-url` | url | 1 | yes | Stable URL on the authority's website |
| `documentation-url` | url | 1 |  |  |
| `dataset` | string | 1 |  | For evidence held in a dataset rather than a document |
| `consultant` | string | 1 |  | Reference to the proposed `consultant` dataset. |
| `development-policies` | string | n |  | References to the `development-policy` dataset: the policies this evidence supports |
| `requirements` | string | n |  | References to the proposed `requirement` codelist |
| `commenced-date` | datetime | 1 |  | When work on the document began |
| `finalised-date` | datetime | 1 |  | When the document was finalised |
| `notes` | text | 1 |  |  |
| `organisation` | curie | 1 | yes | LPA |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes |  |
| `entry-date` | datetime | 1 | yes | A new version of a document is a new entry with a new `entry-date` |
| `start-date` | datetime | 1 |  | When this record became valid (not when work started) |
| `end-date` | datetime | 1 |  | When this record stopped being valid |

### Related proposed datasets

- `document-role` (category typology): `evidence`, `supporting`
- `requirement`: the legislation, NPPF paragraphs and other requirements evidence can address
- `consultant` and `consultant-type`: see the Consultation folder

### Database associations
- `belongs_to` `LocalPlan`
- `has_one` `DevelopmentPlanDocumentType`
- `belongs_to` `DocumentRole`
- `belongs_to` `Consultant`
- `has_many` `DevelopmentPolicy` (through a join table)
- `has_many` `Requirement` (through a join table)

## Example JSON

```
{

}
```

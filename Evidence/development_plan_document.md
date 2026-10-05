
This is an existing dataset in the [official datasets list for local plans](https://www.planning.data.gov.uk/dataset/development-plan-document).

### Existing dataset

This dataset applies to:
- The documents that an authority uses to create their overall plan. For example, the neighbourhood plan.
- Every document within a plan. Each row contains a link to a published document on the authority's website.
- Use this with development-plan-document-type to find the plan document that you are interested in. For example, a transport assessment.

| Field | Type | Required | Notes |
| ----- | ----- | ----- | ----- |
| `description` | string |  |  |
| `development-plan` | string |  |  |
| `document-types` | string |  |  |
| `document-url` | url |  |  |
| `documentation-url` | url |  |  |
| `name` | string |  |  |
| `notes` | text |  |  |
| `entry-date` | datetime |  |  |
| `start-date` | datetime |  |  |
| `end-date` | datetime |  |  |
| `prefix` | string |  | |
| `reference` | string |  |  |
| `organisation` | curie |  | belongs_to |
| `entity` | integer |  |  |


## Scope for co-design

* Currently a local plan is one instance of a development plan, an inspector's report be another. Is this what you would expect to be included in a development-plan-document dataset? 
* Is this dataset adequate to store references to all types of documents that make up the evidence base?
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

| Field | Type | Required | Notes |
| ----- | ----- | ----- | ----- |
| `name` | string |  |  |
| `description` | string |  |  |
| `development-plan` | string |  |  |
| `document-types` | string |  |  |
| `document-url` | url |  |  |
| `documentation-url` | url |  |  |
| `notes` | text |  |  |
| `dataset` | reference |  |  |
| `consultant-id` | reference |  |  |
| `commenced-date` | datetime |  |  |
| `finalised-date` | datetime |  |  |
| `document-id` | string |  |  |
| `chapter` | reference |  |  |
| `evidence` | bool |  | `true`/`false` |
| `requirement` | reference |   | regulation type  |
| `requirement-reference` | string |   | free text reference |
| `entry-date` | datetime |  |  |
| `start-date` | datetime |  |  |
| `end-date` | datetime |  |  |

### Associations
- `belongs_to` `Organisation`
- `belongs_to` `DevelopmentPlan`
- `has_one` `DevelopmentPlanDocumentType`
- Audited by the [Audited gem](https://github.com/collectiveidea/audited) tracking changes with associated `User` in a separate, referenceable model

## Example JSON

```
{

}
```

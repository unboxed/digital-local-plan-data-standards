
This is an existing model in the [official datasets list for local plans](https://www.planning.data.gov.uk/dataset/development-plan-document).

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
| `entity` | integer |  |  |
| `name` | string |  |  |
| `notes` | text |  |  |
| `organisation` | curie |  | belongs_to |
| `prefix` | string |  | for compact URI in MHCLG spec |
| `reference` | string |  |  |
| `entry-date` | datetime |  |  |
| `start-date` | datetime |  |  |
| `end-date` | datetime |  |  |

## Scope for co-design

* Is this dataset adequate to store references to all types of documents that make up the evidence base?
* What additional fields or related datasets might be needed to adequately track evidence creation?

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

## Proposed model


## Example JSON

```
{

}
```

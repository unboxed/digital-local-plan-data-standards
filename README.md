# Digital Local Plan Data Standards (Exploratory)

This is a public repository for co-designing Digital Local Plan data standards.

It applies user insights from the Digital Local Plans Discovery and Alpha project to work already underway and coordinated by MHCLG data teams.

The intent is to:

* provide concrete examples for co-design sessions,
* apply insights,
* surface gaps and ambiguities,
* prompt discussion.

## Ethos

* We should validate the benefits of proposed additions to the schema and proposed data standards 

## Conventions in use in this repository

* If a file name begins with `_` it is a placeholder and may be empty at present.
* "Datasets" refers to categories of data collected and made open source by MHCLG. Additional data will be required to accompany these datasets in a local plan-making service, but would not result in open source datasets and are therefore not included in this repository. For example, a policy officer's choice of "tag" to apply to a consultation response serves only an internal use and would not be collected in a national repository.

## Key references

* [Official datasets list for local plans](https://www.planning.data.gov.uk/local-plans/ 
): MHCLG has begun to publish a tabular data schema for planning datasets. These are the published specifications to which Local Planning Authorities must already adhere and they will be added to over time. There are also some other datasets in this list relating to other types of plan such as mineral plans, waste plans, and supplementary plans, which are out of scope for this stage of the project.

* [MHCLG Github repository](https://github.com/digital-land/specification): Specifications and other data used as a source of truth to model the data for https://planning.data.gov.uk. Every field and table schema for https://planning.data.gov.uk must be defined here but statuses vary from draft to archived. A deployed version can be browsed [here](https://digital-land.github.io/specification/dataset/).

## Tabular conventions used by MHCLG

### Relationships and types

Each dataset is a single flat table:

* **Types are codelists**: these are small datasets (`category` typology) holding a `reference` and a `name`, e.g. `local-plan-document-type`.
* **The record holds the reference**: the record that belongs to something holds a field named after it, e.g. `local-plan` on `local-plan-document`.
* **Prefix, reference and entity**: the `prefix` is the dataset (`local-authority`), the `reference` is the identifier within it (`LND`), and together they make the CURIE `local-authority:LND`. The `entity` is a number planning.data gives the same thing across the whole platform: City of London Corporation is [entity 203](https://www.planning.data.gov.uk/entity/203).
* **CURIEs are short identifiers**: a CURIE combines a dataset name and a reference, e.g. [`local-authority:LND`](https://www.planning.data.gov.uk/curie/local-authority:LND) is the City of London Corporation. When a CURIE appears in a field, such as `organisation`, it links the record to that thing.

### Versioning

| Field | Records |
| :--- | :--- |
| `entry-date` | When the data was created or changed |
| `start-date` | When the thing came into force |
| `end-date` | When the thing stopped being in force |

Drafts, edit history and user records stay in the system that produces the data.

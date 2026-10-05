# Digital Local Plan Data Standards (Exploratory)

This is a public repository for co-designing Digital Local Plan data standards.

It applies user insights from the Digital Local Plans Discovery and Alpha project to work already underway and coordinated by MHCLG data teams.

The intent is to:

* provide concrete examples for co-design sessions,
* apply insights,
* surface gaps and ambiguities,
* prompt discussion.

## Ethos

* We should demonstrate the *benefits* of proposed data standards 
* Additional fields and datasets should be proposed only where a well-defined benefit can be realised

## Conventions in use in this repository

* If a file name begins with `_` it is a placeholder and may be empty at present.
* Files in a given folder are likely to have relationships which may or may not already be defined.
* We have left out reference to the tabular conventions used by MHCLG (see section on tabular conventions below) where new datasets are being tested/proposed given they are not currently part of the ecosystem.

## Key references

* [Official datasets list for local plans](https://www.planning.data.gov.uk/local-plans/ 
): MHCLG has begun to publish tabular data standards for planning datasets. These are the published standards to which Local Planning Authorities must already adhere and they will be added to over time. There are also some other datasets in this list relating to other types of plan such as mineral plans, waste plans, and supplementary plans, which are out of scope for this stage of the project.

* [MHCLG Github repository](https://github.com/digital-land/specification): Specifications and other data used as a source of truth to model the data for https://planning.data.gov.uk. Every field and table schema for https://planning.data.gov.uk must be defined here but statuses vary from draft to archived. A deployed version can be browsed [here](https://digital-land.github.io/specification/dataset/).

## Tabular conventions used by MHCLG

| Field / Concept | Type / Role | What it Represents | Practical Example |
| :--- | :--- | :--- | :--- |
| **`prefix`** | `string` | The namespace or category of the entity (e.g., dataset type). | `"development-plan-document"` |
| **`reference`** | `string` | The local ID used by the publisher or local authority. | `"DOC-2024-A"` |
| **`curie`** | *datatype* | A Compact URI combining `prefix` and `reference` (`prefix:reference`), which also functions as a foreign-key-style reference when used across datasets (e.g., `organisation`). | `"development-plan-document:DOC-2024-A"` |
| **`entity`** | `integer` | A platform-wide unique integer mapped directly to the CURIE. | `4100123` |

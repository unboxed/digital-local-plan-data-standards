# Digital Local Plan Data Standards (Exploratory)

This is an experimental, public repository for co-designing data standards for the local plan-making ecosystem. Nothing here is a finished or agreed standard.

It is informed by prototypes and user research from the Digital Local Plans Discovery and Alpha, carried out with the City of London, and builds on work already underway and coordinated by MHCLG data teams.

## Approach

The examples follow the [planning.data specification](https://github.com/digital-land/specification) conventions, so they can be compared directly with existing MHCLG datasets.

An ecosystem standard for exchanging data between plan-making tools would likely take a different form: a JSON Schema with an agreed exchange format. This will be developed in a later stage of the project.

An exchange standard would not necessarily cover the same data as the national datasets. Some data, such as the structure of consultation responses, is worth standardising so that plan-making tools can share it, but may not need to be collected nationally.

The models support publishing data at any plan-making stage. When data is collected is a decision for MHCLG.

## Key suggestions so far

* Hold policy wording as sections, distinguishing binding wording from explanatory text.
* Separate a policy's number in the plan, e.g. `H3`, from its unique reference.
* Link policies to a chapter and type, and record the vision at plan level.
* Record the plan-making stage on a policy with `plan-event`, using planning.data's fact history to track changes. A separate versions dataset is set out as an option.
* Extend policy areas with the plan they belong to and the stage.
* Hold evidence in its own `evidence-document` dataset, linked to the policies it supports, with editions linked through `replaces` and `supplements`.
* Link evidence to the legislation and national policy it addresses.

## Contents

* `policy_data_model.md` – policies and related datasets
* `evidence_data_model.md` – evidence documents
* `development_policy_version.md` – option for policy versions
* `proposed_changes_diff.md` – all changes as diffs against the planning.data specification

## Purpose

* provide concrete examples for co-design sessions
* surface gaps and ambiguities
* prompt discussion
* begin drafting schemas for technical co-design

Examination datasets to be added.

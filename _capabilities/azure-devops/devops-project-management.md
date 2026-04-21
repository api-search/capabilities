---
consumed_apis:
- azure-devops-work-items
- azure-devops-pipelines
description: Unified workflow for managing Azure DevOps projects combining work item tracking and CI/CD pipeline operations. Used by development teams, project managers, and DevOps engineers to plan work, track progress, and automate build/release processes.
layout: capability
name: Azure DevOps Project Management
operations:
- description: Get a work item by ID
  method: GET
  name: get-work-item
  path: /v1/work-items/{id}
- description: Update a work item
  method: PATCH
  name: update-work-item
  path: /v1/work-items/{id}
- description: Get multiple work items by IDs
  method: GET
  name: get-work-items-batch
  path: /v1/work-items
- description: Create a new work item
  method: POST
  name: create-work-item
  path: /v1/work-items
- description: Query work items using WIQL
  method: POST
  name: query-work-items
  path: /v1/queries
- description: List work item fields
  method: GET
  name: list-fields
  path: /v1/fields
- description: List all pipelines
  method: GET
  name: list-pipelines
  path: /v1/pipelines
- description: Create a new pipeline
  method: POST
  name: create-pipeline
  path: /v1/pipelines
- description: Get a pipeline by ID
  method: GET
  name: get-pipeline
  path: /v1/pipelines/{pipelineId}
- description: List pipeline runs
  method: GET
  name: list-pipeline-runs
  path: /v1/pipelines/{pipelineId}/runs
- description: Trigger a pipeline run
  method: POST
  name: run-pipeline
  path: /v1/pipelines/{pipelineId}/runs
- description: Get a pipeline run
  method: GET
  name: get-pipeline-run
  path: /v1/pipelines/{pipelineId}/runs/{runId}
personas: []
provider_name: Azure DevOps
provider_slug: azure-devops
search_terms:
- devops
- get work items batch
- pipeline runs
- list all pipelines
- get multiple work items by ids
- get work item
- run pipeline
- query work items
- create pipeline
- individual work item operations
- azure
- list pipeline runs
- project management
- get a pipeline run
- work items
- wiql query execution
- list runs for a pipeline
- list all pipelines in a project
- create work item
- list pipelines
- single pipeline
- azure devops
- work item batch and creation
- update a work item
- create a new work item
- get a pipeline by id
- update work item
- query work items using wiql
- get pipeline
- create a new pipeline
- list all work item field definitions
- trigger a pipeline run
- single pipeline run
- get details of a pipeline run
- pipeline definitions
- list fields
- work item field definitions
- ci/cd
- get pipeline run
- pipelines
- list work item fields
- get a work item by id
slug: devops-project-management
tags:
- Azure DevOps
- Project Management
- CI/CD
- Work Items
- Pipelines
tools:
- description: Get a work item by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-work-item
- description: Create a new work item
  hints:
    readOnly: false
  name: create-work-item
- description: Update a work item
  hints:
    idempotent: true
    readOnly: false
  name: update-work-item
- description: Get multiple work items by IDs
  hints:
    idempotent: true
    readOnly: true
  name: get-work-items-batch
- description: Query work items using WIQL
  hints:
    idempotent: true
    readOnly: true
  name: query-work-items
- description: List all work item field definitions
  hints:
    idempotent: true
    readOnly: true
  name: list-work-item-fields
- description: List all pipelines in a project
  hints:
    idempotent: true
    readOnly: true
  name: list-pipelines
- description: Get a pipeline by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-pipeline
- description: Create a new pipeline
  hints:
    readOnly: false
  name: create-pipeline
- description: Trigger a pipeline run
  hints:
    readOnly: false
  name: run-pipeline
- description: List runs for a pipeline
  hints:
    idempotent: true
    readOnly: true
  name: list-pipeline-runs
- description: Get details of a pipeline run
  hints:
    idempotent: true
    readOnly: true
  name: get-pipeline-run
---

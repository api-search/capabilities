---
categories:
- ci-cd
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
- get pipeline run
- project management
- update work item
- create a new work item
- get details of a pipeline run
- create a new pipeline
- pipeline definitions
- run pipeline
- get a pipeline by id
- list all pipelines in a project
- single pipeline
- pipelines
- individual work item operations
- get work item
- work item batch and creation
- create pipeline
- list pipeline runs
- get pipeline
- list pipelines
- list work item fields
- devops
- list all work item field definitions
- work item field definitions
- azure devops
- list runs for a pipeline
- get work items batch
- query work items using wiql
- query work items
- update a work item
- list all pipelines
- pipeline runs
- ci/cd
- wiql query execution
- single pipeline run
- get a pipeline run
- get a work item by id
- work items
- azure
- trigger a pipeline run
- list fields
- create work item
- get multiple work items by ids
slug: devops-project-management
source_filename: devops-project-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure DevOps Project Management\"\n  description: \"Unified workflow for managing Azure DevOps projects combining work item tracking and CI/CD pipeline operations. Used by development teams, project managers, and DevOps engineers to plan work, track progress, and automate build/release processes.\"\n  tags:\n    - Azure DevOps\n    - Project Management\n    - CI/CD\n    - Work Items\n    - Pipelines\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_DEVOPS_PAT: AZURE_DEVOPS_PAT\n\ncapability:\n  consumes:\n    - import: azure-devops-work-items\n      location: ./shared/work-items.yaml\n    - import: azure-devops-pipelines\n      location: ./shared/pipelines.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: devops-project-mgmt-api\n      description: \"Unified REST API for Azure DevOps project management combining work items and pipelines.\"\n     \
  \ resources:\n        - path: /v1/work-items/{id}\n          name: work-item\n          description: \"Individual work item operations\"\n          operations:\n            - method: GET\n              name: get-work-item\n              description: \"Get a work item by ID\"\n              call: \"azure-devops-work-items.get-work-item\"\n              with:\n                project: \"rest.project\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-work-item\n              description: \"Update a work item\"\n              call: \"azure-devops-work-items.update-work-item\"\n              with:\n                project: \"rest.project\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/work-items\n          name: work-items\n          description:\
  \ \"Work item batch and creation\"\n          operations:\n            - method: GET\n              name: get-work-items-batch\n              description: \"Get multiple work items by IDs\"\n              call: \"azure-devops-work-items.get-work-items-batch\"\n              with:\n                project: \"rest.project\"\n                ids: \"rest.ids\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-work-item\n              description: \"Create a new work item\"\n              call: \"azure-devops-work-items.create-work-item\"\n              with:\n                project: \"rest.project\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/queries\n          name: queries\n          description: \"WIQL query execution\"\n          operations:\n            - method: POST\n\
  \              name: query-work-items\n              description: \"Query work items using WIQL\"\n              call: \"azure-devops-work-items.query-work-items-by-wiql\"\n              with:\n                project: \"rest.project\"\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/fields\n          name: fields\n          description: \"Work item field definitions\"\n          operations:\n            - method: GET\n              name: list-fields\n              description: \"List work item fields\"\n              call: \"azure-devops-work-items.list-work-item-fields\"\n              with:\n                project: \"rest.project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pipelines\n          name: pipelines\n          description: \"Pipeline definitions\"\n          operations:\n         \
  \   - method: GET\n              name: list-pipelines\n              description: \"List all pipelines\"\n              call: \"azure-devops-pipelines.list-pipelines\"\n              with:\n                project: \"rest.project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-pipeline\n              description: \"Create a new pipeline\"\n              call: \"azure-devops-pipelines.create-pipeline\"\n              with:\n                project: \"rest.project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pipelines/{pipelineId}\n          name: pipeline\n          description: \"Single pipeline\"\n          operations:\n            - method: GET\n              name: get-pipeline\n              description: \"Get a pipeline by ID\"\n              call: \"azure-devops-pipelines.get-pipeline\"\n     \
  \         with:\n                project: \"rest.project\"\n                pipelineId: \"rest.pipelineId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pipelines/{pipelineId}/runs\n          name: pipeline-runs\n          description: \"Pipeline runs\"\n          operations:\n            - method: GET\n              name: list-pipeline-runs\n              description: \"List pipeline runs\"\n              call: \"azure-devops-pipelines.list-pipeline-runs\"\n              with:\n                project: \"rest.project\"\n                pipelineId: \"rest.pipelineId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: run-pipeline\n              description: \"Trigger a pipeline run\"\n              call: \"azure-devops-pipelines.run-pipeline\"\n              with:\n                project: \"rest.project\"\n   \
  \             pipelineId: \"rest.pipelineId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pipelines/{pipelineId}/runs/{runId}\n          name: pipeline-run\n          description: \"Single pipeline run\"\n          operations:\n            - method: GET\n              name: get-pipeline-run\n              description: \"Get a pipeline run\"\n              call: \"azure-devops-pipelines.get-pipeline-run\"\n              with:\n                project: \"rest.project\"\n                pipelineId: \"rest.pipelineId\"\n                runId: \"rest.runId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: devops-project-mgmt-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure DevOps project management.\"\n      tools:\n        - name: get-work-item\n          description: \"Get\
  \ a work item by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"azure-devops-work-items.get-work-item\"\n          with:\n            project: \"tools.project\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-work-item\n          description: \"Create a new work item\"\n          hints:\n            readOnly: false\n          call: \"azure-devops-work-items.create-work-item\"\n          with:\n            project: \"tools.project\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-work-item\n          description: \"Update a work item\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"azure-devops-work-items.update-work-item\"\n          with:\n            project: \"tools.project\"\n            id:\
  \ \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-work-items-batch\n          description: \"Get multiple work items by IDs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"azure-devops-work-items.get-work-items-batch\"\n          with:\n            project: \"tools.project\"\n            ids: \"tools.ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-work-items\n          description: \"Query work items using WIQL\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"azure-devops-work-items.query-work-items-by-wiql\"\n          with:\n            project: \"tools.project\"\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-work-item-fields\n          description:\
  \ \"List all work item field definitions\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"azure-devops-work-items.list-work-item-fields\"\n          with:\n            project: \"tools.project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-pipelines\n          description: \"List all pipelines in a project\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"azure-devops-pipelines.list-pipelines\"\n          with:\n            project: \"tools.project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pipeline\n          description: \"Get a pipeline by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"azure-devops-pipelines.get-pipeline\"\n          with:\n            project: \"tools.project\"\n            pipelineId:\
  \ \"tools.pipelineId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-pipeline\n          description: \"Create a new pipeline\"\n          hints:\n            readOnly: false\n          call: \"azure-devops-pipelines.create-pipeline\"\n          with:\n            project: \"tools.project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: run-pipeline\n          description: \"Trigger a pipeline run\"\n          hints:\n            readOnly: false\n          call: \"azure-devops-pipelines.run-pipeline\"\n          with:\n            project: \"tools.project\"\n            pipelineId: \"tools.pipelineId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-pipeline-runs\n          description: \"List runs for a pipeline\"\n          hints:\n            readOnly: true\n            idempotent: true\n     \
  \     call: \"azure-devops-pipelines.list-pipeline-runs\"\n          with:\n            project: \"tools.project\"\n            pipelineId: \"tools.pipelineId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pipeline-run\n          description: \"Get details of a pipeline run\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"azure-devops-pipelines.get-pipeline-run\"\n          with:\n            project: \"tools.project\"\n            pipelineId: \"tools.pipelineId\"\n            runId: \"tools.runId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-devops/refs/heads/main/capabilities/devops-project-management.yaml
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

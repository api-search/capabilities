---
categories:
- ci-cd
consumed_apis: []
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
- update work item
- run pipeline
- single pipeline run
- list fields
- devops
- pipeline definitions
- trigger a pipeline run
- list all pipelines
- azure
- query work items using wiql
- list pipelines
- pipelines
- create pipeline
- list pipeline runs
- update a work item
- get a work item by id
- project management
- get a pipeline run
- azure devops
- create a new pipeline
- create a new work item
- list all work item field definitions
- list work item fields
- work item field definitions
- ci/cd
- wiql query execution
- individual work item operations
- work items
- create work item
- pipeline runs
- get a pipeline by id
- get details of a pipeline run
- single pipeline
- get multiple work items by ids
- get work items batch
- query work items
- get pipeline
- work item batch and creation
- list all pipelines in a project
- list runs for a pipeline
- get work item
- get pipeline run
slug: devops-project-management
source_filename: devops-project-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure DevOps Project Management\n  description: Unified workflow for managing Azure DevOps projects combining work item tracking and CI/CD pipeline operations.\n    Used by development teams, project managers, and DevOps engineers to plan work, track progress, and automate build/release\n    processes.\n  tags:\n  - Azure DevOps\n  - Project Management\n  - CI/CD\n  - Work Items\n  - Pipelines\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_DEVOPS_PAT: AZURE_DEVOPS_PAT\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-devops-work-items\n    baseUri: https://dev.azure.com/{organization}\n    description: Azure DevOps Work Item Tracking API for managing work items across Azure Boards.\n    authentication:\n      type: basic\n      username: ''\n      password: '{{AZURE_DEVOPS_PAT}}'\n    resources:\n    - name: work-items\n      path: /{project}/_apis/wit\n      description:\
  \ Work item CRUD and query operations.\n      operations:\n      - name: get-work-item\n        method: GET\n        description: Returns a single work item by its numeric ID.\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Work item ID\n        - name: $expand\n          in: query\n          type: string\n          required: false\n          description: Expand related entities (all, fields, relations, links, none)\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: update-work-item\n        method: PATCH\n        description: Updates a work item using JSON Patch operations.\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Work item ID\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        - name: suppressNotifications\n          in: query\n          type: boolean\n          required: false\n          description: Suppress notifications\n        body:\n          type: json\n          data:\n            op: '{{tools.op}}'\n            path: '{{tools.path}}'\n            value: '{{tools.value}}'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-work-item\n        method: POST\n        description: Creates a new work item of the specified type.\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: type\n          in: path\n          type: string\n          required: true\n          description: Work item type (e.g., Bug, Task, User Story)\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        body:\n          type: json\n          data:\n            op: '{{tools.op}}'\n            path: '{{tools.path}}'\n            value: '{{tools.value}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-work-items-batch\n        method: GET\n \
  \       description: Returns multiple work items by a list of IDs.\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of work item IDs (max 200)\n        - name: $expand\n          in: query\n          type: string\n          required: false\n          description: Expand related entities\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: query-work-items-by-wiql\n        method: POST\n        description: Executes a WIQL query to find work items matching criteria.\n        inputParameters:\n        - name: project\n\
  \          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-work-item-fields\n        method: GET\n        description: Returns all work item fields defined in the project.\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: api-version\n          in: query\n          type: string\n          required:\
  \ true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: azure-devops-pipelines\n    baseUri: https://dev.azure.com/{organization}\n    description: Azure DevOps Pipelines API for CI/CD pipeline management.\n    authentication:\n      type: basic\n      username: ''\n      password: '{{AZURE_DEVOPS_PAT}}'\n    resources:\n    - name: pipelines\n      path: /{project}/_apis/pipelines\n      description: Pipeline definition and run management.\n      operations:\n      - name: list-pipelines\n        method: GET\n        description: List all pipelines in the project.\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: $orderBy\n          in: query\n          type: string\n          required: false\n          description:\
  \ Order results\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        - name: continuationToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pipeline\n        method: POST\n        description: Creates a new pipeline from a YAML definition.\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        body:\n\
  \          type: json\n          data:\n            name: '{{tools.name}}'\n            folder: '{{tools.folder}}'\n            configuration: '{{tools.configuration}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pipeline\n        method: GET\n        description: Get a specific pipeline by ID.\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: pipelineId\n          in: path\n          type: integer\n          required: true\n          description: Pipeline ID\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-pipeline-runs\n    \
  \    method: GET\n        description: List runs for a specific pipeline.\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: pipelineId\n          in: path\n          type: integer\n          required: true\n          description: Pipeline ID\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: run-pipeline\n        method: POST\n        description: Triggers a new run of the specified pipeline.\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: pipelineId\n          in: path\n          type: integer\n       \
  \   required: true\n          description: Pipeline ID\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        body:\n          type: json\n          data:\n            resources: '{{tools.resources}}'\n            variables: '{{tools.variables}}'\n            templateParameters: '{{tools.templateParameters}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pipeline-run\n        method: GET\n        description: Get the details of a specific pipeline run.\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project name or ID\n        - name: pipelineId\n          in: path\n          type: integer\n          required: true\n          description: Pipeline ID\n        - name: runId\n          in: path\n         \
  \ type: integer\n          required: true\n          description: Run ID\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: devops-project-mgmt-api\n    description: Unified REST API for Azure DevOps project management combining work items and pipelines.\n    resources:\n    - path: /v1/work-items/{id}\n      name: work-item\n      description: Individual work item operations\n      operations:\n      - method: GET\n        name: get-work-item\n        description: Get a work item by ID\n        call: azure-devops-work-items.get-work-item\n        with:\n          project: rest.project\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name:\
  \ update-work-item\n        description: Update a work item\n        call: azure-devops-work-items.update-work-item\n        with:\n          project: rest.project\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/work-items\n      name: work-items\n      description: Work item batch and creation\n      operations:\n      - method: GET\n        name: get-work-items-batch\n        description: Get multiple work items by IDs\n        call: azure-devops-work-items.get-work-items-batch\n        with:\n          project: rest.project\n          ids: rest.ids\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-work-item\n        description: Create a new work item\n        call: azure-devops-work-items.create-work-item\n        with:\n          project: rest.project\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/queries\n      name: queries\n      description: WIQL query execution\n      operations:\n      - method: POST\n        name: query-work-items\n        description: Query work items using WIQL\n        call: azure-devops-work-items.query-work-items-by-wiql\n        with:\n          project: rest.project\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fields\n      name: fields\n      description: Work item field definitions\n      operations:\n      - method: GET\n        name: list-fields\n        description: List work item fields\n        call: azure-devops-work-items.list-work-item-fields\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipelines\n      name: pipelines\n      description: Pipeline definitions\n      operations:\n      - method: GET\n        name: list-pipelines\n        description: List all\
  \ pipelines\n        call: azure-devops-pipelines.list-pipelines\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-pipeline\n        description: Create a new pipeline\n        call: azure-devops-pipelines.create-pipeline\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipelines/{pipelineId}\n      name: pipeline\n      description: Single pipeline\n      operations:\n      - method: GET\n        name: get-pipeline\n        description: Get a pipeline by ID\n        call: azure-devops-pipelines.get-pipeline\n        with:\n          project: rest.project\n          pipelineId: rest.pipelineId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipelines/{pipelineId}/runs\n      name: pipeline-runs\n      description: Pipeline runs\n      operations:\n\
  \      - method: GET\n        name: list-pipeline-runs\n        description: List pipeline runs\n        call: azure-devops-pipelines.list-pipeline-runs\n        with:\n          project: rest.project\n          pipelineId: rest.pipelineId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: run-pipeline\n        description: Trigger a pipeline run\n        call: azure-devops-pipelines.run-pipeline\n        with:\n          project: rest.project\n          pipelineId: rest.pipelineId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipelines/{pipelineId}/runs/{runId}\n      name: pipeline-run\n      description: Single pipeline run\n      operations:\n      - method: GET\n        name: get-pipeline-run\n        description: Get a pipeline run\n        call: azure-devops-pipelines.get-pipeline-run\n        with:\n          project: rest.project\n          pipelineId: rest.pipelineId\n   \
  \       runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: devops-project-mgmt-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure DevOps project management.\n    tools:\n    - name: get-work-item\n      description: Get a work item by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: azure-devops-work-items.get-work-item\n      with:\n        project: tools.project\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-work-item\n      description: Create a new work item\n      hints:\n        readOnly: false\n      call: azure-devops-work-items.create-work-item\n      with:\n        project: tools.project\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-work-item\n      description: Update a work item\n      hints:\n        readOnly:\
  \ false\n        idempotent: true\n      call: azure-devops-work-items.update-work-item\n      with:\n        project: tools.project\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-work-items-batch\n      description: Get multiple work items by IDs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: azure-devops-work-items.get-work-items-batch\n      with:\n        project: tools.project\n        ids: tools.ids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-work-items\n      description: Query work items using WIQL\n      hints:\n        readOnly: true\n        idempotent: true\n      call: azure-devops-work-items.query-work-items-by-wiql\n      with:\n        project: tools.project\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-work-item-fields\n      description: List all work item field definitions\n\
  \      hints:\n        readOnly: true\n        idempotent: true\n      call: azure-devops-work-items.list-work-item-fields\n      with:\n        project: tools.project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pipelines\n      description: List all pipelines in a project\n      hints:\n        readOnly: true\n        idempotent: true\n      call: azure-devops-pipelines.list-pipelines\n      with:\n        project: tools.project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pipeline\n      description: Get a pipeline by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: azure-devops-pipelines.get-pipeline\n      with:\n        project: tools.project\n        pipelineId: tools.pipelineId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-pipeline\n      description: Create a new pipeline\n      hints:\n        readOnly: false\n      call: azure-devops-pipelines.create-pipeline\n\
  \      with:\n        project: tools.project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-pipeline\n      description: Trigger a pipeline run\n      hints:\n        readOnly: false\n      call: azure-devops-pipelines.run-pipeline\n      with:\n        project: tools.project\n        pipelineId: tools.pipelineId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pipeline-runs\n      description: List runs for a pipeline\n      hints:\n        readOnly: true\n        idempotent: true\n      call: azure-devops-pipelines.list-pipeline-runs\n      with:\n        project: tools.project\n        pipelineId: tools.pipelineId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pipeline-run\n      description: Get details of a pipeline run\n      hints:\n        readOnly: true\n        idempotent: true\n      call: azure-devops-pipelines.get-pipeline-run\n      with:\n        project: tools.project\n\
  \        pipelineId: tools.pipelineId\n        runId: tools.runId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

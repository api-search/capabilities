---
categories: []
consumed_apis:
- squillo-platform
description: Unified workflow capability for managing and monitoring Squillo integration automations. Enables IT operations and integration teams to build, deploy, monitor, and troubleshoot automated workflows connecting enterprise systems without traditional development overhead.
layout: capability
name: Squillo Workflow Automation
operations:
- description: List all workflow definitions
  method: GET
  name: list-workflows
  path: /v1/workflows
- description: Create a new workflow definition
  method: POST
  name: create-workflow
  path: /v1/workflows
- description: Get workflow details
  method: GET
  name: get-workflow
  path: /v1/workflows/{workflowId}
- description: Update a workflow
  method: PUT
  name: update-workflow
  path: /v1/workflows/{workflowId}
- description: Delete a workflow
  method: DELETE
  name: delete-workflow
  path: /v1/workflows/{workflowId}
- description: Activate a workflow to enable its triggers
  method: POST
  name: activate-workflow
  path: /v1/workflows/{workflowId}/activate
- description: Manually execute a workflow with optional input data
  method: POST
  name: execute-workflow
  path: /v1/workflows/{workflowId}/execute
- description: List workflow execution history
  method: GET
  name: list-executions
  path: /v1/executions
- description: Get execution details with step results
  method: GET
  name: get-execution
  path: /v1/executions/{executionId}
- description: List available integration connectors
  method: GET
  name: list-connectors
  path: /v1/connectors
- description: List workflow variables
  method: GET
  name: list-variables
  path: /v1/variables
- description: Create a workflow variable or secret
  method: POST
  name: create-variable
  path: /v1/variables
personas: []
provider_name: Squillo
provider_slug: squillo
search_terms:
- integration platform
- automation
- create a new squillo workflow automation definition
- it process automation
- activate a squillo workflow to enable its triggers
- manually trigger a squillo workflow execution
- create variable
- get execution
- execution details
- workflow definitions
- delete a workflow
- manually execute a workflow with optional input data
- available integration connectors
- manually trigger a workflow
- list variables
- list squillo workflow execution history with filtering by status and date
- get detailed squillo execution results including step outputs and errors
- create workflow
- list available squillo integration connectors by category
- list workflows
- delete workflow
- activate a workflow to enable its triggers
- create a workflow variable or secret
- workflow execution history
- squillo
- execute workflow
- software as a utility
- list all workflow definitions
- activate or deactivate a workflow
- activate workflow
- list available integration connectors
- get details for a specific squillo workflow including steps and triggers
- list all squillo workflow definitions with optional status filter
- list executions
- delete a squillo workflow definition and its execution history
- list workflow execution history
- update a workflow
- update workflow
- get workflow details
- create a new workflow definition
- get execution details with step results
- list connectors
- workflow automation
- no-code
- workflow variables and secrets
- list workflow variables
- list squillo workflow variables and secrets
- workflow
- individual workflow management
- get workflow
slug: workflow-automation
source_filename: workflow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Squillo Workflow Automation\"\n  description: >-\n    Unified workflow capability for managing and monitoring Squillo integration\n    automations. Enables IT operations and integration teams to build, deploy,\n    monitor, and troubleshoot automated workflows connecting enterprise systems\n    without traditional development overhead.\n  tags:\n    - Squillo\n    - Workflow Automation\n    - Integration Platform\n    - No-Code\n    - IT Process Automation\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SQUILLO_API_TOKEN: SQUILLO_API_TOKEN\n\ncapability:\n  consumes:\n    - import: squillo-platform\n      location: ./shared/platform.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: squillo-workflow-automation-api\n      description: \"Unified REST API for Squillo workflow automation management.\"\n      resources:\n        - path: /v1/workflows\n    \
  \      name: workflows\n          description: \"Workflow definitions\"\n          operations:\n            - method: GET\n              name: list-workflows\n              description: \"List all workflow definitions\"\n              call: \"squillo-platform.list-workflows\"\n              with:\n                status: \"rest.status\"\n                page: \"rest.page\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workflow\n              description: \"Create a new workflow definition\"\n              call: \"squillo-platform.create-workflow\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows/{workflowId}\n          name: workflow-detail\n          description: \"Individual workflow management\"\n          operations:\n            - method: GET\n         \
  \     name: get-workflow\n              description: \"Get workflow details\"\n              call: \"squillo-platform.get-workflow\"\n              with:\n                workflowId: \"rest.workflowId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-workflow\n              description: \"Update a workflow\"\n              call: \"squillo-platform.update-workflow\"\n              with:\n                workflowId: \"rest.workflowId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-workflow\n              description: \"Delete a workflow\"\n              call: \"squillo-platform.delete-workflow\"\n              with:\n                workflowId: \"rest.workflowId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        -\
  \ path: /v1/workflows/{workflowId}/activate\n          name: workflow-activate\n          description: \"Activate or deactivate a workflow\"\n          operations:\n            - method: POST\n              name: activate-workflow\n              description: \"Activate a workflow to enable its triggers\"\n              call: \"squillo-platform.activate-workflow\"\n              with:\n                workflowId: \"rest.workflowId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows/{workflowId}/execute\n          name: workflow-execute\n          description: \"Manually trigger a workflow\"\n          operations:\n            - method: POST\n              name: execute-workflow\n              description: \"Manually execute a workflow with optional input data\"\n              call: \"squillo-platform.execute-workflow\"\n              with:\n                workflowId: \"rest.workflowId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/executions\n          name: executions\n          description: \"Workflow execution history\"\n          operations:\n            - method: GET\n              name: list-executions\n              description: \"List workflow execution history\"\n              call: \"squillo-platform.list-executions\"\n              with:\n                workflowId: \"rest.workflowId\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/executions/{executionId}\n          name: execution-detail\n          description: \"Execution details\"\n          operations:\n            - method: GET\n              name: get-execution\n              description: \"Get execution details with step results\"\n              call: \"squillo-platform.get-execution\"\n              with:\n                executionId: \"rest.executionId\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connectors\n          name: connectors\n          description: \"Available integration connectors\"\n          operations:\n            - method: GET\n              name: list-connectors\n              description: \"List available integration connectors\"\n              call: \"squillo-platform.list-connectors\"\n              with:\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/variables\n          name: variables\n          description: \"Workflow variables and secrets\"\n          operations:\n            - method: GET\n              name: list-variables\n              description: \"List workflow variables\"\n              call: \"squillo-platform.list-variables\"\n              outputParameters:\n                - type: object\n              \
  \    mapping: \"$.\"\n            - method: POST\n              name: create-variable\n              description: \"Create a workflow variable or secret\"\n              call: \"squillo-platform.create-variable\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: squillo-workflow-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Squillo workflow automation management.\"\n      tools:\n        - name: list-workflows\n          description: \"List all Squillo workflow definitions with optional status filter\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squillo-platform.list-workflows\"\n          with:\n            status: \"tools.status\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workflow\n        \
  \  description: \"Get details for a specific Squillo workflow including steps and triggers\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squillo-platform.get-workflow\"\n          with:\n            workflowId: \"tools.workflowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workflow\n          description: \"Create a new Squillo workflow automation definition\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"squillo-platform.create-workflow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: activate-workflow\n          description: \"Activate a Squillo workflow to enable its triggers\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"squillo-platform.activate-workflow\"\n          with:\n\
  \            workflowId: \"tools.workflowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-workflow\n          description: \"Manually trigger a Squillo workflow execution\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"squillo-platform.execute-workflow\"\n          with:\n            workflowId: \"tools.workflowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-executions\n          description: \"List Squillo workflow execution history with filtering by status and date\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squillo-platform.list-executions\"\n          with:\n            workflowId: \"tools.workflowId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-execution\n\
  \          description: \"Get detailed Squillo execution results including step outputs and errors\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squillo-platform.get-execution\"\n          with:\n            executionId: \"tools.executionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connectors\n          description: \"List available Squillo integration connectors by category\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squillo-platform.list-connectors\"\n          with:\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-variables\n          description: \"List Squillo workflow variables and secrets\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squillo-platform.list-variables\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-workflow\n          description: \"Delete a Squillo workflow definition and its execution history\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"squillo-platform.delete-workflow\"\n          with:\n            workflowId: \"tools.workflowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/squillo/refs/heads/main/capabilities/workflow-automation.yaml
tags:
- Squillo
- Workflow Automation
- Integration Platform
- No-Code
- IT Process Automation
tools:
- description: List all Squillo workflow definitions with optional status filter
  hints:
    idempotent: true
    readOnly: true
  name: list-workflows
- description: Get details for a specific Squillo workflow including steps and triggers
  hints:
    idempotent: true
    readOnly: true
  name: get-workflow
- description: Create a new Squillo workflow automation definition
  hints:
    idempotent: false
    readOnly: false
  name: create-workflow
- description: Activate a Squillo workflow to enable its triggers
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: activate-workflow
- description: Manually trigger a Squillo workflow execution
  hints:
    idempotent: false
    readOnly: false
  name: execute-workflow
- description: List Squillo workflow execution history with filtering by status and date
  hints:
    idempotent: true
    readOnly: true
  name: list-executions
- description: Get detailed Squillo execution results including step outputs and errors
  hints:
    idempotent: true
    readOnly: true
  name: get-execution
- description: List available Squillo integration connectors by category
  hints:
    idempotent: true
    readOnly: true
  name: list-connectors
- description: List Squillo workflow variables and secrets
  hints:
    idempotent: true
    readOnly: true
  name: list-variables
- description: Delete a Squillo workflow definition and its execution history
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-workflow
---

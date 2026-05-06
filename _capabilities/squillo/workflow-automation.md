---
categories: []
consumed_apis: []
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
- workflow definitions
- get workflow
- no-code
- available integration connectors
- list connectors
- create a new squillo workflow automation definition
- list squillo workflow execution history with filtering by status and date
- activate a squillo workflow to enable its triggers
- activate or deactivate a workflow
- workflow
- get execution details with step results
- list workflow variables
- execute workflow
- software as a utility
- get workflow details
- individual workflow management
- workflow variables and secrets
- execution details
- it process automation
- list all squillo workflow definitions with optional status filter
- squillo
- get detailed squillo execution results including step outputs and errors
- create a new workflow definition
- list variables
- list available squillo integration connectors by category
- list executions
- manually trigger a workflow
- list workflow execution history
- update workflow
- delete a squillo workflow definition and its execution history
- list available integration connectors
- workflow automation
- create variable
- list squillo workflow variables and secrets
- activate workflow
- list workflows
- create workflow
- list all workflow definitions
- get details for a specific squillo workflow including steps and triggers
- create a workflow variable or secret
- update a workflow
- manually trigger a squillo workflow execution
- integration platform
- delete workflow
- get execution
- delete a workflow
- workflow execution history
- activate a workflow to enable its triggers
- manually execute a workflow with optional input data
- automation
slug: workflow-automation
source_filename: workflow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Squillo Workflow Automation\n  description: Unified workflow capability for managing and monitoring Squillo integration automations. Enables IT operations\n    and integration teams to build, deploy, monitor, and troubleshoot automated workflows connecting enterprise systems without\n    traditional development overhead.\n  tags:\n  - Squillo\n  - Workflow Automation\n  - Integration Platform\n  - No-Code\n  - IT Process Automation\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SQUILLO_API_TOKEN: SQUILLO_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: squillo-platform\n    baseUri: https://api.squillo.io/v1\n    description: Squillo Platform API\n    authentication:\n      type: bearer\n      token: '{{SQUILLO_API_TOKEN}}'\n    resources:\n    - name: workflows\n      path: /workflows\n      description: Workflow management\n      operations:\n      - name: list-workflows\n\
  \        method: GET\n        description: List all workflow definitions\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by workflow status\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workflow\n        method: POST\n        description: Create a new workflow definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n\
  \    - name: workflow-by-id\n      path: /workflows/{workflowId}\n      description: Individual workflow management\n      operations:\n      - name: get-workflow\n        method: GET\n        description: Get workflow details\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: Workflow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-workflow\n        method: PUT\n        description: Update a workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-workflow\n        method: DELETE\n        description: Delete a workflow\n        inputParameters:\n        - name: workflowId\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-activate\n      path: /workflows/{workflowId}/activate\n      description: Workflow activation\n      operations:\n      - name: activate-workflow\n        method: POST\n        description: Activate a workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-execute\n      path: /workflows/{workflowId}/execute\n      description: Manual workflow execution\n      operations:\n      - name: execute-workflow\n        method: POST\n        description: Manually trigger a workflow execution\n        inputParameters:\n        - name: workflowId\n         \
  \ in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: executions\n      path: /executions\n      description: Execution history\n      operations:\n      - name: list-executions\n        method: GET\n        description: List workflow executions\n        inputParameters:\n        - name: workflowId\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: execution-by-id\n      path: /executions/{executionId}\n      description: Individual execution details\n      operations:\n      - name: get-execution\n\
  \        method: GET\n        description: Get execution details\n        inputParameters:\n        - name: executionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connectors\n      path: /connectors\n      description: Integration connectors\n      operations:\n      - name: list-connectors\n        method: GET\n        description: List available connectors\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: variables\n      path: /variables\n      description: Workflow variables\n      operations:\n      - name: list-variables\n        method: GET\n        description: List workflow variables\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-variable\n        method: POST\n        description: Create a workflow variable\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: squillo-workflow-automation-api\n    description: Unified REST API for Squillo workflow automation management.\n    resources:\n    - path: /v1/workflows\n      name: workflows\n      description: Workflow definitions\n      operations:\n      - method: GET\n        name: list-workflows\n        description: List all workflow definitions\n        call: squillo-platform.list-workflows\n        with:\n          status: rest.status\n          page: rest.page\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-workflow\n\
  \        description: Create a new workflow definition\n        call: squillo-platform.create-workflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{workflowId}\n      name: workflow-detail\n      description: Individual workflow management\n      operations:\n      - method: GET\n        name: get-workflow\n        description: Get workflow details\n        call: squillo-platform.get-workflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-workflow\n        description: Update a workflow\n        call: squillo-platform.update-workflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-workflow\n        description: Delete a workflow\n        call: squillo-platform.delete-workflow\n      \
  \  with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{workflowId}/activate\n      name: workflow-activate\n      description: Activate or deactivate a workflow\n      operations:\n      - method: POST\n        name: activate-workflow\n        description: Activate a workflow to enable its triggers\n        call: squillo-platform.activate-workflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{workflowId}/execute\n      name: workflow-execute\n      description: Manually trigger a workflow\n      operations:\n      - method: POST\n        name: execute-workflow\n        description: Manually execute a workflow with optional input data\n        call: squillo-platform.execute-workflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/executions\n      name: executions\n      description: Workflow execution history\n      operations:\n      - method: GET\n        name: list-executions\n        description: List workflow execution history\n        call: squillo-platform.list-executions\n        with:\n          workflowId: rest.workflowId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions/{executionId}\n      name: execution-detail\n      description: Execution details\n      operations:\n      - method: GET\n        name: get-execution\n        description: Get execution details with step results\n        call: squillo-platform.get-execution\n        with:\n          executionId: rest.executionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connectors\n      name: connectors\n      description: Available integration connectors\n      operations:\n   \
  \   - method: GET\n        name: list-connectors\n        description: List available integration connectors\n        call: squillo-platform.list-connectors\n        with:\n          category: rest.category\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/variables\n      name: variables\n      description: Workflow variables and secrets\n      operations:\n      - method: GET\n        name: list-variables\n        description: List workflow variables\n        call: squillo-platform.list-variables\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-variable\n        description: Create a workflow variable or secret\n        call: squillo-platform.create-variable\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: squillo-workflow-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted Squillo\
  \ workflow automation management.\n    tools:\n    - name: list-workflows\n      description: List all Squillo workflow definitions with optional status filter\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squillo-platform.list-workflows\n      with:\n        status: tools.status\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workflow\n      description: Get details for a specific Squillo workflow including steps and triggers\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squillo-platform.get-workflow\n      with:\n        workflowId: tools.workflowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workflow\n      description: Create a new Squillo workflow automation definition\n      hints:\n        readOnly: false\n        idempotent: false\n      call: squillo-platform.create-workflow\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: activate-workflow\n      description: Activate a Squillo workflow to enable its triggers\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: squillo-platform.activate-workflow\n      with:\n        workflowId: tools.workflowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-workflow\n      description: Manually trigger a Squillo workflow execution\n      hints:\n        readOnly: false\n        idempotent: false\n      call: squillo-platform.execute-workflow\n      with:\n        workflowId: tools.workflowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-executions\n      description: List Squillo workflow execution history with filtering by status and date\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squillo-platform.list-executions\n      with:\n        workflowId: tools.workflowId\n\
  \        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-execution\n      description: Get detailed Squillo execution results including step outputs and errors\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squillo-platform.get-execution\n      with:\n        executionId: tools.executionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connectors\n      description: List available Squillo integration connectors by category\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squillo-platform.list-connectors\n      with:\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-variables\n      description: List Squillo workflow variables and secrets\n      hints:\n        readOnly: true\n        idempotent: true\n      call: squillo-platform.list-variables\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: delete-workflow\n      description: Delete a Squillo workflow definition and its execution history\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: squillo-platform.delete-workflow\n      with:\n        workflowId: tools.workflowId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

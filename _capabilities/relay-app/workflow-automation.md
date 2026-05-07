---
categories: []
consumed_apis: []
description: Unified workflow automation capability for Relay.app. Combines webhook-triggered workflow execution, workflow management, run status monitoring, human-in-the-loop approval workflows, and run cancellation into a single AI-ready interface. Used by developers, operations teams, and AI agents to trigger and manage automated workflows across 200+ integrated applications.
layout: capability
name: Relay App Workflow Automation
operations:
- description: Trigger a workflow run via webhook.
  method: POST
  name: trigger-workflow
  path: /v1/webhooks/{webhookId}
- description: List all available workflows.
  method: GET
  name: list-workflows
  path: /v1/workflows
- description: Get details of a specific workflow.
  method: GET
  name: get-workflow
  path: /v1/workflows/{workflowId}
- description: List run instances for a workflow.
  method: GET
  name: list-workflow-runs
  path: /v1/workflows/{workflowId}/runs
- description: Get the status and details of a workflow run.
  method: GET
  name: get-run
  path: /v1/runs/{runId}
- description: Cancel a running or paused workflow.
  method: POST
  name: cancel-run
  path: /v1/runs/{runId}/cancel
- description: Approve a paused workflow step.
  method: POST
  name: approve-step
  path: /v1/runs/{runId}/approve
personas: []
provider_name: Relay App
provider_slug: relay-app
search_terms:
- list workflow runs
- webhook-based workflow triggering.
- list workflows
- get configuration and status details of a specific relay.app workflow.
- automation
- workflow automation
- list all available workflows.
- ai
- workflow run history for a specific workflow.
- cancel a currently running or paused workflow run.
- trigger a workflow run via webhook.
- human-in-the-loop approval for paused workflows.
- ai automation
- approve a paused human-in-the-loop workflow step to continue execution.
- integration
- human in the loop
- approve workflow step
- trigger a relay.app workflow via webhook with optional json payload data.
- get workflow
- relay app
- webhooks
- workflow inventory management.
- list relay workflows
- get relay workflow
- workflow
- list all available workflows in the relay.app account.
- list run history for a specific workflow, with optional status filtering.
- individual workflow management.
- get the current status and details of a workflow run.
- list run instances for a workflow.
- cancel a workflow run.
- cancel a running or paused workflow.
- get the status and details of a workflow run.
- cancel run
- get run status
- trigger relay workflow
- approve a paused workflow step.
- workflow run status and management.
- approve step
- get details of a specific workflow.
- get run
- cancel workflow run
- trigger workflow
- no-code
slug: workflow-automation
source_filename: workflow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Relay App Workflow Automation\n  description: Unified workflow automation capability for Relay.app. Combines webhook-triggered workflow execution, workflow\n    management, run status monitoring, human-in-the-loop approval workflows, and run cancellation into a single AI-ready interface.\n    Used by developers, operations teams, and AI agents to trigger and manage automated workflows across 200+ integrated applications.\n  tags:\n  - Workflow Automation\n  - Webhooks\n  - Human in the Loop\n  - Integration\n  - Relay App\n  - AI Automation\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RELAY_API_KEY: RELAY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: relay-app\n    baseUri: https://api.relay.app/v1\n    description: Relay App automation platform API.\n    authentication:\n      type: apikey\n      key: X-Relay-API-Key\n      value: '{{RELAY_API_KEY}}'\n      placement: header\n\
  \    resources:\n    - name: webhooks\n      path: /webhooks/{webhookId}\n      description: Webhook trigger endpoints for workflow runs.\n      operations:\n      - name: trigger-webhook-workflow\n        method: POST\n        description: Triggers a workflow run via webhook HTTP POST.\n        inputParameters:\n        - name: webhookId\n          in: path\n          type: string\n          required: true\n          description: Unique webhook identifier.\n        - name: relay-deduplication-key\n          in: header\n          type: string\n          required: false\n          description: Deduplication key to prevent duplicate runs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payload: '{{tools.payload}}'\n    - name: workflows\n      path: /workflows\n      description: Workflow management endpoints.\n      operations:\n      - name:\
  \ list-workflows\n        method: GET\n        description: Retrieves a list of all workflows in the account.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-by-id\n      path: /workflows/{workflowId}\n      description: Individual workflow operations.\n      operations:\n      - name: get-workflow\n        method: GET\n        description: Retrieves details of a specific workflow.\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: Workflow identifier.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-runs\n      path: /workflows/{workflowId}/runs\n      description: Workflow run listing.\n      operations:\n      - name: list-workflow-runs\n        method: GET\n        description: Retrieves run instances for a workflow.\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: Workflow identifier.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by run status.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: run-by-id\n      path: /runs/{runId}\n      description:\
  \ Individual run operations.\n      operations:\n      - name: get-workflow-run\n        method: GET\n        description: Retrieves the details and status of a workflow run.\n        inputParameters:\n        - name: runId\n          in: path\n          type: string\n          required: true\n          description: Run identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: run-cancel\n      path: /runs/{runId}/cancel\n      description: Cancel a workflow run.\n      operations:\n      - name: cancel-workflow-run\n        method: POST\n        description: Cancels a currently running or paused workflow run.\n        inputParameters:\n        - name: runId\n          in: path\n          type: string\n          required: true\n          description: Run identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: run-approve\n      path: /runs/{runId}/approve\n      description: Approve a paused workflow run step.\n      operations:\n      - name: approve-workflow-run-step\n        method: POST\n        description: Approves a paused human-in-the-loop workflow step.\n        inputParameters:\n        - name: runId\n          in: path\n          type: string\n          required: true\n          description: Run identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            comment: '{{tools.comment}}'\n            inputs: '{{tools.inputs}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workflow-automation-api\n    description: Unified REST API for Relay.app workflow automation and management.\n    resources:\n    - path: /v1/webhooks/{webhookId}\n      name: webhook-triggers\n      description: Webhook-based workflow triggering.\n\
  \      operations:\n      - method: POST\n        name: trigger-workflow\n        description: Trigger a workflow run via webhook.\n        call: relay-app.trigger-webhook-workflow\n        with:\n          webhookId: rest.webhookId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows\n      name: workflows\n      description: Workflow inventory management.\n      operations:\n      - method: GET\n        name: list-workflows\n        description: List all available workflows.\n        call: relay-app.list-workflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{workflowId}\n      name: workflow\n      description: Individual workflow management.\n      operations:\n      - method: GET\n        name: get-workflow\n        description: Get details of a specific workflow.\n        call: relay-app.get-workflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/workflows/{workflowId}/runs\n      name: workflow-runs\n      description: Workflow run history for a specific workflow.\n      operations:\n      - method: GET\n        name: list-workflow-runs\n        description: List run instances for a workflow.\n        call: relay-app.list-workflow-runs\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs/{runId}\n      name: run\n      description: Workflow run status and management.\n      operations:\n      - method: GET\n        name: get-run\n        description: Get the status and details of a workflow run.\n        call: relay-app.get-workflow-run\n        with:\n          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs/{runId}/cancel\n      name: cancel-run\n      description: Cancel a workflow run.\n      operations:\n\
  \      - method: POST\n        name: cancel-run\n        description: Cancel a running or paused workflow.\n        call: relay-app.cancel-workflow-run\n        with:\n          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs/{runId}/approve\n      name: approve-run\n      description: Human-in-the-loop approval for paused workflows.\n      operations:\n      - method: POST\n        name: approve-step\n        description: Approve a paused workflow step.\n        call: relay-app.approve-workflow-run-step\n        with:\n          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: workflow-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted workflow automation via Relay.app.\n    tools:\n    - name: trigger-relay-workflow\n      description: Trigger a Relay.app workflow via webhook with optional JSON payload\
  \ data.\n      hints:\n        readOnly: false\n      call: relay-app.trigger-webhook-workflow\n      with:\n        webhookId: tools.webhookId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-relay-workflows\n      description: List all available workflows in the Relay.app account.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: relay-app.list-workflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-relay-workflow\n      description: Get configuration and status details of a specific Relay.app workflow.\n      hints:\n        readOnly: true\n      call: relay-app.get-workflow\n      with:\n        workflowId: tools.workflowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workflow-runs\n      description: List run history for a specific workflow, with optional status filtering.\n      hints:\n        readOnly: true\n      call: relay-app.list-workflow-runs\n\
  \      with:\n        workflowId: tools.workflowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-run-status\n      description: Get the current status and details of a workflow run.\n      hints:\n        readOnly: true\n      call: relay-app.get-workflow-run\n      with:\n        runId: tools.runId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-workflow-run\n      description: Cancel a currently running or paused workflow run.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: relay-app.cancel-workflow-run\n      with:\n        runId: tools.runId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approve-workflow-step\n      description: Approve a paused human-in-the-loop workflow step to continue execution.\n      hints:\n        readOnly: false\n      call: relay-app.approve-workflow-run-step\n      with:\n        runId:\
  \ tools.runId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/relay-app/refs/heads/main/capabilities/workflow-automation.yaml
tags:
- Workflow Automation
- Webhooks
- Human in the Loop
- Integration
- Relay App
- AI Automation
tools:
- description: Trigger a Relay.app workflow via webhook with optional JSON payload data.
  hints:
    readOnly: false
  name: trigger-relay-workflow
- description: List all available workflows in the Relay.app account.
  hints:
    openWorld: true
    readOnly: true
  name: list-relay-workflows
- description: Get configuration and status details of a specific Relay.app workflow.
  hints:
    readOnly: true
  name: get-relay-workflow
- description: List run history for a specific workflow, with optional status filtering.
  hints:
    readOnly: true
  name: list-workflow-runs
- description: Get the current status and details of a workflow run.
  hints:
    readOnly: true
  name: get-run-status
- description: Cancel a currently running or paused workflow run.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-workflow-run
- description: Approve a paused human-in-the-loop workflow step to continue execution.
  hints:
    readOnly: false
  name: approve-workflow-step
---

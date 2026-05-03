---
api_specs:
- filename: relay-app-openapi.yml
  format: yaml
  label: relay-app
  slug: relay-app
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/relay-app/refs/heads/main/openapi/relay-app-openapi.yml
categories: []
consumed_apis:
- relay-app
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
- automation
- cancel a workflow run.
- list all available workflows in the relay.app account.
- approve a paused workflow step.
- individual workflow management.
- workflow run status and management.
- workflow run history for a specific workflow.
- ai automation
- get the status and details of a workflow run.
- list workflows
- get run status
- workflow
- integration
- get relay workflow
- list workflow runs
- webhooks
- list all available workflows.
- trigger relay workflow
- get the current status and details of a workflow run.
- trigger workflow
- cancel a running or paused workflow.
- cancel run
- approve a paused human-in-the-loop workflow step to continue execution.
- trigger a workflow run via webhook.
- get configuration and status details of a specific relay.app workflow.
- relay app
- ai
- workflow inventory management.
- get run
- cancel a currently running or paused workflow run.
- cancel workflow run
- list run instances for a workflow.
- approve workflow step
- list run history for a specific workflow, with optional status filtering.
- trigger a relay.app workflow via webhook with optional json payload data.
- human in the loop
- workflow automation
- human-in-the-loop approval for paused workflows.
- list relay workflows
- no-code
- get details of a specific workflow.
- approve step
- get workflow
- webhook-based workflow triggering.
slug: workflow-automation
source_filename: workflow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Relay App Workflow Automation\"\n  description: >-\n    Unified workflow automation capability for Relay.app. Combines webhook-triggered\n    workflow execution, workflow management, run status monitoring, human-in-the-loop\n    approval workflows, and run cancellation into a single AI-ready interface.\n    Used by developers, operations teams, and AI agents to trigger and manage\n    automated workflows across 200+ integrated applications.\n  tags:\n    - Workflow Automation\n    - Webhooks\n    - Human in the Loop\n    - Integration\n    - Relay App\n    - AI Automation\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RELAY_API_KEY: RELAY_API_KEY\n\ncapability:\n  consumes:\n    - import: relay-app\n      location: ./shared/relay-app.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workflow-automation-api\n      description: \"Unified REST API for Relay.app\
  \ workflow automation and management.\"\n      resources:\n        - path: /v1/webhooks/{webhookId}\n          name: webhook-triggers\n          description: \"Webhook-based workflow triggering.\"\n          operations:\n            - method: POST\n              name: trigger-workflow\n              description: \"Trigger a workflow run via webhook.\"\n              call: \"relay-app.trigger-webhook-workflow\"\n              with:\n                webhookId: \"rest.webhookId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows\n          name: workflows\n          description: \"Workflow inventory management.\"\n          operations:\n            - method: GET\n              name: list-workflows\n              description: \"List all available workflows.\"\n              call: \"relay-app.list-workflows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n \
  \       - path: /v1/workflows/{workflowId}\n          name: workflow\n          description: \"Individual workflow management.\"\n          operations:\n            - method: GET\n              name: get-workflow\n              description: \"Get details of a specific workflow.\"\n              call: \"relay-app.get-workflow\"\n              with:\n                workflowId: \"rest.workflowId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows/{workflowId}/runs\n          name: workflow-runs\n          description: \"Workflow run history for a specific workflow.\"\n          operations:\n            - method: GET\n              name: list-workflow-runs\n              description: \"List run instances for a workflow.\"\n              call: \"relay-app.list-workflow-runs\"\n              with:\n                workflowId: \"rest.workflowId\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/runs/{runId}\n          name: run\n          description: \"Workflow run status and management.\"\n          operations:\n            - method: GET\n              name: get-run\n              description: \"Get the status and details of a workflow run.\"\n              call: \"relay-app.get-workflow-run\"\n              with:\n                runId: \"rest.runId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/runs/{runId}/cancel\n          name: cancel-run\n          description: \"Cancel a workflow run.\"\n          operations:\n            - method: POST\n              name: cancel-run\n              description: \"Cancel a running or paused workflow.\"\n              call: \"relay-app.cancel-workflow-run\"\n              with:\n                runId: \"rest.runId\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/runs/{runId}/approve\n          name: approve-run\n          description: \"Human-in-the-loop approval for paused workflows.\"\n          operations:\n            - method: POST\n              name: approve-step\n              description: \"Approve a paused workflow step.\"\n              call: \"relay-app.approve-workflow-run-step\"\n              with:\n                runId: \"rest.runId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: workflow-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted workflow automation via Relay.app.\"\n      tools:\n        - name: trigger-relay-workflow\n          description: \"Trigger a Relay.app workflow via webhook with optional JSON payload data.\"\n          hints:\n            readOnly: false\n          call: \"relay-app.trigger-webhook-workflow\"\n          with:\n       \
  \     webhookId: \"tools.webhookId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-relay-workflows\n          description: \"List all available workflows in the Relay.app account.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"relay-app.list-workflows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-relay-workflow\n          description: \"Get configuration and status details of a specific Relay.app workflow.\"\n          hints:\n            readOnly: true\n          call: \"relay-app.get-workflow\"\n          with:\n            workflowId: \"tools.workflowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workflow-runs\n          description: \"List run history for a specific workflow, with optional status filtering.\"\n          hints:\n           \
  \ readOnly: true\n          call: \"relay-app.list-workflow-runs\"\n          with:\n            workflowId: \"tools.workflowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-run-status\n          description: \"Get the current status and details of a workflow run.\"\n          hints:\n            readOnly: true\n          call: \"relay-app.get-workflow-run\"\n          with:\n            runId: \"tools.runId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-workflow-run\n          description: \"Cancel a currently running or paused workflow run.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"relay-app.cancel-workflow-run\"\n          with:\n            runId: \"tools.runId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ approve-workflow-step\n          description: \"Approve a paused human-in-the-loop workflow step to continue execution.\"\n          hints:\n            readOnly: false\n          call: \"relay-app.approve-workflow-run-step\"\n          with:\n            runId: \"tools.runId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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

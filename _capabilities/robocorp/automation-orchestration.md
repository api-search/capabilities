---
categories: []
consumed_apis:
- control-room
description: Unified workflow capability for RPA automation orchestration using the Robocorp Control Room API. Combines worker management, process execution, work item queuing, secret management, asset storage, webhook configuration, and task package deployment into workflows for automation operations teams.
layout: capability
name: Robocorp Automation Orchestration
operations:
- description: Get workspace details
  method: GET
  name: get-workspace
  path: /v1/workspace
- description: List all workers in the workspace
  method: GET
  name: list-workers
  path: /v1/workers
- description: Get a specific worker
  method: GET
  name: get-worker
  path: /v1/workers/{worker-id}
- description: Remove a worker
  method: DELETE
  name: delete-worker
  path: /v1/workers/{worker-id}
- description: List all worker groups
  method: GET
  name: list-worker-groups
  path: /v1/worker-groups
- description: Create a new worker group
  method: POST
  name: create-worker-group
  path: /v1/worker-groups
- description: List all automation processes
  method: GET
  name: list-processes
  path: /v1/processes
- description: Create a new automation process
  method: POST
  name: create-process
  path: /v1/processes
- description: List all runs for a process
  method: GET
  name: list-process-runs
  path: /v1/processes/{process-id}/runs
- description: Start a new process run
  method: POST
  name: start-process-run
  path: /v1/processes/{process-id}/runs
- description: List work items in the queue
  method: GET
  name: list-work-items
  path: /v1/work-items
- description: Add a new work item to the queue
  method: POST
  name: create-work-item
  path: /v1/work-items
- description: List all assets
  method: GET
  name: list-assets
  path: /v1/assets
- description: Create a new asset
  method: POST
  name: create-asset
  path: /v1/assets
- description: List secret names in the vault
  method: GET
  name: list-secrets
  path: /v1/vault/secrets
- description: Create a new vault secret
  method: POST
  name: create-secret
  path: /v1/vault/secrets
- description: List all webhooks
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Create a process webhook
  method: POST
  name: create-webhook
  path: /v1/webhooks
- description: List all task packages
  method: GET
  name: list-task-packages
  path: /v1/task-packages
- description: Deploy a new task package
  method: POST
  name: create-task-package
  path: /v1/task-packages
personas: []
provider_name: Robocorp
provider_slug: robocorp
search_terms:
- list worker groups
- automation
- create worker group
- list all webhooks
- create secret
- list all configured webhooks for process event notifications
- list process runs
- get workspace
- open source
- list work items in the queue with optional state filter
- get a specific worker
- worker group organization
- list all task packages
- start a new process run
- create task package
- deploy a new task package from zip, github, or gitlab source
- worker agent management
- create work item
- robocorp
- list all assets
- list secret names in the vault
- create webhook
- list all automation workers and their status
- list vault secret names (secret values are never returned)
- process execution runs
- individual worker
- list all runs for a process
- start process run
- work item queue management
- add a new work item to the queue
- vault secret management
- remove a worker from the workspace
- list all workers in the workspace
- list secrets
- define a new automation process with steps and schedules
- add a new work item to the process queue
- list all deployed task packages in the workspace
- asset storage
- create a process webhook
- list all stored assets in the workspace
- create a new asset
- get workspace details
- delete worker
- create a new worker group for organizing automation workers
- trigger a new execution run for an automation process
- list webhooks
- get details and status for a specific worker
- list work items
- list workers
- list all worker groups
- automation process management
- create a new automation process
- list task packages
- task package deployment
- list all worker groups for organizing workers
- create process
- list work items in the queue
- python
- remove a worker
- list processes
- create a new vault secret
- list all automation processes defined in the workspace
- orchestration
- list all automation processes
- create asset
- webhook configuration
- workflow automation
- get workspace configuration and details
- list all execution runs for an automation process
- workflow
- list assets
- create a new worker group
- get worker
- rpa
- workspace management
- deploy a new task package
slug: automation-orchestration
source_filename: automation-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Robocorp Automation Orchestration\"\n  description: >-\n    Unified workflow capability for RPA automation orchestration using the\n    Robocorp Control Room API. Combines worker management, process execution,\n    work item queuing, secret management, asset storage, webhook configuration,\n    and task package deployment into workflows for automation operations teams.\n  tags:\n    - RPA\n    - Automation\n    - Orchestration\n    - Workflow\n    - Robocorp\n    - Python\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      ROBOCORP_API_KEY: ROBOCORP_API_KEY\n      ROBOCORP_WORKSPACE_ID: ROBOCORP_WORKSPACE_ID\n\ncapability:\n  consumes:\n    - import: control-room\n      location: ./shared/control-room.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: robocorp-orchestration-api\n      description: \"Unified REST API for Robocorp RPA automation orchestration.\"\
  \n      resources:\n        - path: /v1/workspace\n          name: workspace\n          description: \"Workspace management\"\n          operations:\n            - method: GET\n              name: get-workspace\n              description: \"Get workspace details\"\n              call: \"control-room.get-workspace\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workers\n          name: workers\n          description: \"Worker agent management\"\n          operations:\n            - method: GET\n              name: list-workers\n              description: \"List all workers in the workspace\"\n              call: \"control-room.list-workers\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workers/{worker-id}\n\
  \          name: worker-detail\n          description: \"Individual worker\"\n          operations:\n            - method: GET\n              name: get-worker\n              description: \"Get a specific worker\"\n              call: \"control-room.get-worker\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n                worker_id: \"rest.worker-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-worker\n              description: \"Remove a worker\"\n              call: \"control-room.delete-worker\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n                worker_id: \"rest.worker-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/worker-groups\n          name: worker-groups\n          description: \"Worker group organization\"\n       \
  \   operations:\n            - method: GET\n              name: list-worker-groups\n              description: \"List all worker groups\"\n              call: \"control-room.list-worker-groups\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-worker-group\n              description: \"Create a new worker group\"\n              call: \"control-room.create-worker-group\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/processes\n          name: processes\n          description: \"Automation process management\"\n          operations:\n            - method: GET\n              name: list-processes\n              description: \"List all automation processes\"\n    \
  \          call: \"control-room.list-processes\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-process\n              description: \"Create a new automation process\"\n              call: \"control-room.create-process\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/processes/{process-id}/runs\n          name: process-runs\n          description: \"Process execution runs\"\n          operations:\n            - method: GET\n              name: list-process-runs\n              description: \"List all runs for a process\"\n              call: \"control-room.list-process-runs\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n         \
  \       process_id: \"rest.process-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: start-process-run\n              description: \"Start a new process run\"\n              call: \"control-room.start-process-run\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n                process_id: \"rest.process-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/work-items\n          name: work-items\n          description: \"Work item queue management\"\n          operations:\n            - method: GET\n              name: list-work-items\n              description: \"List work items in the queue\"\n              call: \"control-room.list-work-items\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n                process_id: \"rest.process_id\"\n              \
  \  state: \"rest.state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-work-item\n              description: \"Add a new work item to the queue\"\n              call: \"control-room.create-work-item\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/assets\n          name: assets\n          description: \"Asset storage\"\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List all assets\"\n              call: \"control-room.list-assets\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-asset\n\
  \              description: \"Create a new asset\"\n              call: \"control-room.create-asset\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vault/secrets\n          name: vault-secrets\n          description: \"Vault secret management\"\n          operations:\n            - method: GET\n              name: list-secrets\n              description: \"List secret names in the vault\"\n              call: \"control-room.list-secrets\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-secret\n              description: \"Create a new vault secret\"\n              call: \"control-room.create-secret\"\n              with:\n                workspace_id: \"rest.workspace_id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/webhooks\n          name: webhooks\n          description: \"Webhook configuration\"\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: \"List all webhooks\"\n              call: \"control-room.list-webhooks\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: \"Create a process webhook\"\n              call: \"control-room.create-webhook\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/task-packages\n          name: task-packages\n          description:\
  \ \"Task package deployment\"\n          operations:\n            - method: GET\n              name: list-task-packages\n              description: \"List all task packages\"\n              call: \"control-room.list-task-packages\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-task-package\n              description: \"Deploy a new task package\"\n              call: \"control-room.create-task-package\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: robocorp-orchestration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Robocorp RPA automation orchestration.\"\n      tools:\n        - name: get-workspace\n\
  \          description: \"Get workspace configuration and details\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"control-room.get-workspace\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-workers\n          description: \"List all automation workers and their status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"control-room.list-workers\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-worker\n          description: \"Get details and status for a specific worker\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"control-room.get-worker\"\n          with:\n            workspace_id: \"\
  tools.workspace_id\"\n            worker_id: \"tools.worker_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-worker\n          description: \"Remove a worker from the workspace\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"control-room.delete-worker\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n            worker_id: \"tools.worker_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-worker-groups\n          description: \"List all worker groups for organizing workers\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"control-room.list-worker-groups\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \n        - name: create-worker-group\n          description: \"Create a new worker group for organizing automation workers\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"control-room.create-worker-group\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-processes\n          description: \"List all automation processes defined in the workspace\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"control-room.list-processes\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-process\n          description: \"Define a new automation process with steps and schedules\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n          call: \"control-room.create-process\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-process-runs\n          description: \"List all execution runs for an automation process\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"control-room.list-process-runs\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n            process_id: \"tools.process_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-process-run\n          description: \"Trigger a new execution run for an automation process\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"control-room.start-process-run\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n            process_id: \"\
  tools.process_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-work-items\n          description: \"List work items in the queue with optional state filter\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"control-room.list-work-items\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n            process_id: \"tools.process_id\"\n            state: \"tools.state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-work-item\n          description: \"Add a new work item to the process queue\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"control-room.create-work-item\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-assets\n\
  \          description: \"List all stored assets in the workspace\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"control-room.list-assets\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-secrets\n          description: \"List vault secret names (secret values are never returned)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"control-room.list-secrets\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-webhooks\n          description: \"List all configured webhooks for process event notifications\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"control-room.list-webhooks\"\n          with:\n\
  \            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-task-packages\n          description: \"List all deployed task packages in the workspace\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"control-room.list-task-packages\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-task-package\n          description: \"Deploy a new task package from zip, GitHub, or GitLab source\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"control-room.create-task-package\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/robocorp/refs/heads/main/capabilities/automation-orchestration.yaml
tags:
- RPA
- Automation
- Orchestration
- Workflow
- Robocorp
- Python
tools:
- description: Get workspace configuration and details
  hints:
    openWorld: false
    readOnly: true
  name: get-workspace
- description: List all automation workers and their status
  hints:
    openWorld: false
    readOnly: true
  name: list-workers
- description: Get details and status for a specific worker
  hints:
    openWorld: false
    readOnly: true
  name: get-worker
- description: Remove a worker from the workspace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-worker
- description: List all worker groups for organizing workers
  hints:
    openWorld: false
    readOnly: true
  name: list-worker-groups
- description: Create a new worker group for organizing automation workers
  hints:
    destructive: false
    readOnly: false
  name: create-worker-group
- description: List all automation processes defined in the workspace
  hints:
    openWorld: false
    readOnly: true
  name: list-processes
- description: Define a new automation process with steps and schedules
  hints:
    destructive: false
    readOnly: false
  name: create-process
- description: List all execution runs for an automation process
  hints:
    openWorld: false
    readOnly: true
  name: list-process-runs
- description: Trigger a new execution run for an automation process
  hints:
    destructive: false
    readOnly: false
  name: start-process-run
- description: List work items in the queue with optional state filter
  hints:
    openWorld: false
    readOnly: true
  name: list-work-items
- description: Add a new work item to the process queue
  hints:
    destructive: false
    readOnly: false
  name: create-work-item
- description: List all stored assets in the workspace
  hints:
    openWorld: false
    readOnly: true
  name: list-assets
- description: List vault secret names (secret values are never returned)
  hints:
    openWorld: false
    readOnly: true
  name: list-secrets
- description: List all configured webhooks for process event notifications
  hints:
    openWorld: false
    readOnly: true
  name: list-webhooks
- description: List all deployed task packages in the workspace
  hints:
    openWorld: false
    readOnly: true
  name: list-task-packages
- description: Deploy a new task package from zip, GitHub, or GitLab source
  hints:
    destructive: false
    readOnly: false
  name: create-task-package
---

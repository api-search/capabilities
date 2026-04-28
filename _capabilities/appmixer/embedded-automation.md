---
categories:
- automation
consumed_apis:
- appmixer
description: Workflow capability for managing embedded automation within SaaS products using Appmixer. Combines flow lifecycle management, user provisioning, data storage, and human-in-the-loop task handling into a unified workflow for SaaS developers embedding white-labeled automation into their products.
layout: capability
name: Appmixer Embedded Automation
operations:
- description: List all automation flows
  method: GET
  name: list-flows
  path: /v1/flows
- description: Create a new automation flow
  method: POST
  name: create-flow
  path: /v1/flows
- description: List automation users
  method: GET
  name: list-users
  path: /v1/users
- description: List pending people tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
personas: []
provider_name: Appmixer
provider_slug: appmixer
search_terms:
- human-in-the-loop tasks
- automation
- user management for embedded automation
- create flow
- starts/runs an automation flow to execute its workflow
- lists human-in-the-loop tasks waiting for user review or approval
- list pending tasks
- developer embedding white-labeled automation into a product
- create automation flow
- list all automation flows
- approve task
- agentic
- creates a new automation flow in appmixer for embedding in a product
- appmixer
- lists all automation workflows configured in appmixer
- list automation users
- end-to-end workflow for embedding automation in saas products
- creating, running, and managing automation flows
- automation flow lifecycle
- provisioning and managing automation platform users
- create a new automation flow
- workflows
- run automation flow
- lists users who have access to the embedded automation platform
- list users
- list automation flows
- list pending people tasks
- approves or completes a pending human-in-the-loop task in an automation flow
- low-code
- managing tasks requiring human review or approval
- integrations
- product user interacting with embedded automation workflows
- saas
- persisting and retrieving workflow state and data
- list flows
- list tasks
- embedded ipaas
slug: embedded-automation
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Appmixer Embedded Automation\n  description: >-\n    Workflow capability for managing embedded automation within SaaS products using\n    Appmixer. Combines flow lifecycle management, user provisioning, data storage,\n    and human-in-the-loop task handling into a unified workflow for SaaS developers\n    embedding white-labeled automation into their products.\n  tags:\n    - Appmixer\n    - Automation\n    - Embedded iPaaS\n    - Workflows\n    - SaaS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APPMIXER_API_TOKEN: APPMIXER_API_TOKEN\n\ncapability:\n  consumes:\n    - import: appmixer\n      location: ./shared/appmixer-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: embedded-automation-api\n      description: Unified REST API for Appmixer embedded automation management.\n      resources:\n        - path: /v1/flows\n          name: flows\n    \
  \      description: Automation flow lifecycle\n          operations:\n            - method: GET\n              name: list-flows\n              description: List all automation flows\n              call: \"appmixer.list-flows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-flow\n              description: Create a new automation flow\n              call: \"appmixer.create-flow\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: User management for embedded automation\n          operations:\n            - method: GET\n              name: list-users\n              description: List automation users\n              call: \"appmixer.list-users\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n        - path: /v1/tasks\n          name: tasks\n          description: Human-in-the-loop tasks\n          operations:\n            - method: GET\n              name: list-tasks\n              description: List pending people tasks\n              call: \"appmixer.list-people-tasks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: embedded-automation-mcp\n      transport: http\n      description: MCP server for AI-assisted automation management in Appmixer.\n      tools:\n        - name: list-automation-flows\n          description: Lists all automation workflows configured in Appmixer\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appmixer.list-flows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-automation-flow\n    \
  \      description: Creates a new automation flow in Appmixer for embedding in a product\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"appmixer.create-flow\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: run-automation-flow\n          description: Starts/runs an automation flow to execute its workflow\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"appmixer.start-flow\"\n          with:\n            flowId: \"tools.flowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-pending-tasks\n          description: Lists human-in-the-loop tasks waiting for user review or approval\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appmixer.list-people-tasks\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: approve-task\n          description: Approves or completes a pending human-in-the-loop task in an automation flow\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"appmixer.complete-task\"\n          with:\n            taskId: \"tools.taskId\"\n            decision: \"tools.decision\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-automation-users\n          description: Lists users who have access to the embedded automation platform\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appmixer.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/appmixer/refs/heads/main/capabilities/embedded-automation.yaml
tags:
- Appmixer
- Automation
- Embedded iPaaS
- Workflows
- SaaS
tools:
- description: Lists all automation workflows configured in Appmixer
  hints:
    idempotent: true
    readOnly: true
  name: list-automation-flows
- description: Creates a new automation flow in Appmixer for embedding in a product
  hints:
    destructive: false
    readOnly: false
  name: create-automation-flow
- description: Starts/runs an automation flow to execute its workflow
  hints:
    destructive: false
    readOnly: false
  name: run-automation-flow
- description: Lists human-in-the-loop tasks waiting for user review or approval
  hints:
    idempotent: true
    readOnly: true
  name: list-pending-tasks
- description: Approves or completes a pending human-in-the-loop task in an automation flow
  hints:
    destructive: false
    readOnly: false
  name: approve-task
- description: Lists users who have access to the embedded automation platform
  hints:
    idempotent: true
    readOnly: true
  name: list-automation-users
---

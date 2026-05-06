---
categories:
- automation
consumed_apis: []
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
- appmixer
- list all automation flows
- low-code
- list flows
- user management for embedded automation
- creates a new automation flow in appmixer for embedding in a product
- create a new automation flow
- managing tasks requiring human review or approval
- list tasks
- list pending tasks
- creating, running, and managing automation flows
- starts/runs an automation flow to execute its workflow
- run automation flow
- lists all automation workflows configured in appmixer
- integrations
- lists users who have access to the embedded automation platform
- saas
- list pending people tasks
- list automation flows
- product user interacting with embedded automation workflows
- provisioning and managing automation platform users
- lists human-in-the-loop tasks waiting for user review or approval
- embedded ipaas
- workflows
- persisting and retrieving workflow state and data
- list automation users
- human-in-the-loop tasks
- approves or completes a pending human-in-the-loop task in an automation flow
- approve task
- end-to-end workflow for embedding automation in saas products
- list users
- agentic
- automation flow lifecycle
- create flow
- create automation flow
- developer embedding white-labeled automation into a product
- automation
slug: embedded-automation
source_filename: embedded-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Appmixer Embedded Automation\n  description: Workflow capability for managing embedded automation within SaaS products using Appmixer. Combines flow lifecycle\n    management, user provisioning, data storage, and human-in-the-loop task handling into a unified workflow for SaaS developers\n    embedding white-labeled automation into their products.\n  tags:\n  - Appmixer\n  - Automation\n  - Embedded iPaaS\n  - Workflows\n  - SaaS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APPMIXER_API_TOKEN: APPMIXER_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: appmixer\n    baseUri: https://api.appmixer.com/v1\n    description: Appmixer REST API for workflow and integration management\n    authentication:\n      type: bearer\n      token: '{{APPMIXER_API_TOKEN}}'\n    resources:\n    - name: flows\n      path: /flows\n      description: Workflow (flow) lifecycle management\n      operations:\n\
  \      - name: list-flows\n        method: GET\n        description: Returns a list of automation flows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-flow\n        method: POST\n        description: Creates a new automation flow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: flow\n      path: /flows/{flowId}\n      description: Single flow operations\n      operations:\n      - name: get-flow\n        method: GET\n        description: Returns a specific automation flow\n        inputParameters:\n        - name: flowId\n          in: path\n          type: string\n          required: true\n          description: Flow identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: start-flow\n        method: POST\n        description: Starts/runs a flow\n        inputParameters:\n        - name: flowId\n          in: path\n          type: string\n          required: true\n          description: Flow identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: User management\n      operations:\n      - name: list-users\n        method: GET\n        description: Returns a list of Appmixer users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Creates a new Appmixer user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type:\
  \ json\n          data:\n            username: '{{tools.username}}'\n            email: '{{tools.email}}'\n    - name: data-stores\n      path: /data-stores\n      description: Data store (key-value storage) management\n      operations:\n      - name: list-data-stores\n        method: GET\n        description: Returns a list of data stores\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-tasks\n      path: /people-tasks\n      description: Human-in-the-loop task management\n      operations:\n      - name: list-people-tasks\n        method: GET\n        description: Returns a list of people tasks pending human action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: complete-task\n        method: POST\n        description: Completes a people task with a human decision\n        inputParameters:\n  \
  \      - name: taskId\n          in: path\n          type: string\n          required: true\n          description: Task identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            decision: '{{tools.decision}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: embedded-automation-api\n    description: Unified REST API for Appmixer embedded automation management.\n    resources:\n    - path: /v1/flows\n      name: flows\n      description: Automation flow lifecycle\n      operations:\n      - method: GET\n        name: list-flows\n        description: List all automation flows\n        call: appmixer.list-flows\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-flow\n        description: Create a new automation flow\n        call: appmixer.create-flow\n        with:\n\
  \          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User management for embedded automation\n      operations:\n      - method: GET\n        name: list-users\n        description: List automation users\n        call: appmixer.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: Human-in-the-loop tasks\n      operations:\n      - method: GET\n        name: list-tasks\n        description: List pending people tasks\n        call: appmixer.list-people-tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: embedded-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted automation management in Appmixer.\n    tools:\n    - name: list-automation-flows\n      description: Lists all automation workflows\
  \ configured in Appmixer\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appmixer.list-flows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-automation-flow\n      description: Creates a new automation flow in Appmixer for embedding in a product\n      hints:\n        readOnly: false\n        destructive: false\n      call: appmixer.create-flow\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-automation-flow\n      description: Starts/runs an automation flow to execute its workflow\n      hints:\n        readOnly: false\n        destructive: false\n      call: appmixer.start-flow\n      with:\n        flowId: tools.flowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pending-tasks\n      description: Lists human-in-the-loop tasks waiting for user review or approval\n      hints:\n        readOnly: true\n\
  \        idempotent: true\n      call: appmixer.list-people-tasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approve-task\n      description: Approves or completes a pending human-in-the-loop task in an automation flow\n      hints:\n        readOnly: false\n        destructive: false\n      call: appmixer.complete-task\n      with:\n        taskId: tools.taskId\n        decision: tools.decision\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-automation-users\n      description: Lists users who have access to the embedded automation platform\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appmixer.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

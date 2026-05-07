---
categories: []
consumed_apis: []
description: Unified capability for managers and HR teams managing Workday business processes including initiating workflows, processing approvals, managing inbox items, and monitoring process status.
layout: capability
name: Workday Workflow Management
operations:
- description: List process definitions
  method: GET
  name: list-process-definitions
  path: /v1/process-definitions
- description: List process instances
  method: GET
  name: list-process-instances
  path: /v1/process-instances
- description: Start a new process
  method: POST
  name: initiate-process
  path: /v1/process-instances
- description: Get a process instance
  method: GET
  name: get-process-instance
  path: /v1/process-instances/{instanceId}
- description: List inbox items
  method: GET
  name: list-inbox-items
  path: /v1/inbox-items
- description: Approve inbox item
  method: POST
  name: approve-inbox-item
  path: /v1/inbox-items/{itemId}/approve
- description: Deny inbox item
  method: POST
  name: deny-inbox-item
  path: /v1/inbox-items/{itemId}/deny
personas: []
provider_name: Workday Business Processes
provider_slug: workday-business-processes
search_terms:
- list workday business process type definitions available for initiation
- process instances
- approvals
- approve inbox item
- business process definitions
- start a new process
- list all steps in a business process instance with completion status
- list process definitions
- workday
- get a process instance
- deny a workday business process inbox item to reject the workflow step
- list workday inbox items pending action for a user or worker
- approve a workday business process inbox item to advance the workflow
- hcm
- get the current status, steps, and progress of a business process instance
- inbox items
- get process instance
- list process instances
- enterprise
- initiate process
- list inbox items
- get process definition
- business processes
- workflows
- cancel process instance
- list process steps
- initiate a new workday business process for hire, termination, or other workflow
- deny inbox item
- get a specific workday business process definition with step details
- list workday business process instances with status and progress tracking
- cancel a running business process instance with a reason
slug: workflow-management
source_filename: workflow-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Workflow Management\n  description: Unified capability for managers and HR teams managing Workday business processes including initiating workflows,\n    processing approvals, managing inbox items, and monitoring process status.\n  tags:\n  - Approvals\n  - Business Processes\n  - Enterprise\n  - HCM\n  - Workflows\n  - Workday\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_CLIENT_ID: WORKDAY_CLIENT_ID\n    WORKDAY_CLIENT_SECRET: WORKDAY_CLIENT_SECRET\n    WORKDAY_TENANT: WORKDAY_TENANT\ncapability:\n  consumes:\n  - openapi: workday-business-processes\n    location: ../../openapi/workday-business-processes-openapi.yml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workday-workflow-management-api\n    description: Unified REST API for Workday Workflow Management.\n    resources:\n    - path: /v1/process-definitions\n      name: process-definitions\n      description:\
  \ Business process definitions\n      operations:\n      - method: GET\n        name: list-process-definitions\n        description: List process definitions\n        call: workday-business-processes.list-business-process-definitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/process-instances\n      name: process-instances\n      description: Process instances\n      operations:\n      - method: GET\n        name: list-process-instances\n        description: List process instances\n        call: workday-business-processes.list-process-instances\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: initiate-process\n        description: Start a new process\n        call: workday-business-processes.initiate-process\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/process-instances/{instanceId}\n      name: process-instance-by-id\n      operations:\n\
  \      - method: GET\n        name: get-process-instance\n        description: Get a process instance\n        call: workday-business-processes.get-process-instance\n        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inbox-items\n      name: inbox-items\n      description: Inbox items\n      operations:\n      - method: GET\n        name: list-inbox-items\n        description: List inbox items\n        call: workday-business-processes.list-inbox-items\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inbox-items/{itemId}/approve\n      name: inbox-item-approve\n      operations:\n      - method: POST\n        name: approve-inbox-item\n        description: Approve inbox item\n        call: workday-business-processes.approve-inbox-item\n        with:\n          itemId: rest.itemId\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/inbox-items/{itemId}/deny\n      name: inbox-item-deny\n      operations:\n      - method: POST\n        name: deny-inbox-item\n        description: Deny inbox item\n        call: workday-business-processes.deny-inbox-item\n        with:\n          itemId: rest.itemId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: workday-workflow-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Workday Workflow Management, business process automation, and approval workflows.\n    tools:\n    - name: list-process-definitions\n      description: List Workday business process type definitions available for initiation\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-business-processes.list-business-process-definitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-process-definition\n      description: Get a specific\
  \ Workday business process definition with step details\n      hints:\n        readOnly: true\n      call: workday-business-processes.get-business-process-definition\n      with:\n        definitionId: tools.definitionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-process-instances\n      description: List Workday business process instances with status and progress tracking\n      hints:\n        readOnly: true\n      call: workday-business-processes.list-process-instances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiate-process\n      description: Initiate a new Workday business process for hire, termination, or other workflow\n      hints:\n        readOnly: false\n      call: workday-business-processes.initiate-process\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-process-instance\n      description: Get the current status, steps, and progress of a business process\
  \ instance\n      hints:\n        readOnly: true\n      call: workday-business-processes.get-process-instance\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-process-steps\n      description: List all steps in a business process instance with completion status\n      hints:\n        readOnly: true\n      call: workday-business-processes.list-process-steps\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-process-instance\n      description: Cancel a running business process instance with a reason\n      hints:\n        readOnly: false\n      call: workday-business-processes.cancelProcessInstance\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-inbox-items\n      description: List Workday inbox items pending action for a user\
  \ or worker\n      hints:\n        readOnly: true\n      call: workday-business-processes.list-inbox-items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approve-inbox-item\n      description: Approve a Workday business process inbox item to advance the workflow\n      hints:\n        readOnly: false\n      call: workday-business-processes.approve-inbox-item\n      with:\n        itemId: tools.itemId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deny-inbox-item\n      description: Deny a Workday business process inbox item to reject the workflow step\n      hints:\n        readOnly: false\n      call: workday-business-processes.deny-inbox-item\n      with:\n        itemId: tools.itemId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-business-processes/refs/heads/main/capabilities/workflow-management.yaml
tags:
- Approvals
- Business Processes
- Enterprise
- HCM
- Workflows
- Workday
tools:
- description: List Workday business process type definitions available for initiation
  hints:
    openWorld: true
    readOnly: true
  name: list-process-definitions
- description: Get a specific Workday business process definition with step details
  hints:
    readOnly: true
  name: get-process-definition
- description: List Workday business process instances with status and progress tracking
  hints:
    readOnly: true
  name: list-process-instances
- description: Initiate a new Workday business process for hire, termination, or other workflow
  hints:
    readOnly: false
  name: initiate-process
- description: Get the current status, steps, and progress of a business process instance
  hints:
    readOnly: true
  name: get-process-instance
- description: List all steps in a business process instance with completion status
  hints:
    readOnly: true
  name: list-process-steps
- description: Cancel a running business process instance with a reason
  hints:
    readOnly: false
  name: cancel-process-instance
- description: List Workday inbox items pending action for a user or worker
  hints:
    readOnly: true
  name: list-inbox-items
- description: Approve a Workday business process inbox item to advance the workflow
  hints:
    readOnly: false
  name: approve-inbox-item
- description: Deny a Workday business process inbox item to reject the workflow step
  hints:
    readOnly: false
  name: deny-inbox-item
---

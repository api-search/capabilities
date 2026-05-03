---
categories: []
consumed_apis:
- salesforce-flow
description: Unified workflow capability for managing and executing Salesforce Flow automation processes. Combines flow definition management, interview execution, and invocable action triggering for business process automation teams.
layout: capability
name: Salesforce Flow Automation
operations:
- description: List all Flow definitions in the org
  method: GET
  name: list-flows
  path: /v1/flows
- description: Get a specific Flow definition
  method: GET
  name: get-flow
  path: /v1/flows/{flowId}
- description: Update a Flow definition
  method: PATCH
  name: update-flow
  path: /v1/flows/{flowId}
- description: Start a new Flow Interview
  method: POST
  name: create-flow-interview
  path: /v1/interviews
- description: Get current Flow Interview state
  method: GET
  name: get-flow-interview
  path: /v1/interviews/{interviewId}
- description: Delete a Flow Interview
  method: DELETE
  name: delete-flow-interview
  path: /v1/interviews/{interviewId}
- description: List all invocable flow actions
  method: GET
  name: list-invocable-flows
  path: /v1/invocable-flows
- description: Get invocable flow input/output schema
  method: GET
  name: get-invocable-flow-metadata
  path: /v1/invocable-flows/{flowApiName}
- description: Execute a flow action
  method: POST
  name: invoke-flow
  path: /v1/invocable-flows/{flowApiName}
personas: []
provider_name: Salesforce Flow
provider_slug: salesforce-flow
search_terms:
- query flow records using soql for advanced filtering
- list invocable flows
- get the current state and output variables of a running flow interview
- delete flow interview
- execute specific invocable flows
- list all flows exposed as invocable actions
- start flow interview
- workflow
- update a flow definition's status or description
- automation
- get flow
- process builder
- salesforce
- flow
- delete a flow interview
- execute a salesforce flow as an invocable action with specified input variables
- get invocable flow metadata
- update flow
- flow interview (execution instance) management
- get invocable flow schema
- invoke flow
- delete a paused or stale flow interview
- get flow interview
- get a specific flow definition
- crm
- create flow interview
- business process
- query flows
- list all flow definitions in the org
- get details for a specific flow definition by id
- get input and output variable schema for an invocable flow
- get invocable flow input/output schema
- create and start a new flow interview instance with input variables
- list all invocable flow actions
- list flows
- get flow interview status
- get current flow interview state
- execute a flow action
- invocable flow action catalog
- individual interview operations
- individual flow operations
- list all flow definitions in the salesforce org
- update a flow definition
- flow definition management
- start a new flow interview
slug: flow-automation
source_filename: flow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Flow Automation\"\n  description: >-\n    Unified workflow capability for managing and executing Salesforce Flow\n    automation processes. Combines flow definition management, interview\n    execution, and invocable action triggering for business process\n    automation teams.\n  tags:\n    - Salesforce\n    - Flow\n    - Automation\n    - Workflow\n    - Business Process\n    - CRM\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: salesforce-flow\n      location: ./shared/flow-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: flow-automation-api\n      description: \"Unified REST API for Salesforce Flow automation management.\"\n      resources:\n        - path: /v1/flows\n          name: flows\n          description: \"Flow definition management\"\
  \n          operations:\n            - method: GET\n              name: list-flows\n              description: \"List all Flow definitions in the org\"\n              call: \"salesforce-flow.list-flows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/flows/{flowId}\n          name: flow\n          description: \"Individual flow operations\"\n          operations:\n            - method: GET\n              name: get-flow\n              description: \"Get a specific Flow definition\"\n              call: \"salesforce-flow.get-flow\"\n              with:\n                flowId: \"rest.flowId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-flow\n              description: \"Update a Flow definition\"\n              call: \"salesforce-flow.update-flow\"\n              with:\n                flowId: \"rest.flowId\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/interviews\n          name: interviews\n          description: \"Flow interview (execution instance) management\"\n          operations:\n            - method: POST\n              name: create-flow-interview\n              description: \"Start a new Flow Interview\"\n              call: \"salesforce-flow.create-flow-interview\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/interviews/{interviewId}\n          name: interview\n          description: \"Individual interview operations\"\n          operations:\n            - method: GET\n              name: get-flow-interview\n              description: \"Get current Flow Interview state\"\n              call: \"salesforce-flow.get-flow-interview\"\n              with:\n                interviewId: \"rest.interviewId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-flow-interview\n              description: \"Delete a Flow Interview\"\n              call: \"salesforce-flow.delete-flow-interview\"\n              with:\n                interviewId: \"rest.interviewId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invocable-flows\n          name: invocable-flows\n          description: \"Invocable flow action catalog\"\n          operations:\n            - method: GET\n              name: list-invocable-flows\n              description: \"List all invocable flow actions\"\n              call: \"salesforce-flow.list-invocable-flows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invocable-flows/{flowApiName}\n          name: invocable-flow\n          description: \"Execute specific\
  \ invocable flows\"\n          operations:\n            - method: GET\n              name: get-invocable-flow-metadata\n              description: \"Get invocable flow input/output schema\"\n              call: \"salesforce-flow.get-invocable-flow-metadata\"\n              with:\n                flowApiName: \"rest.flowApiName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: invoke-flow\n              description: \"Execute a flow action\"\n              call: \"salesforce-flow.invoke-flow\"\n              with:\n                flowApiName: \"rest.flowApiName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: flow-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salesforce Flow automation management.\"\n      tools:\n        - name: list-flows\n\
  \          description: \"List all Flow definitions in the Salesforce org\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"salesforce-flow.list-flows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-flow\n          description: \"Get details for a specific Flow definition by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-flow.get-flow\"\n          with:\n            flowId: \"tools.flowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-flow\n          description: \"Update a Flow definition's status or description\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesforce-flow.update-flow\"\n          with:\n            flowId: \"tools.flowId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: start-flow-interview\n          description: \"Create and start a new Flow Interview instance with input variables\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-flow.create-flow-interview\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-flow-interview-status\n          description: \"Get the current state and output variables of a running Flow Interview\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-flow.get-flow-interview\"\n          with:\n            interviewId: \"tools.interviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-flow-interview\n          description: \"Delete a paused or stale Flow Interview\"\n          hints:\n            readOnly: false\n\
  \            destructive: true\n            idempotent: true\n          call: \"salesforce-flow.delete-flow-interview\"\n          with:\n            interviewId: \"tools.interviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-invocable-flows\n          description: \"List all Flows exposed as invocable actions\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"salesforce-flow.list-invocable-flows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-invocable-flow-schema\n          description: \"Get input and output variable schema for an invocable flow\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-flow.get-invocable-flow-metadata\"\n          with:\n            flowApiName: \"tools.flowApiName\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: invoke-flow\n          description: \"Execute a Salesforce Flow as an invocable action with specified input variables\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-flow.invoke-flow\"\n          with:\n            flowApiName: \"tools.flowApiName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-flows\n          description: \"Query Flow records using SOQL for advanced filtering\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-flow.query-flows\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-flow/refs/heads/main/capabilities/flow-automation.yaml
tags:
- Salesforce
- Flow
- Automation
- Workflow
- Business Process
- CRM
tools:
- description: List all Flow definitions in the Salesforce org
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-flows
- description: Get details for a specific Flow definition by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-flow
- description: Update a Flow definition's status or description
  hints:
    idempotent: true
    readOnly: false
  name: update-flow
- description: Create and start a new Flow Interview instance with input variables
  hints:
    destructive: false
    readOnly: false
  name: start-flow-interview
- description: Get the current state and output variables of a running Flow Interview
  hints:
    idempotent: true
    readOnly: true
  name: get-flow-interview-status
- description: Delete a paused or stale Flow Interview
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-flow-interview
- description: List all Flows exposed as invocable actions
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-invocable-flows
- description: Get input and output variable schema for an invocable flow
  hints:
    idempotent: true
    readOnly: true
  name: get-invocable-flow-schema
- description: Execute a Salesforce Flow as an invocable action with specified input variables
  hints:
    destructive: false
    readOnly: false
  name: invoke-flow
- description: Query Flow records using SOQL for advanced filtering
  hints:
    idempotent: true
    readOnly: true
  name: query-flows
---

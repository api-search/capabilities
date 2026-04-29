---
categories:
- automation
consumed_apis:
- management-api
description: Workflow capability for managing Power Automate flows, environments, and connectors. Used by automation engineers and platform administrators.
layout: capability
name: Microsoft Power Automate Flow Automation
operations:
- description: List all environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: List flows
  method: GET
  name: list-flows
  path: /v1/flows
- description: Create a flow
  method: POST
  name: create-flow
  path: /v1/flows
- description: Get flow details
  method: GET
  name: get-flow
  path: /v1/flows
- description: Update a flow
  method: PATCH
  name: update-flow
  path: /v1/flows
- description: Delete a flow
  method: DELETE
  name: delete-flow
  path: /v1/flows
- description: List connectors
  method: GET
  name: list-connectors
  path: /v1/connectors
personas: []
provider_name: Microsoft Power Automate
provider_slug: microsoft-power-automate
search_terms:
- connector management
- managing environments and available connectors
- update a flow
- creates and manages automation flows
- microsoft power automate
- low-code
- get details of a specific flow
- get details of a specific connector
- delete a flow
- get connector
- list all power automate environments
- delete flow
- turn off flow
- list available connectors in an environment
- environment management
- list all environments
- workflow
- manages environments, connectors, and permissions
- manage flows, environments, and connectors
- microsoft
- update a flow's properties
- list flows in an environment
- create a flow
- get flow
- stop/deactivate a flow
- integration
- flow management
- rpa
- Platform Administrator
- automation
- create a new automation flow
- update flow
- Automation Engineer
- creating, running, and managing automation flows
- turn on flow
- power platform
- flow lifecycle management
- list environments
- business process
- start/activate a flow
- list connectors
- get flow details
- create flow
- list flows
slug: flow-automation
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Power Automate Flow Automation\"\n  description: \"Workflow capability for managing Power Automate flows, environments, and connectors. Used by automation engineers and platform administrators.\"\n  tags:\n    - Microsoft Power Automate\n    - Automation\n    - Flow Management\n    - Low-Code\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      POWER_AUTOMATE_TOKEN: POWER_AUTOMATE_TOKEN\n\ncapability:\n  consumes:\n    - import: management-api\n      location: ./shared/management-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: flow-automation-api\n      description: \"Unified REST API for Power Automate flow automation workflows.\"\n      resources:\n        - path: /v1/environments\n          name: environments\n          description: \"Environment management\"\n          operations:\n            - method: GET\n              name: list-environments\n\
  \              description: \"List all environments\"\n              call: \"management-api.list-environments\"\n        - path: /v1/flows\n          name: flows\n          description: \"Flow lifecycle management\"\n          operations:\n            - method: GET\n              name: list-flows\n              description: \"List flows\"\n              call: \"management-api.list-flows\"\n            - method: POST\n              name: create-flow\n              description: \"Create a flow\"\n              call: \"management-api.create-flow\"\n            - method: GET\n              name: get-flow\n              description: \"Get flow details\"\n              call: \"management-api.get-flow\"\n            - method: PATCH\n              name: update-flow\n              description: \"Update a flow\"\n              call: \"management-api.update-flow\"\n            - method: DELETE\n              name: delete-flow\n              description: \"Delete a flow\"\n              call: \"management-api.delete-flow\"\
  \n        - path: /v1/connectors\n          name: connectors\n          description: \"Connector management\"\n          operations:\n            - method: GET\n              name: list-connectors\n              description: \"List connectors\"\n              call: \"management-api.list-connectors\"\n\n    - type: mcp\n      port: 9090\n      namespace: flow-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Power Automate management.\"\n      tools:\n        - name: list-environments\n          description: \"List all Power Automate environments\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"management-api.list-environments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-flows\n          description: \"List flows in an environment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"management-api.list-flows\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-flow\n          description: \"Create a new automation flow\"\n          hints:\n            readOnly: false\n          call: \"management-api.create-flow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-flow\n          description: \"Get details of a specific flow\"\n          hints:\n            readOnly: true\n          call: \"management-api.get-flow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-flow\n          description: \"Update a flow's properties\"\n          hints:\n            readOnly: false\n          call: \"management-api.update-flow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-flow\n          description: \"Delete a flow\"\n          hints:\n            destructive:\
  \ true\n          call: \"management-api.delete-flow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: turn-on-flow\n          description: \"Start/activate a flow\"\n          hints:\n            readOnly: false\n          call: \"management-api.turn-on-flow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: turn-off-flow\n          description: \"Stop/deactivate a flow\"\n          hints:\n            readOnly: false\n          call: \"management-api.turn-off-flow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connectors\n          description: \"List available connectors in an environment\"\n          hints:\n            readOnly: true\n          call: \"management-api.list-connectors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-connector\n  \
  \        description: \"Get details of a specific connector\"\n          hints:\n            readOnly: true\n          call: \"management-api.get-connector\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-power-automate/refs/heads/main/capabilities/flow-automation.yaml
tags:
- Microsoft Power Automate
- Automation
- Flow Management
- Low-Code
tools:
- description: List all Power Automate environments
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: List flows in an environment
  hints:
    openWorld: true
    readOnly: true
  name: list-flows
- description: Create a new automation flow
  hints:
    readOnly: false
  name: create-flow
- description: Get details of a specific flow
  hints:
    readOnly: true
  name: get-flow
- description: Update a flow's properties
  hints:
    readOnly: false
  name: update-flow
- description: Delete a flow
  hints:
    destructive: true
  name: delete-flow
- description: Start/activate a flow
  hints:
    readOnly: false
  name: turn-on-flow
- description: Stop/deactivate a flow
  hints:
    readOnly: false
  name: turn-off-flow
- description: List available connectors in an environment
  hints:
    readOnly: true
  name: list-connectors
- description: Get details of a specific connector
  hints:
    readOnly: true
  name: get-connector
---

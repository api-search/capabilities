---
api_specs:
- filename: activepieces.json
  format: json
  label: activepieces
  slug: activepieces
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/activepieces/refs/heads/main/openapi/activepieces.json
categories:
- automation
consumed_apis:
- activepieces
description: Unified workflow capability for building, managing, monitoring, and debugging automation flows. Used by developers and no-code builders to orchestrate integrations across 400+ app connections.
layout: capability
name: Activepieces Workflow Automation
operations:
- description: List automation flows
  method: GET
  name: list-flows
  path: /v1/flows
- description: Create a new automation flow
  method: POST
  name: create-flow
  path: /v1/flows
- description: List flow execution runs
  method: GET
  name: list-flow-runs
  path: /v1/flow-runs
- description: List app connections
  method: GET
  name: list-connections
  path: /v1/connections
- description: List projects
  method: GET
  name: list-projects
  path: /v1/projects
personas: []
provider_name: Activepieces
provider_slug: activepieces
search_terms:
- create a new automation flow
- list app connections
- monitors flow execution, manages connections, troubleshoots failures
- Operations Engineer
- integration
- no-code
- mcp
- app connection management
- create a new automation flow in activepieces
- list all app connections available in the project
- No Code Builder
- list automation flows
- list all automation flows in the activepieces project
- Developer
- list execution history for automation flows
- ai agents
- execution monitoring
- open source
- get flow run
- get details of a specific flow execution run
- list flow execution runs
- list connections
- retrieve a specific automation flow by id
- third-party app connections and piece management
- activepieces
- project, user, and organization administration
- get flow
- build and monitor automation flows, manage connections, debug executions
- creates automation workflows using the visual builder
- list all activepieces projects
- list flows
- workflow automation and flow orchestration
- automation
- project management
- list projects
- delete flow
- workflow
- automation flow management
- builds custom integrations using the api and typescript pieces
- create flow
- delete an automation flow
- list flow runs
slug: workflow-automation
source_filename: workflow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Activepieces Workflow Automation\"\n  description: \"Unified workflow capability for building, managing, monitoring, and debugging automation flows. Used by developers and no-code builders to orchestrate integrations across 400+ app connections.\"\n  tags:\n    - Activepieces\n    - Automation\n    - No-Code\n    - Workflow\n    - Integration\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ACTIVEPIECES_API_KEY: ACTIVEPIECES_API_KEY\n      ACTIVEPIECES_PROJECT_ID: ACTIVEPIECES_PROJECT_ID\n\ncapability:\n  consumes:\n    - import: activepieces\n      location: ./shared/activepieces.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workflow-automation-api\n      description: \"Unified REST API for workflow automation with Activepieces.\"\n      resources:\n        - path: /v1/flows\n          name: flows\n          description: \"Automation flow management\"\
  \n          operations:\n            - method: GET\n              name: list-flows\n              description: \"List automation flows\"\n              call: \"activepieces.list-flows\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-flow\n              description: \"Create a new automation flow\"\n              call: \"activepieces.create-flow\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/flow-runs\n          name: flow-runs\n          description: \"Execution monitoring\"\n          operations:\n            - method: GET\n              name: list-flow-runs\n              description: \"List flow execution runs\"\n              call: \"activepieces.list-flow-runs\"\n              with:\n                projectId: \"rest.projectId\"\n \
  \             outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connections\n          name: connections\n          description: \"App connection management\"\n          operations:\n            - method: GET\n              name: list-connections\n              description: \"List app connections\"\n              call: \"activepieces.list-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects\n          name: projects\n          description: \"Project management\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List projects\"\n              call: \"activepieces.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: workflow-automation-mcp\n      transport: http\n\
  \      description: \"MCP server for AI-assisted workflow automation with Activepieces.\"\n      tools:\n        - name: list-flows\n          description: \"List all automation flows in the Activepieces project\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"activepieces.list-flows\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-flow\n          description: \"Create a new automation flow in Activepieces\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"activepieces.create-flow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-flow\n          description: \"Retrieve a specific automation flow by ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n\
  \          call: \"activepieces.get-flow\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-flow\n          description: \"Delete an automation flow\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"activepieces.delete-flow\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-flow-runs\n          description: \"List execution history for automation flows\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"activepieces.list-flow-runs\"\n          with:\n            projectId: \"tools.projectId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-flow-run\n   \
  \       description: \"Get details of a specific flow execution run\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"activepieces.get-flow-run\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connections\n          description: \"List all app connections available in the project\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"activepieces.list-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-projects\n          description: \"List all Activepieces projects\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"activepieces.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/activepieces/refs/heads/main/capabilities/workflow-automation.yaml
tags:
- Activepieces
- Automation
- No-Code
- Workflow
- Integration
tools:
- description: List all automation flows in the Activepieces project
  hints:
    openWorld: true
    readOnly: true
  name: list-flows
- description: Create a new automation flow in Activepieces
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-flow
- description: Retrieve a specific automation flow by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-flow
- description: Delete an automation flow
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-flow
- description: List execution history for automation flows
  hints:
    openWorld: true
    readOnly: true
  name: list-flow-runs
- description: Get details of a specific flow execution run
  hints:
    openWorld: false
    readOnly: true
  name: get-flow-run
- description: List all app connections available in the project
  hints:
    openWorld: true
    readOnly: true
  name: list-connections
- description: List all Activepieces projects
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
---

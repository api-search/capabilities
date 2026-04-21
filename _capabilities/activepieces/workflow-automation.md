---
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
- no-code
- retrieve a specific automation flow by id
- list flows
- list flow execution runs
- create a new automation flow
- delete flow
- get flow run
- list execution history for automation flows
- creates automation workflows using the visual builder
- automation
- Developer
- activepieces
- integration
- list all automation flows in the activepieces project
- get details of a specific flow execution run
- list all activepieces projects
- delete an automation flow
- list connections
- build and monitor automation flows, manage connections, debug executions
- third-party app connections and piece management
- Operations Engineer
- mcp
- create a new automation flow in activepieces
- list app connections
- ai agents
- project management
- list automation flows
- workflow
- execution monitoring
- project, user, and organization administration
- open source
- app connection management
- monitors flow execution, manages connections, troubleshoots failures
- create flow
- builds custom integrations using the api and typescript pieces
- No Code Builder
- automation flow management
- list projects
- get flow
- list flow runs
- list all app connections available in the project
- workflow automation and flow orchestration
slug: workflow-automation
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

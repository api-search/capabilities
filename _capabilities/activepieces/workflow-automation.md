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
- create flow
- list projects
- builds custom integrations using the api and typescript pieces
- automation
- project management
- ai agents
- creates automation workflows using the visual builder
- app connection management
- mcp
- open source
- retrieve a specific automation flow by id
- delete an automation flow
- integration
- monitors flow execution, manages connections, troubleshoots failures
- create a new automation flow
- list flow runs
- delete flow
- list flows
- execution monitoring
- build and monitor automation flows, manage connections, debug executions
- Operations Engineer
- activepieces
- workflow
- list all activepieces projects
- workflow automation and flow orchestration
- list automation flows
- get details of a specific flow execution run
- list app connections
- Developer
- create a new automation flow in activepieces
- third-party app connections and piece management
- list all automation flows in the activepieces project
- list flow execution runs
- automation flow management
- No Code Builder
- list connections
- list all app connections available in the project
- project, user, and organization administration
- get flow run
- get flow
- no-code
- list execution history for automation flows
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

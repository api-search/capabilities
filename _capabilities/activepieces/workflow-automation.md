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
- create a new automation flow
- retrieve a specific automation flow by id
- automation flow management
- builds custom integrations using the api and typescript pieces
- delete an automation flow
- list all activepieces projects
- project management
- get flow run
- integration
- mcp
- list flows
- list all automation flows in the activepieces project
- No Code Builder
- build and monitor automation flows, manage connections, debug executions
- ai agents
- third-party app connections and piece management
- create a new automation flow in activepieces
- app connection management
- get details of a specific flow execution run
- list flow execution runs
- delete flow
- list execution history for automation flows
- project, user, and organization administration
- list automation flows
- execution monitoring
- monitors flow execution, manages connections, troubleshoots failures
- list app connections
- open source
- get flow
- list projects
- activepieces
- Operations Engineer
- workflow
- create flow
- Developer
- list flow runs
- list connections
- list all app connections available in the project
- workflow automation and flow orchestration
- creates automation workflows using the visual builder
- automation
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

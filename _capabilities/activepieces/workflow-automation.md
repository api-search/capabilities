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
- creates automation workflows using the visual builder
- list all automation flows in the activepieces project
- create flow
- get details of a specific flow execution run
- list all activepieces projects
- Developer
- delete flow
- project, user, and organization administration
- project management
- integration
- Operations Engineer
- automation
- automation flow management
- list flow execution runs
- monitors flow execution, manages connections, troubleshoots failures
- workflow
- ai agents
- list automation flows
- build and monitor automation flows, manage connections, debug executions
- list flows
- list flow runs
- list execution history for automation flows
- mcp
- list connections
- list projects
- get flow
- activepieces
- list all app connections available in the project
- create a new automation flow
- retrieve a specific automation flow by id
- create a new automation flow in activepieces
- delete an automation flow
- builds custom integrations using the api and typescript pieces
- get flow run
- no-code
- execution monitoring
- list app connections
- workflow automation and flow orchestration
- third-party app connections and piece management
- open source
- app connection management
- No Code Builder
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

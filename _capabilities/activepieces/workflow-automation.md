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
- project management
- list projects
- project, user, and organization administration
- app connection management
- list all activepieces projects
- get flow
- Operations Engineer
- list connections
- mcp
- list execution history for automation flows
- integration
- workflow
- build and monitor automation flows, manage connections, debug executions
- builds custom integrations using the api and typescript pieces
- execution monitoring
- get details of a specific flow execution run
- list flow execution runs
- activepieces
- No Code Builder
- open source
- ai agents
- get flow run
- list app connections
- delete flow
- create a new automation flow in activepieces
- retrieve a specific automation flow by id
- create flow
- automation
- create a new automation flow
- list all app connections available in the project
- Developer
- monitors flow execution, manages connections, troubleshoots failures
- creates automation workflows using the visual builder
- list flow runs
- no-code
- delete an automation flow
- third-party app connections and piece management
- workflow automation and flow orchestration
- list automation flows
- automation flow management
- list all automation flows in the activepieces project
- list flows
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

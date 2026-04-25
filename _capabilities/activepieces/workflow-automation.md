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
- list all automation flows in the activepieces project
- create a new automation flow in activepieces
- list connections
- mcp
- list app connections
- workflow automation and flow orchestration
- list all activepieces projects
- third-party app connections and piece management
- get flow
- list flows
- No Code Builder
- integration
- activepieces
- automation flow management
- list flow execution runs
- execution monitoring
- project management
- automation
- no-code
- retrieve a specific automation flow by id
- list projects
- list automation flows
- app connection management
- creates automation workflows using the visual builder
- get details of a specific flow execution run
- list execution history for automation flows
- project, user, and organization administration
- workflow
- list flow runs
- create a new automation flow
- create flow
- delete flow
- get flow run
- build and monitor automation flows, manage connections, debug executions
- monitors flow execution, manages connections, troubleshoots failures
- Operations Engineer
- ai agents
- delete an automation flow
- Developer
- list all app connections available in the project
- open source
- builds custom integrations using the api and typescript pieces
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

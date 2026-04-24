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
- integration
- create a new automation flow
- Operations Engineer
- list all automation flows in the activepieces project
- workflow automation and flow orchestration
- builds custom integrations using the api and typescript pieces
- create flow
- third-party app connections and piece management
- get flow run
- workflow
- creates automation workflows using the visual builder
- get flow
- list all activepieces projects
- create a new automation flow in activepieces
- list flow execution runs
- execution monitoring
- no-code
- list app connections
- delete an automation flow
- automation
- list automation flows
- No Code Builder
- automation flow management
- list execution history for automation flows
- activepieces
- list all app connections available in the project
- open source
- mcp
- get details of a specific flow execution run
- delete flow
- app connection management
- project management
- ai agents
- list projects
- retrieve a specific automation flow by id
- list flows
- monitors flow execution, manages connections, troubleshoots failures
- project, user, and organization administration
- Developer
- list connections
- list flow runs
- build and monitor automation flows, manage connections, debug executions
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

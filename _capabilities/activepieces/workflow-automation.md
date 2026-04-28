---
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
- list all automation flows in the activepieces project
- list flows
- create a new automation flow
- list flow runs
- delete an automation flow
- get details of a specific flow execution run
- activepieces
- workflow
- builds custom integrations using the api and typescript pieces
- third-party app connections and piece management
- list flow execution runs
- list all activepieces projects
- create a new automation flow in activepieces
- app connection management
- no-code
- Operations Engineer
- project management
- automation flow management
- delete flow
- list automation flows
- integration
- ai agents
- list connections
- list projects
- list all app connections available in the project
- monitors flow execution, manages connections, troubleshoots failures
- project, user, and organization administration
- build and monitor automation flows, manage connections, debug executions
- execution monitoring
- Developer
- creates automation workflows using the visual builder
- workflow automation and flow orchestration
- retrieve a specific automation flow by id
- open source
- get flow
- create flow
- get flow run
- mcp
- list execution history for automation flows
- No Code Builder
- automation
- list app connections
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

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
- list all activepieces projects
- list app connections
- integration
- list connections
- automation
- list automation flows
- workflow automation and flow orchestration
- create flow
- get flow
- create a new automation flow in activepieces
- creates automation workflows using the visual builder
- Developer
- delete an automation flow
- activepieces
- monitors flow execution, manages connections, troubleshoots failures
- third-party app connections and piece management
- list all app connections available in the project
- list flow runs
- list flows
- build and monitor automation flows, manage connections, debug executions
- list all automation flows in the activepieces project
- list projects
- list flow execution runs
- get details of a specific flow execution run
- open source
- mcp
- ai agents
- builds custom integrations using the api and typescript pieces
- list execution history for automation flows
- retrieve a specific automation flow by id
- create a new automation flow
- no-code
- No Code Builder
- execution monitoring
- project, user, and organization administration
- app connection management
- get flow run
- project management
- workflow
- delete flow
- Operations Engineer
- automation flow management
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

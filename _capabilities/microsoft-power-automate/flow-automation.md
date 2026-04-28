---
categories:
- automation
consumed_apis:
- management-api
description: Workflow capability for managing Power Automate flows, environments, and connectors. Used by automation engineers and platform administrators.
layout: capability
name: Microsoft Power Automate Flow Automation
operations:
- description: List all environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: List flows
  method: GET
  name: list-flows
  path: /v1/flows
- description: Create a flow
  method: POST
  name: create-flow
  path: /v1/flows
- description: Get flow details
  method: GET
  name: get-flow
  path: /v1/flows
- description: Update a flow
  method: PATCH
  name: update-flow
  path: /v1/flows
- description: Delete a flow
  method: DELETE
  name: delete-flow
  path: /v1/flows
- description: List connectors
  method: GET
  name: list-connectors
  path: /v1/connectors
personas: []
provider_name: Microsoft Power Automate
provider_slug: microsoft-power-automate
search_terms:
- manage flows, environments, and connectors
- Automation Engineer
- integration
- delete a flow
- get details of a specific flow
- automation
- creates and manages automation flows
- create flow
- get flow
- Platform Administrator
- update a flow's properties
- connector management
- power platform
- update flow
- get flow details
- low-code
- list flows
- list all power automate environments
- stop/deactivate a flow
- business process
- environment management
- manages environments, connectors, and permissions
- start/activate a flow
- list environments
- list connectors
- turn on flow
- list all environments
- get details of a specific connector
- managing environments and available connectors
- create a new automation flow
- microsoft
- create a flow
- get connector
- list available connectors in an environment
- rpa
- flow management
- flow lifecycle management
- turn off flow
- workflow
- microsoft power automate
- delete flow
- creating, running, and managing automation flows
- update a flow
- list flows in an environment
slug: flow-automation
tags:
- Microsoft Power Automate
- Automation
- Flow Management
- Low-Code
tools:
- description: List all Power Automate environments
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: List flows in an environment
  hints:
    openWorld: true
    readOnly: true
  name: list-flows
- description: Create a new automation flow
  hints:
    readOnly: false
  name: create-flow
- description: Get details of a specific flow
  hints:
    readOnly: true
  name: get-flow
- description: Update a flow's properties
  hints:
    readOnly: false
  name: update-flow
- description: Delete a flow
  hints:
    destructive: true
  name: delete-flow
- description: Start/activate a flow
  hints:
    readOnly: false
  name: turn-on-flow
- description: Stop/deactivate a flow
  hints:
    readOnly: false
  name: turn-off-flow
- description: List available connectors in an environment
  hints:
    readOnly: true
  name: list-connectors
- description: Get details of a specific connector
  hints:
    readOnly: true
  name: get-connector
---

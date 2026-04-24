---
consumed_apis:
- appmixer
description: Workflow capability for managing embedded automation within SaaS products using Appmixer. Combines flow lifecycle management, user provisioning, data storage, and human-in-the-loop task handling into a unified workflow for SaaS developers embedding white-labeled automation into their products.
layout: capability
name: Appmixer Embedded Automation
operations:
- description: List all automation flows
  method: GET
  name: list-flows
  path: /v1/flows
- description: Create a new automation flow
  method: POST
  name: create-flow
  path: /v1/flows
- description: List automation users
  method: GET
  name: list-users
  path: /v1/users
- description: List pending people tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
personas: []
provider_name: Appmixer
provider_slug: appmixer
search_terms:
- end-to-end workflow for embedding automation in saas products
- automation flow lifecycle
- create a new automation flow
- starts/runs an automation flow to execute its workflow
- creating, running, and managing automation flows
- list automation users
- list all automation flows
- create flow
- appmixer
- lists all automation workflows configured in appmixer
- list tasks
- user management for embedded automation
- lists human-in-the-loop tasks waiting for user review or approval
- provisioning and managing automation platform users
- automation
- list automation flows
- agentic
- run automation flow
- low-code
- list pending tasks
- embedded ipaas
- approve task
- approves or completes a pending human-in-the-loop task in an automation flow
- integrations
- creates a new automation flow in appmixer for embedding in a product
- persisting and retrieving workflow state and data
- create automation flow
- product user interacting with embedded automation workflows
- saas
- list flows
- list pending people tasks
- lists users who have access to the embedded automation platform
- developer embedding white-labeled automation into a product
- workflows
- human-in-the-loop tasks
- managing tasks requiring human review or approval
- list users
slug: embedded-automation
tags:
- Appmixer
- Automation
- Embedded iPaaS
- Workflows
- SaaS
tools:
- description: Lists all automation workflows configured in Appmixer
  hints:
    idempotent: true
    readOnly: true
  name: list-automation-flows
- description: Creates a new automation flow in Appmixer for embedding in a product
  hints:
    destructive: false
    readOnly: false
  name: create-automation-flow
- description: Starts/runs an automation flow to execute its workflow
  hints:
    destructive: false
    readOnly: false
  name: run-automation-flow
- description: Lists human-in-the-loop tasks waiting for user review or approval
  hints:
    idempotent: true
    readOnly: true
  name: list-pending-tasks
- description: Approves or completes a pending human-in-the-loop task in an automation flow
  hints:
    destructive: false
    readOnly: false
  name: approve-task
- description: Lists users who have access to the embedded automation platform
  hints:
    idempotent: true
    readOnly: true
  name: list-automation-users
---

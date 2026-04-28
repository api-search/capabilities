---
categories:
- automation
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
- list tasks
- approves or completes a pending human-in-the-loop task in an automation flow
- developer embedding white-labeled automation into a product
- automation
- list pending people tasks
- list automation flows
- create flow
- list automation users
- list all automation flows
- starts/runs an automation flow to execute its workflow
- persisting and retrieving workflow state and data
- list flows
- low-code
- agentic
- lists users who have access to the embedded automation platform
- creates a new automation flow in appmixer for embedding in a product
- managing tasks requiring human review or approval
- automation flow lifecycle
- lists human-in-the-loop tasks waiting for user review or approval
- workflows
- user management for embedded automation
- human-in-the-loop tasks
- list pending tasks
- embedded ipaas
- end-to-end workflow for embedding automation in saas products
- integrations
- saas
- list users
- create a new automation flow
- approve task
- create automation flow
- product user interacting with embedded automation workflows
- provisioning and managing automation platform users
- lists all automation workflows configured in appmixer
- run automation flow
- appmixer
- creating, running, and managing automation flows
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

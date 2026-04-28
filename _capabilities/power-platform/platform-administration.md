---
categories: []
consumed_apis:
- power-platform-api
description: Unified workflow for Power Platform administrators to manage environments, deploy applications, monitor flow runs, and govern licensing across the tenant.
layout: capability
name: Microsoft Power Platform Administration
operations:
- description: List all environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: Get environment details
  method: GET
  name: get-environment
  path: /v1/environments/{environmentId}
- description: Delete an environment
  method: DELETE
  name: delete-environment
  path: /v1/environments/{environmentId}
- description: List application packages for an environment
  method: GET
  name: list-packages
  path: /v1/environments/{environmentId}/packages
- description: List flow runs for an environment
  method: GET
  name: list-flow-runs
  path: /v1/environments/{environmentId}/flow-runs
- description: List all billing policies
  method: GET
  name: list-billing-policies
  path: /v1/billing-policies
- description: Create a billing policy
  method: POST
  name: create-billing-policy
  path: /v1/billing-policies
personas: []
provider_name: Microsoft Power Platform APIs
provider_slug: power-platform
search_terms:
- create a new billing policy linking azure subscription
- flow run monitoring
- create billing policy
- list all power platform environments in the tenant
- single environment operations
- list billing policies for the tenant
- dataverse
- install an application package in an environment
- copilot studio
- billing policy management
- power platform
- list flow runs
- application package management
- get install status
- business applications
- low-code
- list all billing policies
- list power automate flow runs by workflow id
- update an existing billing policy
- environment management
- power pages
- list tenant packages
- delete environment
- get details for a specific power platform environment
- administration
- list environments
- delete a power platform environment
- list billing policies
- list all environments
- check the installation status of an application package
- delete an environment
- list application packages
- microsoft
- install application package
- update billing policy
- list application packages available in an environment
- no-code
- get environment details
- list packages
- get environment
- governance
- list installable application packages for the tenant
- list application packages for an environment
- create a billing policy
- get billing policy
- get details for a specific billing policy
- list flow runs for an environment
slug: platform-administration
tags:
- Microsoft
- Power Platform
- Administration
- Governance
tools:
- description: List all Power Platform environments in the tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: Get details for a specific Power Platform environment
  hints:
    idempotent: true
    readOnly: true
  name: get-environment
- description: Delete a Power Platform environment
  hints:
    destructive: true
    idempotent: true
  name: delete-environment
- description: List application packages available in an environment
  hints:
    readOnly: true
  name: list-application-packages
- description: Install an application package in an environment
  hints:
    readOnly: false
  name: install-application-package
- description: Check the installation status of an application package
  hints:
    readOnly: true
  name: get-install-status
- description: List installable application packages for the tenant
  hints:
    readOnly: true
  name: list-tenant-packages
- description: List Power Automate flow runs by workflow ID
  hints:
    readOnly: true
  name: list-flow-runs
- description: List billing policies for the tenant
  hints:
    readOnly: true
  name: list-billing-policies
- description: Create a new billing policy linking Azure subscription
  hints:
    readOnly: false
  name: create-billing-policy
- description: Get details for a specific billing policy
  hints:
    readOnly: true
  name: get-billing-policy
- description: Update an existing billing policy
  hints:
    idempotent: true
    readOnly: false
  name: update-billing-policy
---

---
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
- copilot studio
- list billing policies
- no-code
- delete environment
- list all billing policies
- administration
- power pages
- get install status
- dataverse
- get details for a specific billing policy
- power platform
- update an existing billing policy
- list packages
- environment management
- single environment operations
- get environment details
- list billing policies for the tenant
- list all environments
- microsoft
- delete a power platform environment
- low-code
- list application packages
- create a billing policy
- install an application package in an environment
- billing policy management
- list power automate flow runs by workflow id
- list application packages for an environment
- create billing policy
- get environment
- get details for a specific power platform environment
- application package management
- flow run monitoring
- list installable application packages for the tenant
- list environments
- create a new billing policy linking azure subscription
- delete an environment
- install application package
- update billing policy
- get billing policy
- list flow runs for an environment
- list tenant packages
- list flow runs
- list all power platform environments in the tenant
- governance
- business applications
- check the installation status of an application package
- list application packages available in an environment
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

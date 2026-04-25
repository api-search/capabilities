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
- update an existing billing policy
- list application packages
- copilot studio
- single environment operations
- billing policy management
- governance
- list packages
- power platform
- get details for a specific billing policy
- list application packages available in an environment
- list tenant packages
- get environment
- create a billing policy
- environment management
- list flow runs for an environment
- list environments
- update billing policy
- list flow runs
- install an application package in an environment
- application package management
- create billing policy
- flow run monitoring
- microsoft
- dataverse
- power pages
- get details for a specific power platform environment
- delete environment
- get install status
- check the installation status of an application package
- delete an environment
- low-code
- get environment details
- list billing policies
- list all power platform environments in the tenant
- business applications
- list billing policies for the tenant
- list all billing policies
- no-code
- list application packages for an environment
- list all environments
- delete a power platform environment
- administration
- get billing policy
- list installable application packages for the tenant
- list power automate flow runs by workflow id
- create a new billing policy linking azure subscription
- install application package
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

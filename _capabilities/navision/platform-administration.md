---
categories:
- automation
consumed_apis:
- admin-center
- automation
description: Unified workflow for administering Dynamics 365 Business Central combining the Administration Center API for environment management with the Automation API for company setup, extensions, users, and permissions. Used by platform administrators and IT teams.
layout: capability
name: Dynamics NAV Platform Administration
operations:
- description: List all environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: Get environment details
  method: GET
  name: get-environment
  path: /v1/environments/{environmentName}
- description: Create a new environment
  method: PUT
  name: create-environment
  path: /v1/environments/{environmentName}
- description: Delete an environment
  method: DELETE
  name: delete-environment
  path: /v1/environments/{environmentName}
- description: List automation companies
  method: GET
  name: list-companies
  path: /v1/companies
- description: List extensions
  method: GET
  name: list-extensions
  path: /v1/extensions
- description: List users
  method: GET
  name: list-users
  path: /v1/users
- description: List permission sets
  method: GET
  name: list-permission-sets
  path: /v1/permission-sets
- description: Get allowed quotas
  method: GET
  name: get-quotas
  path: /v1/quotas
personas: []
provider_name: Microsoft Dynamics NAV
provider_slug: navision
search_terms:
- list companies
- uninstall extension
- microsoft
- list scheduled background jobs
- dynamics nav
- get environment settings
- install extension
- update user properties
- extension management
- list installed apps
- list environments
- get a user by id
- list features
- restore environment
- storage quotas
- create environment
- get environment
- list installed apps in an environment
- restore an environment from a point in time
- finance
- list business central users
- administration
- create a new environment
- get environment storage usage
- copy an environment
- permission sets
- inventory
- list security groups
- list scheduled jobs
- create automation company
- install an extension
- list automation companies
- delete a company
- navision
- company management
- list rapidstart configuration packages
- copy environment
- business central
- get environment details
- delete environment
- single environment
- list extensions
- get user
- business management
- get allowed quotas and limits
- list users
- update user
- list permission sets
- delete an environment
- get allowed quotas
- delete automation company
- get scheduled upgrade information
- create a new company
- erp
- get environment storage
- get scheduled upgrade
- dynamics 365
- list all business central environments
- uninstall an extension
- environment management
- list all environments
- list published extensions
- list configuration packages
- automation
- get quotas
- user management
slug: platform-administration
tags:
- Business Central
- Dynamics 365
- Administration
- Automation
- Environment Management
- User Management
tools:
- description: List all Business Central environments
  hints:
    idempotent: true
    readOnly: true
  name: list-all-environments
- description: Get environment details
  hints:
    idempotent: true
    readOnly: true
  name: get-environment
- description: Create a new environment
  hints:
    readOnly: false
  name: create-environment
- description: Delete an environment
  hints:
    destructive: true
    readOnly: false
  name: delete-environment
- description: Copy an environment
  hints:
    readOnly: false
  name: copy-environment
- description: Restore an environment from a point in time
  hints:
    readOnly: false
  name: restore-environment
- description: List installed apps in an environment
  hints:
    idempotent: true
    readOnly: true
  name: list-installed-apps
- description: Get environment settings
  hints:
    idempotent: true
    readOnly: true
  name: get-environment-settings
- description: Get environment storage usage
  hints:
    idempotent: true
    readOnly: true
  name: get-environment-storage
- description: Get scheduled upgrade information
  hints:
    idempotent: true
    readOnly: true
  name: get-scheduled-upgrade
- description: Get allowed quotas and limits
  hints:
    idempotent: true
    readOnly: true
  name: get-quotas
- description: List automation companies
  hints:
    idempotent: true
    readOnly: true
  name: list-companies
- description: Create a new company
  hints:
    readOnly: false
  name: create-automation-company
- description: Delete a company
  hints:
    destructive: true
    readOnly: false
  name: delete-automation-company
- description: List published extensions
  hints:
    idempotent: true
    readOnly: true
  name: list-extensions
- description: Install an extension
  hints:
    readOnly: false
  name: install-extension
- description: Uninstall an extension
  hints:
    destructive: true
    readOnly: false
  name: uninstall-extension
- description: List Business Central users
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: Get a user by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-user
- description: Update user properties
  hints:
    idempotent: true
    readOnly: false
  name: update-user
- description: List permission sets
  hints:
    idempotent: true
    readOnly: true
  name: list-permission-sets
- description: List features
  hints:
    idempotent: true
    readOnly: true
  name: list-features
- description: List security groups
  hints:
    idempotent: true
    readOnly: true
  name: list-security-groups
- description: List RapidStart configuration packages
  hints:
    idempotent: true
    readOnly: true
  name: list-configuration-packages
- description: List scheduled background jobs
  hints:
    idempotent: true
    readOnly: true
  name: list-scheduled-jobs
---

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
- business central
- get environment settings
- install an extension
- automation
- dynamics 365
- list configuration packages
- get quotas
- get environment storage
- get allowed quotas and limits
- finance
- get scheduled upgrade information
- dynamics nav
- create a new company
- list extensions
- list security groups
- erp
- environment management
- inventory
- uninstall an extension
- list all business central environments
- get environment storage usage
- restore an environment from a point in time
- update user
- business management
- uninstall extension
- restore environment
- list business central users
- delete environment
- delete a company
- administration
- list environments
- list features
- list all environments
- extension management
- list automation companies
- list users
- get allowed quotas
- list installed apps
- create automation company
- delete automation company
- create a new environment
- copy an environment
- list published extensions
- update user properties
- list rapidstart configuration packages
- get scheduled upgrade
- get user
- microsoft
- get environment details
- get a user by id
- install extension
- list scheduled jobs
- get environment
- storage quotas
- copy environment
- list scheduled background jobs
- single environment
- create environment
- list companies
- list permission sets
- user management
- permission sets
- navision
- list installed apps in an environment
- delete an environment
- company management
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

---
categories:
- payroll-hr
consumed_apis:
- bettercloud
description: Unified SaaS user lifecycle management workflow combining user management, group management, workflow automation, and audit logging. Used by IT administrators and security teams to manage employee access throughout the full SaaS application lifecycle from onboarding to offboarding.
layout: capability
name: BetterCloud SaaS Lifecycle Management
operations:
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
- description: Get user details
  method: GET
  name: get-user
  path: /v1/users/{id}
- description: Update user attributes
  method: PATCH
  name: update-user
  path: /v1/users/{id}
- description: Suspend a user
  method: POST
  name: suspend-user
  path: /v1/users/{id}/suspend
- description: Deprovision a user
  method: POST
  name: deprovision-user
  path: /v1/users/{id}/deprovision
- description: List all groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create a group
  method: POST
  name: create-group
  path: /v1/groups
- description: List all workflows
  method: GET
  name: list-workflows
  path: /v1/workflows
- description: Run a workflow
  method: POST
  name: run-workflow
  path: /v1/workflows/{id}/run
- description: List audit events
  method: GET
  name: list-events
  path: /v1/events
personas:
- description: IT admin managing SaaS access and user lifecycle
  id: it-administrator
  name: IT Administrator
- description: Security team member managing compliance and access policies
  id: security-engineer
  name: Security Engineer
provider_name: BetterCloud
provider_slug: bettercloud
search_terms:
- workflow automation for it operations
- bettercloud
- user discovery and management
- list audit events for compliance investigation
- onboarding, management, and offboarding of users across saas
- run a workflow
- security engineer
- security team member managing compliance and access policies
- automation
- list all connected saas application integrations
- audit event log
- list all workflows
- automation workflow management
- create group
- suspend a departing or at-risk user across all saas apps
- compliance
- list all automation workflows
- user onboarding and offboarding across saas applications
- get full details for a specific user including saas access
- saas application connectivity
- list users across all connected saas applications
- list all groups from connected directory services
- update user attributes
- list audit events
- list workflows
- onboarding
- update user
- add a user to a group
- enterprise
- security
- list all users
- workflows
- individual user operations
- suspend user
- create a group
- list users
- audit trails and policy enforcement
- group management
- it administrator
- run workflow
- list integrations
- get user
- get user details
- it operations
- add group member
- list all groups
- it admin managing saas access and user lifecycle
- suspend a user
- deprovision user
- list groups
- deprovision a user
- fully deprovision a user removing all saas application access
- offboarding
- trigger workflow execution
- list events
- trigger a workflow for a set of users (e.g., offboarding)
- user lifecycle
- saas management
- update user attributes like department or title
slug: saas-lifecycle-management
tags:
- BetterCloud
- Saas Management
- User Lifecycle
- Onboarding
- Offboarding
- Compliance
tools:
- description: List users across all connected SaaS applications
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Get full details for a specific user including SaaS access
  hints:
    readOnly: true
  name: get-user
- description: Update user attributes like department or title
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-user
- description: Suspend a departing or at-risk user across all SaaS apps
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: suspend-user
- description: Fully deprovision a user removing all SaaS application access
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deprovision-user
- description: List all groups from connected directory services
  hints:
    readOnly: true
  name: list-groups
- description: Add a user to a group
  hints:
    destructive: false
    readOnly: false
  name: add-group-member
- description: List all automation workflows
  hints:
    readOnly: true
  name: list-workflows
- description: Trigger a workflow for a set of users (e.g., offboarding)
  hints:
    destructive: false
    readOnly: false
  name: run-workflow
- description: List audit events for compliance investigation
  hints:
    readOnly: true
  name: list-events
- description: List all connected SaaS application integrations
  hints:
    readOnly: true
  name: list-integrations
---

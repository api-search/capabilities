---
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
- user onboarding and offboarding across saas applications
- create group
- deprovision a user
- group management
- get user
- list audit events
- offboarding
- fully deprovision a user removing all saas application access
- user lifecycle
- audit event log
- list workflows
- user discovery and management
- list all workflows
- onboarding, management, and offboarding of users across saas
- saas application connectivity
- suspend user
- workflow automation for it operations
- add a user to a group
- update user attributes like department or title
- update user
- list all automation workflows
- automation
- security team member managing compliance and access policies
- compliance
- audit trails and policy enforcement
- it admin managing saas access and user lifecycle
- update user attributes
- suspend a departing or at-risk user across all saas apps
- list all connected saas application integrations
- run workflow
- get user details
- list audit events for compliance investigation
- deprovision user
- list all users
- suspend a user
- enterprise
- run a workflow
- saas management
- trigger workflow execution
- list users across all connected saas applications
- add group member
- list all groups from connected directory services
- security
- onboarding
- bettercloud
- individual user operations
- create a group
- it operations
- list events
- it administrator
- workflows
- list all groups
- automation workflow management
- list groups
- list integrations
- trigger a workflow for a set of users (e.g., offboarding)
- get full details for a specific user including saas access
- list users
- security engineer
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

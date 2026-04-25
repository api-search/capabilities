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
- add group member
- user discovery and management
- enterprise
- user onboarding and offboarding across saas applications
- list all groups
- create a group
- automation
- it operations
- user lifecycle
- compliance
- update user attributes like department or title
- update user
- create group
- list users across all connected saas applications
- security
- get user
- list workflows
- saas application connectivity
- list events
- add a user to a group
- trigger workflow execution
- group management
- individual user operations
- run a workflow
- suspend a departing or at-risk user across all saas apps
- fully deprovision a user removing all saas application access
- offboarding
- security engineer
- bettercloud
- run workflow
- get full details for a specific user including saas access
- workflow automation for it operations
- list users
- update user attributes
- list all automation workflows
- list all users
- automation workflow management
- it administrator
- suspend user
- it admin managing saas access and user lifecycle
- saas management
- list all connected saas application integrations
- security team member managing compliance and access policies
- audit event log
- get user details
- suspend a user
- list audit events
- deprovision a user
- list groups
- list all workflows
- trigger a workflow for a set of users (e.g., offboarding)
- list audit events for compliance investigation
- list integrations
- onboarding
- audit trails and policy enforcement
- list all groups from connected directory services
- workflows
- onboarding, management, and offboarding of users across saas
- deprovision user
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

---
categories:
- compliance
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
- list audit events for compliance investigation
- run a workflow
- suspend a departing or at-risk user across all saas apps
- add a user to a group
- user onboarding and offboarding across saas applications
- it admin managing saas access and user lifecycle
- list users
- it operations
- security
- enterprise
- get user
- list events
- list audit events
- user lifecycle
- saas application connectivity
- user discovery and management
- trigger a workflow for a set of users (e.g., offboarding)
- create group
- offboarding
- update user
- fully deprovision a user removing all saas application access
- add group member
- saas management
- get user details
- list workflows
- workflow automation for it operations
- deprovision a user
- audit event log
- list all connected saas application integrations
- it administrator
- suspend user
- individual user operations
- group management
- trigger workflow execution
- get full details for a specific user including saas access
- create a group
- security engineer
- list integrations
- list all users
- onboarding
- automation workflow management
- bettercloud
- update user attributes like department or title
- update user attributes
- audit trails and policy enforcement
- list all groups from connected directory services
- list all automation workflows
- security team member managing compliance and access policies
- list users across all connected saas applications
- compliance
- run workflow
- list all workflows
- list all groups
- deprovision user
- automation
- onboarding, management, and offboarding of users across saas
- workflows
- suspend a user
- list groups
slug: saas-lifecycle-management
source_filename: saas-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: BetterCloud SaaS Lifecycle Management\n  description: >-\n    Unified SaaS user lifecycle management workflow combining user management,\n    group management, workflow automation, and audit logging. Used by IT\n    administrators and security teams to manage employee access throughout\n    the full SaaS application lifecycle from onboarding to offboarding.\n  tags:\n    - BetterCloud\n    - Saas Management\n    - User Lifecycle\n    - Onboarding\n    - Offboarding\n    - Compliance\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BETTERCLOUD_API_KEY: BETTERCLOUD_API_KEY\n\ncapability:\n  consumes:\n    - import: bettercloud\n      location: ./shared/bettercloud.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: bettercloud-lifecycle-api\n      description: Unified REST API for BetterCloud SaaS lifecycle management.\n      resources:\n        - path: /v1/users\n\
  \          name: users\n          description: User discovery and management\n          operations:\n            - method: GET\n              name: list-users\n              description: List all users\n              call: \"bettercloud.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{id}\n          name: user\n          description: Individual user operations\n          operations:\n            - method: GET\n              name: get-user\n              description: Get user details\n              call: \"bettercloud.get-user\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-user\n              description: Update user attributes\n              call: \"bettercloud.update-user\"\n              with:\n                id: \"rest.id\"\n  \
  \            outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{id}/suspend\n          name: user-suspend\n          description: Suspend user\n          operations:\n            - method: POST\n              name: suspend-user\n              description: Suspend a user\n              call: \"bettercloud.suspend-user\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{id}/deprovision\n          name: user-deprovision\n          description: Deprovision user\n          operations:\n            - method: POST\n              name: deprovision-user\n              description: Deprovision a user\n              call: \"bettercloud.deprovision-user\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \        - path: /v1/groups\n          name: groups\n          description: Group management\n          operations:\n            - method: GET\n              name: list-groups\n              description: List all groups\n              call: \"bettercloud.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-group\n              description: Create a group\n              call: \"bettercloud.create-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows\n          name: workflows\n          description: Automation workflow management\n          operations:\n            - method: GET\n              name: list-workflows\n              description: List all workflows\n              call: \"bettercloud.list-workflows\"\n              outputParameters:\n                - type: object\n           \
  \       mapping: \"$.\"\n        - path: /v1/workflows/{id}/run\n          name: workflow-run\n          description: Trigger workflow execution\n          operations:\n            - method: POST\n              name: run-workflow\n              description: Run a workflow\n              call: \"bettercloud.run-workflow\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: Audit event log\n          operations:\n            - method: GET\n              name: list-events\n              description: List audit events\n              call: \"bettercloud.list-events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: bettercloud-lifecycle-mcp\n      transport: http\n      description: MCP server for AI-assisted BetterCloud\
  \ SaaS lifecycle management.\n      tools:\n        - name: list-users\n          description: List users across all connected SaaS applications\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"bettercloud.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: Get full details for a specific user including SaaS access\n          hints:\n            readOnly: true\n          call: \"bettercloud.get-user\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-user\n          description: Update user attributes like department or title\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"bettercloud.update-user\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: suspend-user\n          description: Suspend a departing or at-risk user across all SaaS apps\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"bettercloud.suspend-user\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deprovision-user\n          description: Fully deprovision a user removing all SaaS application access\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"bettercloud.deprovision-user\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: List all groups from connected directory services\n          hints:\n    \
  \        readOnly: true\n          call: \"bettercloud.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-group-member\n          description: Add a user to a group\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"bettercloud.add-group-member\"\n          with:\n            id: \"tools.group_id\"\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workflows\n          description: List all automation workflows\n          hints:\n            readOnly: true\n          call: \"bettercloud.list-workflows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-workflow\n          description: Trigger a workflow for a set of users (e.g., offboarding)\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n          call: \"bettercloud.run-workflow\"\n          with:\n            id: \"tools.workflow_id\"\n            user_ids: \"tools.user_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-events\n          description: List audit events for compliance investigation\n          hints:\n            readOnly: true\n          call: \"bettercloud.list-events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-integrations\n          description: List all connected SaaS application integrations\n          hints:\n            readOnly: true\n          call: \"bettercloud.list-integrations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bettercloud/refs/heads/main/capabilities/saas-lifecycle-management.yaml
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

---
categories:
- compliance
consumed_apis: []
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
- list events
- security engineer
- run workflow
- deprovision a user
- list all connected saas application integrations
- update user attributes
- bettercloud
- add group member
- onboarding, management, and offboarding of users across saas
- suspend user
- audit trails and policy enforcement
- trigger workflow execution
- saas management
- it administrator
- compliance
- security
- list all users
- deprovision user
- enterprise
- list all groups
- user onboarding and offboarding across saas applications
- it operations
- get full details for a specific user including saas access
- individual user operations
- it admin managing saas access and user lifecycle
- saas application connectivity
- list integrations
- group management
- list audit events for compliance investigation
- onboarding
- list all automation workflows
- trigger a workflow for a set of users (e.g., offboarding)
- list workflows
- workflows
- update user
- add a user to a group
- get user
- user discovery and management
- suspend a user
- security team member managing compliance and access policies
- automation workflow management
- list all workflows
- fully deprovision a user removing all saas application access
- update user attributes like department or title
- list users
- suspend a departing or at-risk user across all saas apps
- user lifecycle
- get user details
- list audit events
- list groups
- list all groups from connected directory services
- audit event log
- list users across all connected saas applications
- offboarding
- create group
- run a workflow
- workflow automation for it operations
- create a group
- automation
slug: saas-lifecycle-management
source_filename: saas-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: BetterCloud SaaS Lifecycle Management\n  description: Unified SaaS user lifecycle management workflow combining user management, group management, workflow automation,\n    and audit logging. Used by IT administrators and security teams to manage employee access throughout the full SaaS application\n    lifecycle from onboarding to offboarding.\n  tags:\n  - BetterCloud\n  - Saas Management\n  - User Lifecycle\n  - Onboarding\n  - Offboarding\n  - Compliance\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BETTERCLOUD_API_KEY: BETTERCLOUD_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: bettercloud\n    baseUri: https://api.bettercloud.com/v1\n    description: BetterCloud Platform API\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{BETTERCLOUD_API_KEY}}'\n      placement: header\n    resources:\n    - name: users\n      path: /users\n      description:\
  \ SaaS user management\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        - name: email\n          in: query\n          type: string\n          required: false\n          description: Filter by email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-user\n        method: GET\n        description: Get a user by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n      - name: update-user\n        method: PATCH\n        description: Update user attributes\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            department: '{{tools.department}}'\n            title: '{{tools.title}}'\n      - name: suspend-user\n        method: POST\n        description: Suspend a user\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deprovision-user\n        method: POST\n        description: Deprovision\
  \ a user\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      description: Group management\n      operations:\n      - name: list-groups\n        method: GET\n        description: List all groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: get-group\n        method: GET\n        description: Get a group by ID\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n          description: Group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-group\n        method: DELETE\n        description: Delete a group\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-group-members\n        method: GET\n        description: List members of a group\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: add-group-member\n        method: POST\n        description: Add a user to a group\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            user_id: '{{tools.user_id}}'\n    - name: workflows\n      path: /workflows\n      description: Automation workflows\n      operations:\n      - name: list-workflows\n        method: GET\n        description: List all workflows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workflow\n        method: POST\n        description: Create a new workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            trigger_type: '{{tools.trigger_type}}'\n      - name: get-workflow\n        method: GET\n        description: Get a workflow by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Workflow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: run-workflow\n        method: POST\n        description: Trigger a workflow execution\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Workflow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            user_ids: '{{tools.user_ids}}'\n\
  \    - name: events\n      path: /events\n      description: Audit events and activity logs\n      operations:\n      - name: list-events\n        method: GET\n        description: List audit events\n        inputParameters:\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start date\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End date\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Event type filter\n        - name: user_id\n          in: query\n          type: string\n          required: false\n          description: Filter by user ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrations\n      path: /integrations\n      description: SaaS application integrations\n      operations:\n\
  \      - name: list-integrations\n        method: GET\n        description: List all configured integrations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bettercloud-lifecycle-api\n    description: Unified REST API for BetterCloud SaaS lifecycle management.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User discovery and management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users\n        call: bettercloud.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{id}\n      name: user\n      description: Individual user operations\n      operations:\n      - method: GET\n        name: get-user\n        description: Get user details\n        call: bettercloud.get-user\n        with:\n          id: rest.id\n     \
  \   outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-user\n        description: Update user attributes\n        call: bettercloud.update-user\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{id}/suspend\n      name: user-suspend\n      description: Suspend user\n      operations:\n      - method: POST\n        name: suspend-user\n        description: Suspend a user\n        call: bettercloud.suspend-user\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{id}/deprovision\n      name: user-deprovision\n      description: Deprovision user\n      operations:\n      - method: POST\n        name: deprovision-user\n        description: Deprovision a user\n        call: bettercloud.deprovision-user\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Group management\n      operations:\n      - method: GET\n        name: list-groups\n        description: List all groups\n        call: bettercloud.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create a group\n        call: bettercloud.create-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows\n      name: workflows\n      description: Automation workflow management\n      operations:\n      - method: GET\n        name: list-workflows\n        description: List all workflows\n        call: bettercloud.list-workflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{id}/run\n      name: workflow-run\n      description: Trigger workflow execution\n      operations:\n\
  \      - method: POST\n        name: run-workflow\n        description: Run a workflow\n        call: bettercloud.run-workflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Audit event log\n      operations:\n      - method: GET\n        name: list-events\n        description: List audit events\n        call: bettercloud.list-events\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: bettercloud-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted BetterCloud SaaS lifecycle management.\n    tools:\n    - name: list-users\n      description: List users across all connected SaaS applications\n      hints:\n        readOnly: true\n        openWorld: true\n      call: bettercloud.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-user\n      description: Get full details for a specific user including SaaS access\n      hints:\n        readOnly: true\n      call: bettercloud.get-user\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-user\n      description: Update user attributes like department or title\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: bettercloud.update-user\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: suspend-user\n      description: Suspend a departing or at-risk user across all SaaS apps\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: bettercloud.suspend-user\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deprovision-user\n      description: Fully deprovision a user\
  \ removing all SaaS application access\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: bettercloud.deprovision-user\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List all groups from connected directory services\n      hints:\n        readOnly: true\n      call: bettercloud.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-group-member\n      description: Add a user to a group\n      hints:\n        readOnly: false\n        destructive: false\n      call: bettercloud.add-group-member\n      with:\n        id: tools.group_id\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workflows\n      description: List all automation workflows\n      hints:\n        readOnly: true\n      call: bettercloud.list-workflows\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: run-workflow\n      description: Trigger a workflow for a set of users (e.g., offboarding)\n      hints:\n        readOnly: false\n        destructive: false\n      call: bettercloud.run-workflow\n      with:\n        id: tools.workflow_id\n        user_ids: tools.user_ids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-events\n      description: List audit events for compliance investigation\n      hints:\n        readOnly: true\n      call: bettercloud.list-events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-integrations\n      description: List all connected SaaS application integrations\n      hints:\n        readOnly: true\n      call: bettercloud.list-integrations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

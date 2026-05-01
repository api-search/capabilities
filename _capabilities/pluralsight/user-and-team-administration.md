---
api_specs:
- filename: user-management.yml
  format: yaml
  label: pluralsight-user-management
  slug: pluralsight-user-management
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/user-management.yml
- filename: teams.yml
  format: yaml
  label: pluralsight-teams
  slug: pluralsight-teams
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/teams.yml
- filename: licensing-rest.yml
  format: yaml
  label: pluralsight-licensing-rest
  slug: pluralsight-licensing-rest
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/licensing-rest.yml
- filename: plan-info.yml
  format: yaml
  label: pluralsight-plan-info
  slug: pluralsight-plan-info
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/plan-info.yml
- filename: flow-users.yml
  format: yaml
  label: pluralsight-flow-users
  slug: pluralsight-flow-users
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/flow-users.yml
- filename: flow-teams.yml
  format: yaml
  label: pluralsight-flow-teams
  slug: pluralsight-flow-teams
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/flow-teams.yml
- filename: flow-integrations.yml
  format: yaml
  label: pluralsight-flow-integrations
  slug: pluralsight-flow-integrations
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/flow-integrations.yml
- filename: flow-repos.yml
  format: yaml
  label: pluralsight-flow-repos
  slug: pluralsight-flow-repos
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/flow-repos.yml
categories: []
consumed_apis:
- pluralsight-user-management
- pluralsight-teams
- pluralsight-licensing-rest
- pluralsight-plan-info
- pluralsight-flow-users
- pluralsight-flow-teams
- pluralsight-flow-integrations
- pluralsight-flow-repos
description: Unified workflow for platform administrators to manage users, teams, licensing, plan configuration, and Flow workspace settings. Combines user management, teams, licensing, plan info, Flow users, Flow teams, Flow integrations, and Flow repos APIs.
layout: capability
name: Pluralsight User And Team Administration
operations:
- description: Query and manage users via GraphQL
  method: POST
  name: manage-users
  path: /v1/users
- description: Query and manage teams via GraphQL
  method: POST
  name: manage-teams
  path: /v1/teams
- description: List pending user invitations
  method: GET
  name: list-invitations
  path: /v1/invitations
- description: Create a new user invitation
  method: POST
  name: create-invitation
  path: /v1/invitations
- description: List users in the plan
  method: GET
  name: list-license-users
  path: /v1/license-users
- description: List teams in the plan
  method: GET
  name: list-license-teams
  path: /v1/license-teams
- description: Retrieve account and plan details
  method: POST
  name: query-plan-info
  path: /v1/plan-info
- description: List Flow workspace users
  method: GET
  name: list-flow-users
  path: /v1/flow-users
- description: Update Flow user accounts
  method: PUT
  name: update-flow-users
  path: /v1/flow-users
- description: List Flow engineering teams
  method: GET
  name: list-flow-teams
  path: /v1/flow-teams
- description: List Flow integrations and connection status
  method: GET
  name: list-integrations
  path: /v1/integrations
- description: Retrieve repository data and metadata
  method: GET
  name: get-repos
  path: /v1/repositories
personas: []
provider_name: Pluralsight
provider_slug: pluralsight
search_terms:
- list teams in the plan
- plan team listing (legacy rest, deprecated)
- retrieve account and plan details
- list license users
- list users in the plan. deprecated - migrate to graphql user management api.
- send a new user invitation. deprecated - migrate to graphql user management api.
- team administration
- flow integration management and connection status
- update flow users
- get repos
- education
- list pending user invitations. deprecated - migrate to graphql user management api.
- list flow teams
- platform administration
- account and plan details including subscription tier
- update flow user accounts
- list flow workspace users
- list flow integrations and check connection status with external tools and services.
- list pending user invitations
- technology
- list users in the plan
- retrieve repository data and metadata
- user management
- licensing
- query and manage teams including creating teams, managing membership, assigning managers, and configuring team permissions.
- skills assessment
- update, merge, hide, or perform bulk operations on flow user accounts.
- create a new user invitation
- team management including creating teams, managing membership, and permissions
- list integrations
- list teams in the plan. deprecated - migrate to graphql teams api.
- flow engineering team management
- retrieve account and plan details including subscription tier and configuration.
- retrieve repository data and metadata across connected source control systems.
- connected repository data and metadata
- query and manage users via graphql
- query and manage teams via graphql
- flow workspace user management
- courses
- user invitation management (legacy rest, deprecated)
- query plan info
- manage users
- list flow engineering teams
- list flow integrations and connection status
- query and manage users including listing users, inviting members, editing user details, removing users, and canceling invitations.
- create invitation
- list invitations
- engineering metrics
- list flow users in the workspace.
- learning
- video training
- user management including listing, inviting, editing, and removing users
- list flow engineering teams and team membership data.
- manage teams
- list flow users
- plan user listing (legacy rest, deprecated)
- list license teams
- pluralsight
slug: user-and-team-administration
source_filename: user-and-team-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Pluralsight User And Team Administration\"\n  description: \"Unified workflow for platform administrators to manage users, teams, licensing, plan configuration, and Flow workspace settings. Combines user management, teams, licensing, plan info, Flow users, Flow teams, Flow integrations, and Flow repos APIs.\"\n  tags:\n    - Pluralsight\n    - User Management\n    - Team Administration\n    - Platform Administration\n    - Licensing\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PLURALSIGHT_BEARER_TOKEN: PLURALSIGHT_BEARER_TOKEN\n      PLURALSIGHT_FLOW_BEARER_TOKEN: PLURALSIGHT_FLOW_BEARER_TOKEN\n      PLURALSIGHT_FLOW_WORKSPACE: PLURALSIGHT_FLOW_WORKSPACE\n\ncapability:\n  consumes:\n    - import: pluralsight-user-management\n      location: ./shared/user-management.yaml\n    - import: pluralsight-teams\n      location: ./shared/teams.yaml\n    - import: pluralsight-licensing-rest\n\
  \      location: ./shared/licensing-rest.yaml\n    - import: pluralsight-plan-info\n      location: ./shared/plan-info.yaml\n    - import: pluralsight-flow-users\n      location: ./shared/flow-users.yaml\n    - import: pluralsight-flow-teams\n      location: ./shared/flow-teams.yaml\n    - import: pluralsight-flow-integrations\n      location: ./shared/flow-integrations.yaml\n    - import: pluralsight-flow-repos\n      location: ./shared/flow-repos.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: user-team-admin-api\n      description: \"Unified REST API for Pluralsight user and team administration across Skills and Flow platforms.\"\n      resources:\n        - path: /v1/users\n          name: users\n          description: \"User management including listing, inviting, editing, and removing users\"\n          operations:\n            - method: POST\n              name: manage-users\n              description: \"Query and manage users via GraphQL\"\n           \
  \   call: \"pluralsight-user-management.manage-users\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/teams\n          name: teams\n          description: \"Team management including creating teams, managing membership, and permissions\"\n          operations:\n            - method: POST\n              name: manage-teams\n              description: \"Query and manage teams via GraphQL\"\n              call: \"pluralsight-teams.manage-teams\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invitations\n          name: invitations\n\
  \          description: \"User invitation management (legacy REST, deprecated)\"\n          operations:\n            - method: GET\n              name: list-invitations\n              description: \"List pending user invitations\"\n              call: \"pluralsight-licensing-rest.list-invitations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-invitation\n              description: \"Create a new user invitation\"\n              call: \"pluralsight-licensing-rest.create-invitation\"\n              with:\n                payload: \"rest.payload\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/license-users\n          name: license-users\n          description: \"Plan user listing (legacy REST, deprecated)\"\n          operations:\n            - method: GET\n              name: list-license-users\n        \
  \      description: \"List users in the plan\"\n              call: \"pluralsight-licensing-rest.list-license-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/license-teams\n          name: license-teams\n          description: \"Plan team listing (legacy REST, deprecated)\"\n          operations:\n            - method: GET\n              name: list-license-teams\n              description: \"List teams in the plan\"\n              call: \"pluralsight-licensing-rest.list-license-teams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/plan-info\n          name: plan-info\n          description: \"Account and plan details including subscription tier\"\n          operations:\n            - method: POST\n              name: query-plan-info\n              description: \"Retrieve account and plan details\"\n              call: \"pluralsight-plan-info.query-plan-info\"\
  \n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/flow-users\n          name: flow-users\n          description: \"Flow workspace user management\"\n          operations:\n            - method: GET\n              name: list-flow-users\n              description: \"List Flow workspace users\"\n              call: \"pluralsight-flow-users.list-flow-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-flow-users\n              description: \"Update Flow user accounts\"\n              call: \"pluralsight-flow-users.update-flow-users\"\n              with:\n                payload: \"rest.payload\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/flow-teams\n          name: flow-teams\n          description: \"Flow engineering team management\"\n          operations:\n            - method: GET\n              name: list-flow-teams\n              description: \"List Flow engineering teams\"\n              call: \"pluralsight-flow-teams.list-flow-teams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/integrations\n          name: integrations\n          description: \"Flow integration management and connection status\"\n          operations:\n            - method: GET\n              name: list-integrations\n              description: \"List Flow integrations and connection status\"\n              call: \"pluralsight-flow-integrations.list-integrations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories\n       \
  \   name: repositories\n          description: \"Connected repository data and metadata\"\n          operations:\n            - method: GET\n              name: get-repos\n              description: \"Retrieve repository data and metadata\"\n              call: \"pluralsight-flow-repos.get-repos\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: user-team-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted user and team administration across Pluralsight Skills and Flow platforms.\"\n      tools:\n        - name: manage-users\n          description: \"Query and manage users including listing users, inviting members, editing user details, removing users, and canceling invitations.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          call: \"pluralsight-user-management.manage-users\"\
  \n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-teams\n          description: \"Query and manage teams including creating teams, managing membership, assigning managers, and configuring team permissions.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          call: \"pluralsight-teams.manage-teams\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-invitations\n          description: \"List pending user invitations. Deprecated - migrate to GraphQL User Management API.\"\n    \
  \      hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-licensing-rest.list-invitations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-invitation\n          description: \"Send a new user invitation. Deprecated - migrate to GraphQL User Management API.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          call: \"pluralsight-licensing-rest.create-invitation\"\n          with:\n            payload: \"tools.payload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-license-users\n          description: \"List users in the plan. Deprecated - migrate to GraphQL User Management API.\"\n          hints:\n            readOnly: true\n            destructive: false\n\
  \            idempotent: true\n            openWorld: true\n          call: \"pluralsight-licensing-rest.list-license-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-license-teams\n          description: \"List teams in the plan. Deprecated - migrate to GraphQL Teams API.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-licensing-rest.list-license-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-plan-info\n          description: \"Retrieve account and plan details including subscription tier and configuration.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-plan-info.query-plan-info\"\n          with:\n      \
  \      query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-flow-users\n          description: \"List Flow users in the workspace.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-flow-users.list-flow-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-flow-users\n          description: \"Update, merge, hide, or perform bulk operations on Flow user accounts.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-flow-users.update-flow-users\"\n          with:\n            payload: \"tools.payload\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-flow-teams\n          description: \"List Flow engineering teams and team membership data.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-flow-teams.list-flow-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-integrations\n          description: \"List Flow integrations and check connection status with external tools and services.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-flow-integrations.list-integrations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-repos\n          description: \"Retrieve repository data and metadata across connected\
  \ source control systems.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-flow-repos.get-repos\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/capabilities/user-and-team-administration.yaml
tags:
- Pluralsight
- User Management
- Team Administration
- Platform Administration
- Licensing
tools:
- description: Query and manage users including listing users, inviting members, editing user details, removing users, and canceling invitations.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: manage-users
- description: Query and manage teams including creating teams, managing membership, assigning managers, and configuring team permissions.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: manage-teams
- description: List pending user invitations. Deprecated - migrate to GraphQL User Management API.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-invitations
- description: Send a new user invitation. Deprecated - migrate to GraphQL User Management API.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-invitation
- description: List users in the plan. Deprecated - migrate to GraphQL User Management API.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-license-users
- description: List teams in the plan. Deprecated - migrate to GraphQL Teams API.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-license-teams
- description: Retrieve account and plan details including subscription tier and configuration.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-plan-info
- description: List Flow users in the workspace.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-flow-users
- description: Update, merge, hide, or perform bulk operations on Flow user accounts.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-flow-users
- description: List Flow engineering teams and team membership data.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-flow-teams
- description: List Flow integrations and check connection status with external tools and services.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-integrations
- description: Retrieve repository data and metadata across connected source control systems.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-repos
---

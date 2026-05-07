---
categories: []
consumed_apis: []
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
- list integrations
- courses
- video training
- get repos
- list users in the plan
- query and manage teams including creating teams, managing membership, assigning managers, and configuring team permissions.
- update flow user accounts
- user invitation management (legacy rest, deprecated)
- list flow workspace users
- licensing
- update flow users
- query and manage teams via graphql
- account and plan details including subscription tier
- manage teams
- team management including creating teams, managing membership, and permissions
- team administration
- list pending user invitations
- create a new user invitation
- list flow engineering teams
- skills assessment
- manage users
- plan user listing (legacy rest, deprecated)
- update, merge, hide, or perform bulk operations on flow user accounts.
- list license users
- flow integration management and connection status
- list flow integrations and check connection status with external tools and services.
- learning
- list flow engineering teams and team membership data.
- retrieve repository data and metadata across connected source control systems.
- list invitations
- retrieve account and plan details
- flow engineering team management
- retrieve account and plan details including subscription tier and configuration.
- engineering metrics
- plan team listing (legacy rest, deprecated)
- query and manage users via graphql
- connected repository data and metadata
- list license teams
- list flow integrations and connection status
- list users in the plan. deprecated - migrate to graphql user management api.
- list teams in the plan
- create invitation
- technology
- query and manage users including listing users, inviting members, editing user details, removing users, and canceling invitations.
- list flow users
- list flow teams
- user management
- education
- list flow users in the workspace.
- list teams in the plan. deprecated - migrate to graphql teams api.
- query plan info
- flow workspace user management
- retrieve repository data and metadata
- send a new user invitation. deprecated - migrate to graphql user management api.
- pluralsight
- platform administration
- user management including listing, inviting, editing, and removing users
- list pending user invitations. deprecated - migrate to graphql user management api.
slug: user-and-team-administration
source_filename: user-and-team-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pluralsight User And Team Administration\n  description: Unified workflow for platform administrators to manage users, teams, licensing, plan configuration, and Flow\n    workspace settings. Combines user management, teams, licensing, plan info, Flow users, Flow teams, Flow integrations,\n    and Flow repos APIs.\n  tags:\n  - Pluralsight\n  - User Management\n  - Team Administration\n  - Platform Administration\n  - Licensing\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PLURALSIGHT_BEARER_TOKEN: PLURALSIGHT_BEARER_TOKEN\n    PLURALSIGHT_FLOW_BEARER_TOKEN: PLURALSIGHT_FLOW_BEARER_TOKEN\n    PLURALSIGHT_FLOW_WORKSPACE: PLURALSIGHT_FLOW_WORKSPACE\ncapability:\n  consumes:\n  - type: http\n    namespace: pluralsight-user-management\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL queries and mutations for managing users including listing users, inviting members, editing\
  \ user\n      details, removing users, and canceling invitations.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: user-management\n      path: /graphql\n      description: User management via GraphQL\n      operations:\n      - name: manage-users\n        method: POST\n        description: Execute GraphQL queries and mutations for managing users including listing users, inviting members, editing\n          user details, removing users, and canceling invitations.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation\
  \ to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  - type: http\n    namespace: pluralsight-teams\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL queries and mutations for managing teams including creating teams, managing membership, assigning\n      managers, and configuring team permissions.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: teams\n      path: /graphql\n      description: Team management via GraphQL\n      operations:\n      - name: manage-teams\n        method: POST\n        description: Execute GraphQL queries and mutations for managing teams including creating teams, managing membership,\n        \
  \  assigning managers, and configuring team permissions.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  - type: http\n    namespace: pluralsight-licensing-rest\n    baseUri: https://app.pluralsight.com/plans/api/license/v1\n    description: Legacy\
  \ REST API for managing user invitations, users, and teams within a plan. Deprecated.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: invitations\n      path: /invitations\n      description: User invitation management (deprecated)\n      operations:\n      - name: list-invitations\n        method: GET\n        description: Retrieve a list of pending user invitations. Deprecated - migrate to GraphQL User Management API.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-invitation\n        method: POST\n        description: Send a new user invitation. Deprecated - migrate to GraphQL User Management API.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payload: '{{tools.payload}}'\n\
  \    - name: users\n      path: /users\n      description: User management (deprecated)\n      operations:\n      - name: list-license-users\n        method: GET\n        description: Retrieve a list of users in the plan. Deprecated - migrate to GraphQL User Management API.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams\n      description: Team management (deprecated)\n      operations:\n      - name: list-license-teams\n        method: GET\n        description: Retrieve a list of teams in the plan. Deprecated - migrate to GraphQL Teams API.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: pluralsight-plan-info\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL query for retrieving account and plan details including subscription tier and configuration.\n\
  \    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: plan-info\n      path: /graphql\n      description: Plan info queries via GraphQL\n      operations:\n      - name: query-plan-info\n        method: POST\n        description: Execute GraphQL queries to retrieve account and plan details including subscription tier and configuration.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  - type: http\n    namespace: pluralsight-flow-users\n    baseUri: https://{{PLURALSIGHT_FLOW_WORKSPACE}}.appfireflow.com/v3/customer/core\n    description: REST API for managing Flow users including listing, updating, merging, hiding, and bulk operations on user\n      accounts.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_FLOW_BEARER_TOKEN}}'\n    resources:\n    - name: flow-users\n      path: /users\n      description: Flow user management\n      operations:\n      - name: list-flow-users\n        method: GET\n        description: Retrieve a list of Flow users in the workspace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-flow-users\n        method: PUT\n    \
  \    description: Update, merge, hide, or perform bulk operations on Flow user accounts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payload: '{{tools.payload}}'\n  - type: http\n    namespace: pluralsight-flow-teams\n    baseUri: https://{{PLURALSIGHT_FLOW_WORKSPACE}}.appfireflow.com/v3/customer/core\n    description: REST API for managing Flow engineering teams and team membership data.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_FLOW_BEARER_TOKEN}}'\n    resources:\n    - name: flow-teams\n      path: /teams\n      description: Flow team management\n      operations:\n      - name: list-flow-teams\n        method: GET\n        description: Retrieve a list of Flow engineering teams and team membership data.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  - type: http\n    namespace: pluralsight-flow-integrations\n    baseUri: https://{{PLURALSIGHT_FLOW_WORKSPACE}}.appfireflow.com/v3/customer/core\n    description: REST API for managing Flow integrations and checking connection status with external tools and services.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_FLOW_BEARER_TOKEN}}'\n    resources:\n    - name: integrations\n      path: /integrations\n      description: Flow integration management\n      operations:\n      - name: list-integrations\n        method: GET\n        description: Retrieve a list of Flow integrations and check connection status with external tools and services.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: pluralsight-flow-repos\n    baseUri: https://{{PLURALSIGHT_FLOW_WORKSPACE}}.appfireflow.com/v3/customer/core\n    description: REST API for accessing\
  \ repository data and metadata across connected source control systems.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_FLOW_BEARER_TOKEN}}'\n    resources:\n    - name: repos\n      path: /repos\n      description: Repository data and metadata\n      operations:\n      - name: get-repos\n        method: GET\n        description: Retrieve repository data and metadata across connected source control systems.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: user-team-admin-api\n    description: Unified REST API for Pluralsight user and team administration across Skills and Flow platforms.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User management including listing, inviting, editing, and removing users\n      operations:\n      - method: POST\n        name: manage-users\n        description: Query\
  \ and manage users via GraphQL\n        call: pluralsight-user-management.manage-users\n        with:\n          query: rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams\n      name: teams\n      description: Team management including creating teams, managing membership, and permissions\n      operations:\n      - method: POST\n        name: manage-teams\n        description: Query and manage teams via GraphQL\n        call: pluralsight-teams.manage-teams\n        with:\n          query: rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invitations\n      name: invitations\n      description: User invitation management (legacy REST, deprecated)\n      operations:\n      - method: GET\n        name: list-invitations\n\
  \        description: List pending user invitations\n        call: pluralsight-licensing-rest.list-invitations\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-invitation\n        description: Create a new user invitation\n        call: pluralsight-licensing-rest.create-invitation\n        with:\n          payload: rest.payload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/license-users\n      name: license-users\n      description: Plan user listing (legacy REST, deprecated)\n      operations:\n      - method: GET\n        name: list-license-users\n        description: List users in the plan\n        call: pluralsight-licensing-rest.list-license-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/license-teams\n      name: license-teams\n      description: Plan team listing (legacy REST, deprecated)\n      operations:\n      - method:\
  \ GET\n        name: list-license-teams\n        description: List teams in the plan\n        call: pluralsight-licensing-rest.list-license-teams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/plan-info\n      name: plan-info\n      description: Account and plan details including subscription tier\n      operations:\n      - method: POST\n        name: query-plan-info\n        description: Retrieve account and plan details\n        call: pluralsight-plan-info.query-plan-info\n        with:\n          query: rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flow-users\n      name: flow-users\n      description: Flow workspace user management\n      operations:\n      - method: GET\n        name: list-flow-users\n        description: List Flow workspace users\n        call: pluralsight-flow-users.list-flow-users\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-flow-users\n        description: Update Flow user accounts\n        call: pluralsight-flow-users.update-flow-users\n        with:\n          payload: rest.payload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flow-teams\n      name: flow-teams\n      description: Flow engineering team management\n      operations:\n      - method: GET\n        name: list-flow-teams\n        description: List Flow engineering teams\n        call: pluralsight-flow-teams.list-flow-teams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/integrations\n      name: integrations\n      description: Flow integration management and connection status\n      operations:\n      - method: GET\n        name: list-integrations\n        description: List Flow integrations and connection status\n        call: pluralsight-flow-integrations.list-integrations\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories\n      name: repositories\n      description: Connected repository data and metadata\n      operations:\n      - method: GET\n        name: get-repos\n        description: Retrieve repository data and metadata\n        call: pluralsight-flow-repos.get-repos\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: user-team-admin-mcp\n    transport: http\n    description: MCP server for AI-assisted user and team administration across Pluralsight Skills and Flow platforms.\n    tools:\n    - name: manage-users\n      description: Query and manage users including listing users, inviting members, editing user details, removing users,\n        and canceling invitations.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n        openWorld: true\n      call: pluralsight-user-management.manage-users\n\
  \      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: manage-teams\n      description: Query and manage teams including creating teams, managing membership, assigning managers, and configuring\n        team permissions.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n        openWorld: true\n      call: pluralsight-teams.manage-teams\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invitations\n      description: List pending user invitations. Deprecated - migrate to GraphQL User Management API.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-licensing-rest.list-invitations\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-invitation\n      description: Send a new user invitation. Deprecated - migrate to GraphQL User Management API.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n        openWorld: true\n      call: pluralsight-licensing-rest.create-invitation\n      with:\n        payload: tools.payload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-license-users\n      description: List users in the plan. Deprecated - migrate to GraphQL User Management API.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-licensing-rest.list-license-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-license-teams\n      description: List teams in the plan. Deprecated - migrate to GraphQL Teams API.\n      hints:\n  \
  \      readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-licensing-rest.list-license-teams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-plan-info\n      description: Retrieve account and plan details including subscription tier and configuration.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-plan-info.query-plan-info\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-flow-users\n      description: List Flow users in the workspace.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-flow-users.list-flow-users\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: update-flow-users\n      description: Update, merge, hide, or perform bulk operations on Flow user accounts.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-flow-users.update-flow-users\n      with:\n        payload: tools.payload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-flow-teams\n      description: List Flow engineering teams and team membership data.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-flow-teams.list-flow-teams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-integrations\n      description: List Flow integrations and check connection status with external tools and services.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n        openWorld: true\n      call: pluralsight-flow-integrations.list-integrations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-repos\n      description: Retrieve repository data and metadata across connected source control systems.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-flow-repos.get-repos\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

---
categories: []
consumed_apis: []
description: Workflow capability for provisioning and managing users, teams, and access control across SAP Analytics Cloud using SCIM 2.0. Used by IT administrators and system integrators for identity lifecycle management.
layout: capability
name: SAP BI Tools User and Access Management
operations:
- description: List all provisioned users.
  method: GET
  name: list-users
  path: /v1/users
- description: Get a user by ID.
  method: GET
  name: get-user
  path: /v1/users/{userId}
- description: Delete a user account.
  method: DELETE
  name: delete-user
  path: /v1/users/{userId}
- description: List all teams.
  method: GET
  name: list-teams
  path: /v1/teams
personas: []
provider_name: SAP BI Tools
provider_slug: sap-bi-tools
search_terms:
- reporting
- analytics
- user management via scim 2.0.
- scim
- get a user by id.
- create user
- list teams
- identity management
- team management via scim 2.0.
- provision a new user in sap analytics cloud via scim 2.0.
- create team
- get details of a specific user account.
- data visualization
- delete user
- list all users provisioned in sap analytics cloud.
- list all provisioned users.
- list all teams (groups) configured in sap analytics cloud.
- sap
- deprovision a user from sap analytics cloud.
- delete a user account.
- update user
- single user.
- list all teams.
- get user
- business intelligence
- create a new team for organizing users and managing content access.
- list users
- update an existing user's profile and role assignments.
slug: user-and-access-management
source_filename: user-and-access-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP BI Tools User and Access Management\n  description: Workflow capability for provisioning and managing users, teams, and access control across SAP Analytics Cloud\n    using SCIM 2.0. Used by IT administrators and system integrators for identity lifecycle management.\n  tags:\n  - Analytics\n  - Business Intelligence\n  - Identity Management\n  - SAP\n  - SCIM\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_AC_OAUTH_TOKEN: SAP_AC_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: analytics-cloud\n    baseUri: https://{tenant}.{datacenter}.sapanalytics.cloud\n    description: SAP Analytics Cloud REST API for managing stories, resources, users, and teams.\n    authentication:\n      type: bearer\n      token: '{{SAP_AC_OAUTH_TOKEN}}'\n    resources:\n    - name: stories\n      path: /api/v1/stories\n      description: Manage analytic stories including dashboards and reports.\n\
  \      operations:\n      - name: list-stories\n        method: GET\n        description: List all stories available on the SAP Analytics Cloud tenant.\n        inputParameters:\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: Comma-separated related resources to include (e.g., models)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-story\n        method: GET\n        description: Get a story by its unique ID.\n        inputParameters:\n        - name: storyId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the story\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: Comma-separated related resources to include\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: resources\n      path: /api/v1/Resources\n      description: Browse and manage resources in the SAP Analytics Cloud file repository.\n      operations:\n      - name: list-resources\n        method: GET\n        description: List resources including stories, models, and folders.\n        inputParameters:\n        - name: resourceType\n          in: query\n          type: string\n          required: false\n          description: Filter by resource type (STORY, MODEL, FOLDER)\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Number of records to skip for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name:\
  \ users\n      path: /api/v1/scim2/Users\n      description: SCIM 2.0 endpoints for managing user accounts.\n      operations:\n      - name: list-users\n        method: GET\n        description: List users using SCIM 2.0 protocol.\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: SCIM 2.0 filter expression\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user using SCIM 2.0 protocol.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userName: '{{tools.userName}}'\n\
  \            displayName: '{{tools.displayName}}'\n      - name: get-user\n        method: GET\n        description: Get a user by ID using SCIM 2.0.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PUT\n        description: Update a user record using SCIM 2.0.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userName: '{{tools.userName}}'\n      - name: delete-user\n      \
  \  method: DELETE\n        description: Delete a user from SAP Analytics Cloud.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /api/v1/scim2/Groups\n      description: SCIM 2.0 endpoints for managing teams and group memberships.\n      operations:\n      - name: list-teams\n        method: GET\n        description: List teams using SCIM 2.0 protocol.\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: SCIM 2.0 filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-team\n        method: POST\n      \
  \  description: Create a new team using SCIM 2.0 protocol.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n    - name: calendars\n      path: /api/v1/calendars\n      description: Manage calendar events and tasks for planning workflows.\n      operations:\n      - name: list-calendars\n        method: GET\n        description: List calendar events and planning tasks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: user-access-management-api\n    description: Unified REST API for SAP Analytics Cloud user and team provisioning.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User management via SCIM 2.0.\n      operations:\n      - method: GET\n\
  \        name: list-users\n        description: List all provisioned users.\n        call: analytics-cloud.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{userId}\n      name: user\n      description: Single user.\n      operations:\n      - method: GET\n        name: get-user\n        description: Get a user by ID.\n        call: analytics-cloud.get-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-user\n        description: Delete a user account.\n        call: analytics-cloud.delete-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams\n      name: teams\n      description: Team management via SCIM 2.0.\n      operations:\n      - method: GET\n        name: list-teams\n        description: List all teams.\n    \
  \    call: analytics-cloud.list-teams\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: user-access-management-mcp\n    transport: http\n    description: MCP server for AI-assisted user provisioning in SAP Analytics Cloud.\n    tools:\n    - name: list-users\n      description: List all users provisioned in SAP Analytics Cloud.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: analytics-cloud.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get details of a specific user account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: analytics-cloud.get-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Provision a new user in SAP Analytics Cloud via SCIM 2.0.\n      hints:\n        readOnly:\
  \ false\n        openWorld: false\n      call: analytics-cloud.create-user\n      with:\n        userName: tools.userName\n        displayName: tools.displayName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-user\n      description: Update an existing user's profile and role assignments.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: analytics-cloud.update-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Deprovision a user from SAP Analytics Cloud.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: analytics-cloud.delete-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-teams\n      description: List all teams (groups) configured in SAP Analytics Cloud.\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: analytics-cloud.list-teams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-team\n      description: Create a new team for organizing users and managing content access.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: analytics-cloud.create-team\n      with:\n        displayName: tools.displayName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-bi-tools/refs/heads/main/capabilities/user-and-access-management.yaml
tags:
- Analytics
- Business Intelligence
- Identity Management
- SAP
- SCIM
tools:
- description: List all users provisioned in SAP Analytics Cloud.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Get details of a specific user account.
  hints:
    openWorld: false
    readOnly: true
  name: get-user
- description: Provision a new user in SAP Analytics Cloud via SCIM 2.0.
  hints:
    openWorld: false
    readOnly: false
  name: create-user
- description: Update an existing user's profile and role assignments.
  hints:
    idempotent: true
    readOnly: false
  name: update-user
- description: Deprovision a user from SAP Analytics Cloud.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-user
- description: List all teams (groups) configured in SAP Analytics Cloud.
  hints:
    openWorld: true
    readOnly: true
  name: list-teams
- description: Create a new team for organizing users and managing content access.
  hints:
    openWorld: false
    readOnly: false
  name: create-team
---

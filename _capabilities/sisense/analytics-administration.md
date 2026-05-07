---
categories: []
consumed_apis: []
description: Unified analytics administration workflow for Sisense BI platform management. Combines dashboard management, user and group access control, Elasticube data model management, and data security rule configuration. Used by BI administrators, OEM partners, and DevOps teams automating Sisense platform operations.
layout: capability
name: Sisense Analytics Administration
operations:
- description: List user-accessible dashboards
  method: GET
  name: list-dashboards
  path: /v1/dashboards
- description: Create a new analytics dashboard
  method: POST
  name: create-dashboard
  path: /v1/dashboards
- description: Get dashboard details
  method: GET
  name: get-dashboard
  path: /v1/dashboards/{id}
- description: Delete a dashboard
  method: DELETE
  name: delete-dashboard
  path: /v1/dashboards/{id}
- description: List all dashboards (admin)
  method: GET
  name: list-all-dashboards
  path: /v1/admin/dashboards
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user
  method: POST
  name: create-user
  path: /v1/users
- description: Get user details
  method: GET
  name: get-user
  path: /v1/users/{id}
- description: Remove a user
  method: DELETE
  name: delete-user
  path: /v1/users/{id}
- description: List user groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create a user group
  method: POST
  name: create-group
  path: /v1/groups
- description: List all Elasticubes
  method: GET
  name: list-elasticubes
  path: /v1/elasticubes
personas: []
provider_name: Sisense
provider_slug: sisense
search_terms:
- analytics
- create group
- list user groups configured for access control
- get dashboard details
- manage platform users
- data security
- remove a user
- list groups
- create a new analytics dashboard in sisense
- create a new user group for organizing access control
- embedded analytics
- delete an analytics dashboard
- list elasticubes
- list all elasticubes
- delete dashboard
- delete a dashboard
- remove a user from the sisense platform
- list all users
- list user groups
- list user-accessible dashboards
- manage analytics dashboards
- business intelligence
- delete user
- get user details
- list all dashboards across all users (admin access required)
- administration
- list users
- dashboards
- get details for a specific dashboard including its configuration
- data models
- manage user groups
- get row-level data security rules configured for an elasticube
- create dashboard
- manage a specific user
- list analytics dashboards accessible to the current user
- get details for a specific user account
- get data security rules
- get dashboard
- list dashboards
- list all dashboards (admin)
- get user
- list all users in the sisense platform
- create a new sisense user with specified role and group assignments
- manage a specific dashboard
- create a new analytics dashboard
- list all dashboards
- create user
- create a new user
- create a user group
- manage elasticube data models
- list all elasticube data models in the sisense platform
- admin dashboard access
slug: analytics-administration
source_filename: analytics-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sisense Analytics Administration\n  description: Unified analytics administration workflow for Sisense BI platform management. Combines dashboard management,\n    user and group access control, Elasticube data model management, and data security rule configuration. Used by BI administrators,\n    OEM partners, and DevOps teams automating Sisense platform operations.\n  tags:\n  - Analytics\n  - Business Intelligence\n  - Dashboards\n  - Administration\n  - Data Security\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SISENSE_API_TOKEN: SISENSE_API_TOKEN\n    SISENSE_HOST: SISENSE_HOST\ncapability:\n  consumes:\n  - type: http\n    namespace: sisense\n    baseUri: https://{{SISENSE_HOST}}/api/v1\n    description: Sisense REST API v1 for analytics platform management\n    authentication:\n      type: bearer\n      token: '{{SISENSE_API_TOKEN}}'\n    resources:\n    - name: dashboards\n      path:\
  \ /dashboards\n      description: Manage analytics dashboards\n      operations:\n      - name: list-dashboards\n        method: GET\n        description: List dashboards accessible to the authenticated user\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: skip\n          in: query\n          type: integer\n          required: false\n          description: Number of results to skip\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated fields to include\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dashboard\n        method: POST\n        description: Create a new dashboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            desc: '{{tools.desc}}'\n    - name: dashboard\n      path: /dashboards/{id}\n      description: Manage a specific dashboard\n      operations:\n      - name: get-dashboard\n        method: GET\n        description: Get a specific dashboard by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Dashboard identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-dashboard\n        method: DELETE\n        description: Delete a dashboard\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Dashboard identifier\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: dashboards-admin\n      path: /dashboards/admin\n      description: Admin-level dashboard access\n      operations:\n      - name: list-all-dashboards\n        method: GET\n        description: List all dashboards across all users (admin only)\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: skip\n          in: query\n          type: integer\n          required: false\n          description: Results to skip\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: Manage platform users\n      operations:\n      - name: list-users\n        method: GET\n        description: List users in the system\n        inputParameters:\n        - name: limit\n          in:\
  \ query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            role: '{{tools.role}}'\n    - name: user\n      path: /users/{id}\n      description: Manage a specific user\n      operations:\n      - name: get-user\n        method: GET\n        description: Get a user by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ User identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-user\n        method: DELETE\n        description: Delete a user\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: User identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      description: Manage user groups\n      operations:\n      - name: list-groups\n        method: GET\n        description: List user groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new user group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: elasticubes\n      path: /elasticubes/getElasticubes\n      description: List Elasticube data models\n      operations:\n      - name: list-elasticubes\n        method: GET\n        description: List all Elasticube data models\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-security\n      path: /elasticubes/{server}/{elasticube}/datasecurity\n      description: Manage data security rules for Elasticubes\n      operations:\n      - name: get-data-security-rules\n        method: GET\n        description: Get all data security rules for an Elasticube\n        inputParameters:\n        - name: server\n          in: path\n          type: string\n          required: true\n          description: Server\
  \ name (use LocalHost for single-node)\n        - name: elasticube\n          in: path\n          type: string\n          required: true\n          description: Elasticube title\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-data-security-rule\n        method: POST\n        description: Create a data security rule for an Elasticube\n        inputParameters:\n        - name: server\n          in: path\n          type: string\n          required: true\n          description: Server name\n        - name: elasticube\n          in: path\n          type: string\n          required: true\n          description: Elasticube title\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            column: '{{tools.column}}'\n            table: '{{tools.table}}'\n        \
  \    members: '{{tools.members}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: analytics-administration-api\n    description: Unified REST API for Sisense analytics platform administration.\n    resources:\n    - path: /v1/dashboards\n      name: dashboards\n      description: Manage analytics dashboards\n      operations:\n      - method: GET\n        name: list-dashboards\n        description: List user-accessible dashboards\n        call: sisense.list-dashboards\n        with:\n          limit: rest.limit\n          skip: rest.skip\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dashboard\n        description: Create a new analytics dashboard\n        call: sisense.create-dashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dashboards/{id}\n      name: dashboard\n      description: Manage a specific dashboard\n      operations:\n      - method: GET\n \
  \       name: get-dashboard\n        description: Get dashboard details\n        call: sisense.get-dashboard\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-dashboard\n        description: Delete a dashboard\n        call: sisense.delete-dashboard\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/admin/dashboards\n      name: admin-dashboards\n      description: Admin dashboard access\n      operations:\n      - method: GET\n        name: list-all-dashboards\n        description: List all dashboards (admin)\n        call: sisense.list-all-dashboards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Manage platform users\n      operations:\n      - method: GET\n        name: list-users\n        description: List all\
  \ users\n        call: sisense.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new user\n        call: sisense.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{id}\n      name: user\n      description: Manage a specific user\n      operations:\n      - method: GET\n        name: get-user\n        description: Get user details\n        call: sisense.get-user\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-user\n        description: Remove a user\n        call: sisense.delete-user\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Manage user groups\n      operations:\n      - method:\
  \ GET\n        name: list-groups\n        description: List user groups\n        call: sisense.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create a user group\n        call: sisense.create-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/elasticubes\n      name: elasticubes\n      description: Manage Elasticube data models\n      operations:\n      - method: GET\n        name: list-elasticubes\n        description: List all Elasticubes\n        call: sisense.list-elasticubes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: analytics-administration-mcp\n    transport: http\n    description: MCP server for AI-assisted Sisense analytics platform administration.\n    tools:\n    - name: list-dashboards\n      description: List analytics dashboards accessible to\
  \ the current user\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sisense.list-dashboards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-all-dashboards\n      description: List all dashboards across all users (admin access required)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sisense.list-all-dashboards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dashboard\n      description: Get details for a specific dashboard including its configuration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sisense.get-dashboard\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-dashboard\n      description: Create a new analytics dashboard in Sisense\n      hints:\n        readOnly: false\n        destructive: false\n      call: sisense.create-dashboard\n      with:\n\
  \        title: tools.title\n        desc: tools.desc\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-dashboard\n      description: Delete an analytics dashboard\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sisense.delete-dashboard\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all users in the Sisense platform\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sisense.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new Sisense user with specified role and group assignments\n      hints:\n        readOnly: false\n        destructive: false\n      call: sisense.create-user\n      with:\n        email: tools.email\n        firstName: tools.firstName\n        lastName: tools.lastName\n\
  \        role: tools.role\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get details for a specific user account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sisense.get-user\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Remove a user from the Sisense platform\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sisense.delete-user\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List user groups configured for access control\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sisense.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-group\n      description: Create a new\
  \ user group for organizing access control\n      hints:\n        readOnly: false\n        destructive: false\n      call: sisense.create-group\n      with:\n        name: tools.name\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-elasticubes\n      description: List all Elasticube data models in the Sisense platform\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sisense.list-elasticubes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-data-security-rules\n      description: Get row-level data security rules configured for an Elasticube\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sisense.get-data-security-rules\n      with:\n        server: tools.server\n        elasticube: tools.elasticube\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sisense/refs/heads/main/capabilities/analytics-administration.yaml
tags:
- Analytics
- Business Intelligence
- Dashboards
- Administration
- Data Security
tools:
- description: List analytics dashboards accessible to the current user
  hints:
    openWorld: true
    readOnly: true
  name: list-dashboards
- description: List all dashboards across all users (admin access required)
  hints:
    openWorld: false
    readOnly: true
  name: list-all-dashboards
- description: Get details for a specific dashboard including its configuration
  hints:
    openWorld: false
    readOnly: true
  name: get-dashboard
- description: Create a new analytics dashboard in Sisense
  hints:
    destructive: false
    readOnly: false
  name: create-dashboard
- description: Delete an analytics dashboard
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-dashboard
- description: List all users in the Sisense platform
  hints:
    openWorld: false
    readOnly: true
  name: list-users
- description: Create a new Sisense user with specified role and group assignments
  hints:
    destructive: false
    readOnly: false
  name: create-user
- description: Get details for a specific user account
  hints:
    openWorld: false
    readOnly: true
  name: get-user
- description: Remove a user from the Sisense platform
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-user
- description: List user groups configured for access control
  hints:
    openWorld: false
    readOnly: true
  name: list-groups
- description: Create a new user group for organizing access control
  hints:
    destructive: false
    readOnly: false
  name: create-group
- description: List all Elasticube data models in the Sisense platform
  hints:
    openWorld: false
    readOnly: true
  name: list-elasticubes
- description: Get row-level data security rules configured for an Elasticube
  hints:
    openWorld: false
    readOnly: true
  name: get-data-security-rules
---

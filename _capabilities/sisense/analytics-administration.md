---
categories: []
consumed_apis:
- sisense
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
- manage analytics dashboards
- delete dashboard
- create a new sisense user with specified role and group assignments
- create user
- create a user group
- create a new user group for organizing access control
- delete a dashboard
- administration
- delete user
- analytics
- embedded analytics
- list all dashboards across all users (admin access required)
- get dashboard
- dashboards
- list all dashboards
- list elasticubes
- data models
- get user
- business intelligence
- create group
- list user groups
- list all dashboards (admin)
- list all elasticube data models in the sisense platform
- get details for a specific dashboard including its configuration
- remove a user
- list dashboards
- get row-level data security rules configured for an elasticube
- manage a specific dashboard
- list analytics dashboards accessible to the current user
- get details for a specific user account
- list users
- create a new user
- manage user groups
- list all elasticubes
- get dashboard details
- list user groups configured for access control
- create dashboard
- list all users in the sisense platform
- get data security rules
- create a new analytics dashboard
- list groups
- create a new analytics dashboard in sisense
- manage platform users
- list all users
- data security
- delete an analytics dashboard
- get user details
- list user-accessible dashboards
- manage a specific user
- manage elasticube data models
- remove a user from the sisense platform
- admin dashboard access
slug: analytics-administration
source_filename: analytics-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sisense Analytics Administration\"\n  description: >-\n    Unified analytics administration workflow for Sisense BI platform management.\n    Combines dashboard management, user and group access control, Elasticube data\n    model management, and data security rule configuration. Used by BI administrators,\n    OEM partners, and DevOps teams automating Sisense platform operations.\n  tags:\n    - Analytics\n    - Business Intelligence\n    - Dashboards\n    - Administration\n    - Data Security\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SISENSE_API_TOKEN: SISENSE_API_TOKEN\n      SISENSE_HOST: SISENSE_HOST\n\ncapability:\n  consumes:\n    - import: sisense\n      location: ./shared/sisense.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: analytics-administration-api\n      description: \"Unified REST API for Sisense analytics platform administration.\"\
  \n      resources:\n        - path: /v1/dashboards\n          name: dashboards\n          description: Manage analytics dashboards\n          operations:\n            - method: GET\n              name: list-dashboards\n              description: List user-accessible dashboards\n              call: \"sisense.list-dashboards\"\n              with:\n                limit: \"rest.limit\"\n                skip: \"rest.skip\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dashboard\n              description: Create a new analytics dashboard\n              call: \"sisense.create-dashboard\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dashboards/{id}\n          name: dashboard\n          description: Manage a specific dashboard\n          operations:\n            - method: GET\n              name: get-dashboard\n\
  \              description: Get dashboard details\n              call: \"sisense.get-dashboard\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-dashboard\n              description: Delete a dashboard\n              call: \"sisense.delete-dashboard\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/admin/dashboards\n          name: admin-dashboards\n          description: Admin dashboard access\n          operations:\n            - method: GET\n              name: list-all-dashboards\n              description: List all dashboards (admin)\n              call: \"sisense.list-all-dashboards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        -\
  \ path: /v1/users\n          name: users\n          description: Manage platform users\n          operations:\n            - method: GET\n              name: list-users\n              description: List all users\n              call: \"sisense.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: Create a new user\n              call: \"sisense.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{id}\n          name: user\n          description: Manage a specific user\n          operations:\n            - method: GET\n              name: get-user\n              description: Get user details\n              call: \"sisense.get-user\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n   \
  \               mapping: \"$.\"\n            - method: DELETE\n              name: delete-user\n              description: Remove a user\n              call: \"sisense.delete-user\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: Manage user groups\n          operations:\n            - method: GET\n              name: list-groups\n              description: List user groups\n              call: \"sisense.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-group\n              description: Create a user group\n              call: \"sisense.create-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/elasticubes\n     \
  \     name: elasticubes\n          description: Manage Elasticube data models\n          operations:\n            - method: GET\n              name: list-elasticubes\n              description: List all Elasticubes\n              call: \"sisense.list-elasticubes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: analytics-administration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Sisense analytics platform administration.\"\n      tools:\n        - name: list-dashboards\n          description: List analytics dashboards accessible to the current user\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sisense.list-dashboards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-all-dashboards\n          description: List all dashboards across all users\
  \ (admin access required)\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sisense.list-all-dashboards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dashboard\n          description: Get details for a specific dashboard including its configuration\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sisense.get-dashboard\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-dashboard\n          description: Create a new analytics dashboard in Sisense\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"sisense.create-dashboard\"\n          with:\n            title: \"tools.title\"\n            desc: \"tools.desc\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: delete-dashboard\n          description: Delete an analytics dashboard\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"sisense.delete-dashboard\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: List all users in the Sisense platform\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sisense.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: Create a new Sisense user with specified role and group assignments\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"sisense.create-user\"\n          with:\n            email: \"tools.email\"\n            firstName: \"\
  tools.firstName\"\n            lastName: \"tools.lastName\"\n            role: \"tools.role\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: Get details for a specific user account\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sisense.get-user\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: Remove a user from the Sisense platform\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"sisense.delete-user\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: List user groups configured for access control\n\
  \          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sisense.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-group\n          description: Create a new user group for organizing access control\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"sisense.create-group\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-elasticubes\n          description: List all Elasticube data models in the Sisense platform\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sisense.list-elasticubes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-data-security-rules\n          description:\
  \ Get row-level data security rules configured for an Elasticube\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sisense.get-data-security-rules\"\n          with:\n            server: \"tools.server\"\n            elasticube: \"tools.elasticube\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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

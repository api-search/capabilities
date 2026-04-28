---
categories:
- analytics
consumed_apis:
- looker
description: Unified workflow for business intelligence analytics including dashboards, looks, queries, and user management. Used by data analysts and BI administrators.
layout: capability
name: Looker Analytics and Reporting
operations:
- description: List all looks.
  method: GET
  name: list-looks
  path: /v1/looks
- description: Get look details.
  method: GET
  name: get-look
  path: /v1/looks/{id}
- description: Update a look.
  method: PATCH
  name: update-look
  path: /v1/looks/{id}
- description: Delete a look.
  method: DELETE
  name: delete-look
  path: /v1/looks/{id}
- description: List all dashboards.
  method: GET
  name: list-dashboards
  path: /v1/dashboards
- description: Create a dashboard.
  method: POST
  name: create-dashboard
  path: /v1/dashboards
- description: Get dashboard details.
  method: GET
  name: get-dashboard
  path: /v1/dashboards/{id}
- description: Update a dashboard.
  method: PATCH
  name: update-dashboard
  path: /v1/dashboards/{id}
- description: Delete a dashboard.
  method: DELETE
  name: delete-dashboard
  path: /v1/dashboards/{id}
- description: Create a query.
  method: POST
  name: create-query
  path: /v1/queries
- description: Get query details.
  method: GET
  name: get-query
  path: /v1/queries/{id}
- description: List all users.
  method: GET
  name: list-users
  path: /v1/users
- description: Create a user.
  method: POST
  name: create-user
  path: /v1/users
personas: []
provider_name: Looker
provider_slug: looker
search_terms:
- search for dashboards.
- create user
- get dashboard details.
- list dashboards
- run look
- bi platform
- list looks
- get query
- run query
- dashboard management.
- update a dashboard.
- list all saved looks.
- data visualization
- get dashboard
- list all looks.
- delete a look.
- create a new dashboard.
- create dashboard
- create a dashboard.
- create a user.
- run a look and return results.
- look management.
- analytics
- delete look
- update user
- create a query.
- business intelligence
- delete a user.
- dashboards
- delete dashboard
- individual dashboard management.
- search for looks by title.
- list all dashboards.
- individual query operations.
- get look
- looker
- query management.
- list all users.
- get look details.
- delete user
- list users
- individual look management.
- update look
- search looks
- update a user.
- update dashboard
- run a saved query.
- create a new user.
- data analytics
- update a look.
- get user
- search dashboards
- create query
- user management.
- delete a dashboard.
- get user details.
- get query details.
slug: analytics-and-reporting
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Looker Analytics and Reporting\"\n  description: \"Unified workflow for business intelligence analytics including dashboards, looks, queries, and user management. Used by data analysts and BI administrators.\"\n  tags:\n    - Looker\n    - Business Intelligence\n    - Analytics\n    - Dashboards\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      LOOKER_CLIENT_ID: LOOKER_CLIENT_ID\n      LOOKER_CLIENT_SECRET: LOOKER_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: looker\n      location: ./shared/looker-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: looker-analytics-api\n      description: \"Unified REST API for Looker analytics and reporting.\"\n      resources:\n        - path: /v1/looks\n          name: looks\n          description: \"Look management.\"\n          operations:\n            - method: GET\n              name: list-looks\n \
  \             description: \"List all looks.\"\n              call: \"looker.list-looks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/looks/{id}\n          name: look-details\n          description: \"Individual look management.\"\n          operations:\n            - method: GET\n              name: get-look\n              description: \"Get look details.\"\n              call: \"looker.get-look\"\n              with:\n                look_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-look\n              description: \"Update a look.\"\n              call: \"looker.update-look\"\n              with:\n                look_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name:\
  \ delete-look\n              description: \"Delete a look.\"\n              call: \"looker.delete-look\"\n              with:\n                look_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dashboards\n          name: dashboards\n          description: \"Dashboard management.\"\n          operations:\n            - method: GET\n              name: list-dashboards\n              description: \"List all dashboards.\"\n              call: \"looker.list-dashboards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dashboard\n              description: \"Create a dashboard.\"\n              call: \"looker.create-dashboard\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dashboards/{id}\n          name: dashboard-details\n\
  \          description: \"Individual dashboard management.\"\n          operations:\n            - method: GET\n              name: get-dashboard\n              description: \"Get dashboard details.\"\n              call: \"looker.get-dashboard\"\n              with:\n                dashboard_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-dashboard\n              description: \"Update a dashboard.\"\n              call: \"looker.update-dashboard\"\n              with:\n                dashboard_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-dashboard\n              description: \"Delete a dashboard.\"\n              call: \"looker.delete-dashboard\"\n              with:\n                dashboard_id: \"rest.id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queries\n          name: queries\n          description: \"Query management.\"\n          operations:\n            - method: POST\n              name: create-query\n              description: \"Create a query.\"\n              call: \"looker.create-query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queries/{id}\n          name: query-details\n          description: \"Individual query operations.\"\n          operations:\n            - method: GET\n              name: get-query\n              description: \"Get query details.\"\n              call: \"looker.get-query\"\n              with:\n                query_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User management.\"\n  \
  \        operations:\n            - method: GET\n              name: list-users\n              description: \"List all users.\"\n              call: \"looker.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a user.\"\n              call: \"looker.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: looker-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Looker analytics and reporting.\"\n      tools:\n        - name: list-looks\n          description: \"List all saved looks.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"looker.list-looks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: search-looks\n          description: \"Search for looks by title.\"\n          hints:\n            readOnly: true\n          call: \"looker.search-looks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-look\n          description: \"Get look details.\"\n          hints:\n            readOnly: true\n          call: \"looker.get-look\"\n          with:\n            look_id: \"tools.lookId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-look\n          description: \"Update a look.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"looker.update-look\"\n          with:\n            look_id: \"tools.lookId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-look\n          description: \"Delete a look.\"\n          hints:\n            destructive:\
  \ true\n            idempotent: true\n          call: \"looker.delete-look\"\n          with:\n            look_id: \"tools.lookId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-look\n          description: \"Run a look and return results.\"\n          hints:\n            readOnly: true\n          call: \"looker.run-look\"\n          with:\n            look_id: \"tools.lookId\"\n            result_format: \"tools.resultFormat\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dashboards\n          description: \"List all dashboards.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"looker.list-dashboards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-dashboards\n          description: \"Search for dashboards.\"\n          hints:\n            readOnly:\
  \ true\n          call: \"looker.search-dashboards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-dashboard\n          description: \"Create a new dashboard.\"\n          hints:\n            readOnly: false\n          call: \"looker.create-dashboard\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dashboard\n          description: \"Get dashboard details.\"\n          hints:\n            readOnly: true\n          call: \"looker.get-dashboard\"\n          with:\n            dashboard_id: \"tools.dashboardId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-dashboard\n          description: \"Update a dashboard.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"looker.update-dashboard\"\n          with:\n            dashboard_id: \"tools.dashboardId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-dashboard\n          description: \"Delete a dashboard.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"looker.delete-dashboard\"\n          with:\n            dashboard_id: \"tools.dashboardId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-query\n          description: \"Create a query.\"\n          hints:\n            readOnly: false\n          call: \"looker.create-query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-query\n          description: \"Get query details.\"\n          hints:\n            readOnly: true\n          call: \"looker.get-query\"\n          with:\n            query_id: \"tools.queryId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: run-query\n          description: \"Run a saved query.\"\n          hints:\n            readOnly: true\n          call: \"looker.run-query\"\n          with:\n            query_id: \"tools.queryId\"\n            result_format: \"tools.resultFormat\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List all users.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"looker.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Create a new user.\"\n          hints:\n            readOnly: false\n          call: \"looker.create-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Get user details.\"\n          hints:\n            readOnly: true\n\
  \          call: \"looker.get-user\"\n          with:\n            user_id: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-user\n          description: \"Update a user.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"looker.update-user\"\n          with:\n            user_id: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: \"Delete a user.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"looker.delete-user\"\n          with:\n            user_id: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/looker/refs/heads/main/capabilities/analytics-and-reporting.yaml
tags:
- Looker
- Business Intelligence
- Analytics
- Dashboards
tools:
- description: List all saved looks.
  hints:
    openWorld: true
    readOnly: true
  name: list-looks
- description: Search for looks by title.
  hints:
    readOnly: true
  name: search-looks
- description: Get look details.
  hints:
    readOnly: true
  name: get-look
- description: Update a look.
  hints:
    idempotent: true
    readOnly: false
  name: update-look
- description: Delete a look.
  hints:
    destructive: true
    idempotent: true
  name: delete-look
- description: Run a look and return results.
  hints:
    readOnly: true
  name: run-look
- description: List all dashboards.
  hints:
    openWorld: true
    readOnly: true
  name: list-dashboards
- description: Search for dashboards.
  hints:
    readOnly: true
  name: search-dashboards
- description: Create a new dashboard.
  hints:
    readOnly: false
  name: create-dashboard
- description: Get dashboard details.
  hints:
    readOnly: true
  name: get-dashboard
- description: Update a dashboard.
  hints:
    idempotent: true
    readOnly: false
  name: update-dashboard
- description: Delete a dashboard.
  hints:
    destructive: true
    idempotent: true
  name: delete-dashboard
- description: Create a query.
  hints:
    readOnly: false
  name: create-query
- description: Get query details.
  hints:
    readOnly: true
  name: get-query
- description: Run a saved query.
  hints:
    readOnly: true
  name: run-query
- description: List all users.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new user.
  hints:
    readOnly: false
  name: create-user
- description: Get user details.
  hints:
    readOnly: true
  name: get-user
- description: Update a user.
  hints:
    idempotent: true
    readOnly: false
  name: update-user
- description: Delete a user.
  hints:
    destructive: true
    idempotent: true
  name: delete-user
---

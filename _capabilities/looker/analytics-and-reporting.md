---
categories:
- analytics
consumed_apis: []
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
- individual query operations.
- list all users.
- individual look management.
- create query
- search dashboards
- delete dashboard
- query management.
- looker
- update a user.
- analytics
- delete a look.
- list all dashboards.
- data analytics
- create a user.
- create a query.
- delete a user.
- list all looks.
- update look
- dashboards
- create user
- dashboard management.
- run query
- get user details.
- create dashboard
- get query
- run a look and return results.
- search for looks by title.
- run look
- get dashboard details.
- search for dashboards.
- run a saved query.
- get look details.
- get query details.
- data visualization
- delete user
- create a dashboard.
- delete look
- update dashboard
- update a dashboard.
- create a new dashboard.
- user management.
- get look
- get dashboard
- update user
- list all saved looks.
- individual dashboard management.
- look management.
- get user
- business intelligence
- delete a dashboard.
- list looks
- list users
- list dashboards
- search looks
- update a look.
- bi platform
- create a new user.
slug: analytics-and-reporting
source_filename: analytics-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Looker Analytics and Reporting\n  description: Unified workflow for business intelligence analytics including dashboards, looks, queries, and user management.\n    Used by data analysts and BI administrators.\n  tags:\n  - Looker\n  - Business Intelligence\n  - Analytics\n  - Dashboards\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    LOOKER_CLIENT_ID: LOOKER_CLIENT_ID\n    LOOKER_CLIENT_SECRET: LOOKER_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: looker\n    baseUri: https://your-instance.looker.com:19999/api/4.0\n    description: Looker API 4.0 for business intelligence operations.\n    authentication:\n      type: bearer\n      token: '{{LOOKER_ACCESS_TOKEN}}'\n    resources:\n    - name: auth\n      path: /login\n      description: Authentication.\n      operations:\n      - name: login\n        method: POST\n        description: Authenticate and obtain an access token.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: logout\n        method: DELETE\n        description: Log out and invalidate the current access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: looks\n      path: /looks\n      description: Look management.\n      operations:\n      - name: list-looks\n        method: GET\n        description: List all looks.\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to include in response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: looks-search\n      path: /looks/search\n      description: Search looks.\n      operations:\n      - name: search-looks\n        method:\
  \ GET\n        description: Search for looks by title or other criteria.\n        inputParameters:\n        - name: title\n          in: query\n          type: string\n          required: false\n          description: Title to search for.\n        - name: space_id\n          in: query\n          type: string\n          required: false\n          description: Space ID to filter by.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: look-details\n      path: /looks/{look_id}\n      description: Individual look management.\n      operations:\n      - name: get-look\n        method: GET\n        description: Get look details.\n        inputParameters:\n        - name: look_id\n          in: path\n          type: integer\n          required: true\n          description: Look ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: update-look\n        method: PATCH\n        description: Update a look.\n        inputParameters:\n        - name: look_id\n          in: path\n          type: integer\n          required: true\n          description: Look ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n      - name: delete-look\n        method: DELETE\n        description: Delete a look.\n        inputParameters:\n        - name: look_id\n          in: path\n          type: integer\n          required: true\n          description: Look ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: look-run\n      path: /looks/{look_id}/run/{result_format}\n      description: Run a look.\n      operations:\n      - name: run-look\n        method: GET\n\
  \        description: Run a look and return results.\n        inputParameters:\n        - name: look_id\n          in: path\n          type: integer\n          required: true\n          description: Look ID.\n        - name: result_format\n          in: path\n          type: string\n          required: true\n          description: Result format (json, csv, etc).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards\n      path: /dashboards\n      description: Dashboard management.\n      operations:\n      - name: list-dashboards\n        method: GET\n        description: List all dashboards.\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to include.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ create-dashboard\n        method: POST\n        description: Create a new dashboard.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            space_id: '{{tools.spaceId}}'\n    - name: dashboards-search\n      path: /dashboards/search\n      description: Search dashboards.\n      operations:\n      - name: search-dashboards\n        method: GET\n        description: Search for dashboards.\n        inputParameters:\n        - name: title\n          in: query\n          type: string\n          required: false\n          description: Title to search for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboard-details\n      path: /dashboards/{dashboard_id}\n      description: Individual dashboard management.\n      operations:\n\
  \      - name: get-dashboard\n        method: GET\n        description: Get dashboard details.\n        inputParameters:\n        - name: dashboard_id\n          in: path\n          type: string\n          required: true\n          description: Dashboard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-dashboard\n        method: PATCH\n        description: Update a dashboard.\n        inputParameters:\n        - name: dashboard_id\n          in: path\n          type: string\n          required: true\n          description: Dashboard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n      - name: delete-dashboard\n        method: DELETE\n        description: Delete a dashboard.\n        inputParameters:\n        -\
  \ name: dashboard_id\n          in: path\n          type: string\n          required: true\n          description: Dashboard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queries\n      path: /queries\n      description: Query management.\n      operations:\n      - name: create-query\n        method: POST\n        description: Create a query.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            view: '{{tools.view}}'\n    - name: query-details\n      path: /queries/{query_id}\n      description: Individual query operations.\n      operations:\n      - name: get-query\n        method: GET\n        description: Get query details.\n        inputParameters:\n        - name: query_id\n          in: path\n          type:\
  \ integer\n          required: true\n          description: Query ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query-run\n      path: /queries/{query_id}/run/{result_format}\n      description: Run a query.\n      operations:\n      - name: run-query\n        method: GET\n        description: Run a saved query.\n        inputParameters:\n        - name: query_id\n          in: path\n          type: integer\n          required: true\n          description: Query ID.\n        - name: result_format\n          in: path\n          type: string\n          required: true\n          description: Result format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: User management.\n      operations:\n      - name: list-users\n        method: GET\n        description:\
  \ List all users.\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to include.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            first_name: '{{tools.firstName}}'\n            last_name: '{{tools.lastName}}'\n    - name: user-details\n      path: /users/{user_id}\n      description: Individual user management.\n      operations:\n      - name: get-user\n        method: GET\n        description: Get user details.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: integer\n          required: true\n\
  \          description: User ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PATCH\n        description: Update a user.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: integer\n          required: true\n          description: User ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            first_name: '{{tools.firstName}}'\n      - name: delete-user\n        method: DELETE\n        description: Delete a user.\n        inputParameters:\n        - name: user_id\n          in: path\n          type: integer\n          required: true\n          description: User ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \  exposes:\n  - type: rest\n    port: 8080\n    namespace: looker-analytics-api\n    description: Unified REST API for Looker analytics and reporting.\n    resources:\n    - path: /v1/looks\n      name: looks\n      description: Look management.\n      operations:\n      - method: GET\n        name: list-looks\n        description: List all looks.\n        call: looker.list-looks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/looks/{id}\n      name: look-details\n      description: Individual look management.\n      operations:\n      - method: GET\n        name: get-look\n        description: Get look details.\n        call: looker.get-look\n        with:\n          look_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-look\n        description: Update a look.\n        call: looker.update-look\n        with:\n          look_id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-look\n        description: Delete a look.\n        call: looker.delete-look\n        with:\n          look_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dashboards\n      name: dashboards\n      description: Dashboard management.\n      operations:\n      - method: GET\n        name: list-dashboards\n        description: List all dashboards.\n        call: looker.list-dashboards\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dashboard\n        description: Create a dashboard.\n        call: looker.create-dashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dashboards/{id}\n      name: dashboard-details\n      description: Individual dashboard management.\n      operations:\n      - method: GET\n        name: get-dashboard\n\
  \        description: Get dashboard details.\n        call: looker.get-dashboard\n        with:\n          dashboard_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-dashboard\n        description: Update a dashboard.\n        call: looker.update-dashboard\n        with:\n          dashboard_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-dashboard\n        description: Delete a dashboard.\n        call: looker.delete-dashboard\n        with:\n          dashboard_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queries\n      name: queries\n      description: Query management.\n      operations:\n      - method: POST\n        name: create-query\n        description: Create a query.\n        call: looker.create-query\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /v1/queries/{id}\n      name: query-details\n      description: Individual query operations.\n      operations:\n      - method: GET\n        name: get-query\n        description: Get query details.\n        call: looker.get-query\n        with:\n          query_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User management.\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users.\n        call: looker.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a user.\n        call: looker.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: looker-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted\
  \ Looker analytics and reporting.\n    tools:\n    - name: list-looks\n      description: List all saved looks.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: looker.list-looks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-looks\n      description: Search for looks by title.\n      hints:\n        readOnly: true\n      call: looker.search-looks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-look\n      description: Get look details.\n      hints:\n        readOnly: true\n      call: looker.get-look\n      with:\n        look_id: tools.lookId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-look\n      description: Update a look.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: looker.update-look\n      with:\n        look_id: tools.lookId\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: delete-look\n      description: Delete a look.\n      hints:\n        destructive: true\n        idempotent: true\n      call: looker.delete-look\n      with:\n        look_id: tools.lookId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-look\n      description: Run a look and return results.\n      hints:\n        readOnly: true\n      call: looker.run-look\n      with:\n        look_id: tools.lookId\n        result_format: tools.resultFormat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dashboards\n      description: List all dashboards.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: looker.list-dashboards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-dashboards\n      description: Search for dashboards.\n      hints:\n        readOnly: true\n      call: looker.search-dashboards\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: create-dashboard\n      description: Create a new dashboard.\n      hints:\n        readOnly: false\n      call: looker.create-dashboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dashboard\n      description: Get dashboard details.\n      hints:\n        readOnly: true\n      call: looker.get-dashboard\n      with:\n        dashboard_id: tools.dashboardId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-dashboard\n      description: Update a dashboard.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: looker.update-dashboard\n      with:\n        dashboard_id: tools.dashboardId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-dashboard\n      description: Delete a dashboard.\n      hints:\n        destructive: true\n        idempotent: true\n      call: looker.delete-dashboard\n      with:\n        dashboard_id:\
  \ tools.dashboardId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-query\n      description: Create a query.\n      hints:\n        readOnly: false\n      call: looker.create-query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-query\n      description: Get query details.\n      hints:\n        readOnly: true\n      call: looker.get-query\n      with:\n        query_id: tools.queryId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-query\n      description: Run a saved query.\n      hints:\n        readOnly: true\n      call: looker.run-query\n      with:\n        query_id: tools.queryId\n        result_format: tools.resultFormat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all users.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: looker.list-users\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new user.\n      hints:\n        readOnly: false\n      call: looker.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get user details.\n      hints:\n        readOnly: true\n      call: looker.get-user\n      with:\n        user_id: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-user\n      description: Update a user.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: looker.update-user\n      with:\n        user_id: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Delete a user.\n      hints:\n        destructive: true\n        idempotent: true\n      call: looker.delete-user\n      with:\n        user_id: tools.userId\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n"
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

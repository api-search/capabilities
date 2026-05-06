---
categories: []
consumed_apis: []
description: The Metabase API provides programmatic access to Metabase, an open source business intelligence and analytics platform. It allows developers to manage dashboards, questions (cards), collections, databases, users, permissions, and to execute queries against connected data sources.
layout: capability
name: Metabase API
operations:
- description: Create a session
  method: POST
  name: post-session
  path: /session
- description: Delete a session
  method: DELETE
  name: delete-session
  path: /session
- description: List collections
  method: GET
  name: get-collection
  path: /collection
- description: Create a collection
  method: POST
  name: post-collection
  path: /collection
- description: Get a collection
  method: GET
  name: get-collection-id
  path: /collection/{id}
- description: List dashboards
  method: GET
  name: get-dashboard
  path: /dashboard
- description: Create a dashboard
  method: POST
  name: post-dashboard
  path: /dashboard
- description: Get a dashboard
  method: GET
  name: get-dashboard-id
  path: /dashboard/{id}
- description: Update a dashboard
  method: PUT
  name: put-dashboard-id
  path: /dashboard/{id}
- description: Archive a dashboard
  method: DELETE
  name: delete-dashboard-id
  path: /dashboard/{id}
- description: List saved questions (cards)
  method: GET
  name: get-card
  path: /card
- description: Create a card
  method: POST
  name: post-card
  path: /card
- description: Get a card
  method: GET
  name: get-card-id
  path: /card/{id}
- description: Execute a card's query
  method: POST
  name: post-card-id-query
  path: /card/{id}/query
- description: List databases
  method: GET
  name: get-database
  path: /database
- description: Add a database connection
  method: POST
  name: post-database
  path: /database
- description: Get a database
  method: GET
  name: get-database-id
  path: /database/{id}
- description: Execute an ad-hoc query
  method: POST
  name: post-dataset
  path: /dataset
- description: Search Metabase content
  method: GET
  name: get-search
  path: /search
- description: List users
  method: GET
  name: get-user
  path: /user
- description: Create a user
  method: POST
  name: post-user
  path: /user
- description: Get a user
  method: GET
  name: get-user-id
  path: /user/{id}
- description: List permission groups
  method: GET
  name: get-permissions-group
  path: /permissions/group
- description: List settings
  method: GET
  name: get-setting
  path: /setting
personas: []
provider_name: Metabase
provider_slug: metabase
search_terms:
- get database
- post session
- get database id
- get a dashboard
- post dataset
- add a database connection
- post user
- get a collection
- post database
- delete session
- analytics
- update a dashboard
- get search
- get dashboard id
- get a database
- get permissions group
- get collection
- dashboards
- delete dashboard id
- get collection id
- put dashboard id
- get a card
- sql
- data visualization
- open source
- get user id
- delete a session
- execute an ad-hoc query
- metabase
- list saved questions (cards)
- create a session
- api
- create a dashboard
- get card id
- execute a card's query
- get setting
- post dashboard
- get dashboard
- create a collection
- create a user
- list databases
- archive a dashboard
- get user
- business intelligence
- search metabase content
- list users
- get a user
- list permission groups
- list settings
- list dashboards
- get card
- post card id query
- post card
- post collection
- list collections
- create a card
slug: metabase-capability
source_filename: metabase-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Metabase API\n  description: The Metabase API provides programmatic access to Metabase, an open source business intelligence and analytics\n    platform. It allows developers to manage dashboards, questions (cards), collections, databases, users, permissions, and\n    to execute queries against connected data sources.\n  tags:\n  - Metabase\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: metabase\n    baseUri: https://your-metabase-instance.com/api\n    description: Metabase API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{METABASE_TOKEN}}'\n    resources:\n    - name: session\n      path: /session\n      operations:\n      - name: post-session\n        method: POST\n        description: Create a session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: delete-session\n        method: DELETE\n        description: Delete a session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: collection\n      path: /collection\n      operations:\n      - name: get-collection\n        method: GET\n        description: List collections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-collection\n        method: POST\n        description: Create a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: collection-id\n      path: /collection/{id}\n      operations:\n      - name: get-collection-id\n        method: GET\n        description: Get a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: dashboard\n      path: /dashboard\n      operations:\n      - name: get-dashboard\n        method: GET\n        description: List dashboards\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-dashboard\n        method: POST\n        description: Create a dashboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboard-id\n      path: /dashboard/{id}\n      operations:\n      - name: get-dashboard-id\n        method: GET\n        description: Get a dashboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-dashboard-id\n        method: PUT\n        description: Update a dashboard\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: delete-dashboard-id\n        method: DELETE\n        description: Archive a dashboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: card\n      path: /card\n      operations:\n      - name: get-card\n        method: GET\n        description: List saved questions (cards)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-card\n        method: POST\n        description: Create a card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: card-id\n      path: /card/{id}\n      operations:\n      - name: get-card-id\n        method: GET\n        description: Get a card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: card-id-query\n      path: /card/{id}/query\n      operations:\n      - name: post-card-id-query\n        method: POST\n        description: Execute a card's query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: database\n      path: /database\n      operations:\n      - name: get-database\n        method: GET\n        description: List databases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-database\n        method: POST\n        description: Add a database connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: database-id\n      path: /database/{id}\n      operations:\n      - name: get-database-id\n        method: GET\n        description: Get\
  \ a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dataset\n      path: /dataset\n      operations:\n      - name: post-dataset\n        method: POST\n        description: Execute an ad-hoc query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      operations:\n      - name: get-search\n        method: GET\n        description: Search Metabase content\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Search term.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /user\n      operations:\n      - name: get-user\n        method: GET\n        description: List users\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-user\n        method: POST\n        description: Create a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-id\n      path: /user/{id}\n      operations:\n      - name: get-user-id\n        method: GET\n        description: Get a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: permissions-group\n      path: /permissions/group\n      operations:\n      - name: get-permissions-group\n        method: GET\n        description: List permission groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: setting\n      path: /setting\n      operations:\n      - name: get-setting\n        method: GET\n\
  \        description: List settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: metabase-rest\n    description: REST adapter for Metabase API.\n    resources:\n    - path: /session\n      name: post-session\n      operations:\n      - method: POST\n        name: post-session\n        description: Create a session\n        call: metabase.post-session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /session\n      name: delete-session\n      operations:\n      - method: DELETE\n        name: delete-session\n        description: Delete a session\n        call: metabase.delete-session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collection\n      name: get-collection\n      operations:\n      - method: GET\n        name: get-collection\n        description: List collections\n\
  \        call: metabase.get-collection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collection\n      name: post-collection\n      operations:\n      - method: POST\n        name: post-collection\n        description: Create a collection\n        call: metabase.post-collection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collection/{id}\n      name: get-collection-id\n      operations:\n      - method: GET\n        name: get-collection-id\n        description: Get a collection\n        call: metabase.get-collection-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboard\n      name: get-dashboard\n      operations:\n      - method: GET\n        name: get-dashboard\n        description: List dashboards\n        call: metabase.get-dashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboard\n      name: post-dashboard\n\
  \      operations:\n      - method: POST\n        name: post-dashboard\n        description: Create a dashboard\n        call: metabase.post-dashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboard/{id}\n      name: get-dashboard-id\n      operations:\n      - method: GET\n        name: get-dashboard-id\n        description: Get a dashboard\n        call: metabase.get-dashboard-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboard/{id}\n      name: put-dashboard-id\n      operations:\n      - method: PUT\n        name: put-dashboard-id\n        description: Update a dashboard\n        call: metabase.put-dashboard-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboard/{id}\n      name: delete-dashboard-id\n      operations:\n      - method: DELETE\n        name: delete-dashboard-id\n        description: Archive a dashboard\n        call: metabase.delete-dashboard-id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /card\n      name: get-card\n      operations:\n      - method: GET\n        name: get-card\n        description: List saved questions (cards)\n        call: metabase.get-card\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /card\n      name: post-card\n      operations:\n      - method: POST\n        name: post-card\n        description: Create a card\n        call: metabase.post-card\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /card/{id}\n      name: get-card-id\n      operations:\n      - method: GET\n        name: get-card-id\n        description: Get a card\n        call: metabase.get-card-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /card/{id}/query\n      name: post-card-id-query\n      operations:\n      - method: POST\n        name: post-card-id-query\n        description:\
  \ Execute a card's query\n        call: metabase.post-card-id-query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /database\n      name: get-database\n      operations:\n      - method: GET\n        name: get-database\n        description: List databases\n        call: metabase.get-database\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /database\n      name: post-database\n      operations:\n      - method: POST\n        name: post-database\n        description: Add a database connection\n        call: metabase.post-database\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /database/{id}\n      name: get-database-id\n      operations:\n      - method: GET\n        name: get-database-id\n        description: Get a database\n        call: metabase.get-database-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dataset\n      name:\
  \ post-dataset\n      operations:\n      - method: POST\n        name: post-dataset\n        description: Execute an ad-hoc query\n        call: metabase.post-dataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search\n      name: get-search\n      operations:\n      - method: GET\n        name: get-search\n        description: Search Metabase content\n        call: metabase.get-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user\n      name: get-user\n      operations:\n      - method: GET\n        name: get-user\n        description: List users\n        call: metabase.get-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user\n      name: post-user\n      operations:\n      - method: POST\n        name: post-user\n        description: Create a user\n        call: metabase.post-user\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /user/{id}\n      name: get-user-id\n      operations:\n      - method: GET\n        name: get-user-id\n        description: Get a user\n        call: metabase.get-user-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /permissions/group\n      name: get-permissions-group\n      operations:\n      - method: GET\n        name: get-permissions-group\n        description: List permission groups\n        call: metabase.get-permissions-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /setting\n      name: get-setting\n      operations:\n      - method: GET\n        name: get-setting\n        description: List settings\n        call: metabase.get-setting\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: metabase-mcp\n    transport: http\n    description: MCP adapter for Metabase API for AI agent use.\n    tools:\n    - name:\
  \ post-session\n      description: Create a session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: metabase.post-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-session\n      description: Delete a session\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: metabase.delete-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-collection\n      description: List collections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metabase.get-collection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-collection\n      description: Create a collection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: metabase.post-collection\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-collection-id\n      description: Get a collection\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metabase.get-collection-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dashboard\n      description: List dashboards\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metabase.get-dashboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-dashboard\n      description: Create a dashboard\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: metabase.post-dashboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dashboard-id\n      description: Get a dashboard\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n    \
  \  call: metabase.get-dashboard-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-dashboard-id\n      description: Update a dashboard\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: metabase.put-dashboard-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-dashboard-id\n      description: Archive a dashboard\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: metabase.delete-dashboard-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-card\n      description: List saved questions (cards)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metabase.get-card\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-card\n      description: Create a card\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: metabase.post-card\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-card-id\n      description: Get a card\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metabase.get-card-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-card-id-query\n      description: Execute a card's query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: metabase.post-card-id-query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-database\n      description: List databases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metabase.get-database\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-database\n      description: Add a database\
  \ connection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: metabase.post-database\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-database-id\n      description: Get a database\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metabase.get-database-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-dataset\n      description: Execute an ad-hoc query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: metabase.post-dataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-search\n      description: Search Metabase content\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metabase.get-search\n      with:\n        q: tools.q\n      inputParameters:\n      - name:\
  \ q\n        type: string\n        description: Search term.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metabase.get-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-user\n      description: Create a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: metabase.post-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user-id\n      description: Get a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metabase.get-user-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-permissions-group\n      description: List permission groups\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: metabase.get-permissions-group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-setting\n      description: List settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metabase.get-setting\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    METABASE_TOKEN: METABASE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/metabase/refs/heads/main/capabilities/metabase-capability.yaml
tags:
- Metabase
- API
tools:
- description: Create a session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-session
- description: Delete a session
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-session
- description: List collections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-collection
- description: Create a collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-collection
- description: Get a collection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-collection-id
- description: List dashboards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dashboard
- description: Create a dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-dashboard
- description: Get a dashboard
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dashboard-id
- description: Update a dashboard
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-dashboard-id
- description: Archive a dashboard
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-dashboard-id
- description: List saved questions (cards)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-card
- description: Create a card
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-card
- description: Get a card
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-card-id
- description: Execute a card's query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-card-id-query
- description: List databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-database
- description: Add a database connection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-database
- description: Get a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-database-id
- description: Execute an ad-hoc query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-dataset
- description: Search Metabase content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-search
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-user
- description: Create a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-user
- description: Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-user-id
- description: List permission groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-permissions-group
- description: List settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-setting
---

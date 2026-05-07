---
categories: []
consumed_apis: []
description: Oracle Primavera P6 EPPM REST API provides programmatic access to enterprise project portfolio management data including WBS structures, activity schedules, resource assignments, critical path analysis, and portfolio dashboards. Available for both cloud and on-premises deployments.
layout: capability
name: Oracle Primavera P6 EPPM REST API
operations:
- description: List projects
  method: GET
  name: listprojects
  path: /projects
- description: Create a project
  method: POST
  name: createproject
  path: /projects
- description: Get a project
  method: GET
  name: getproject
  path: /projects/{objectId}
- description: Update a project
  method: PUT
  name: updateproject
  path: /projects/{objectId}
- description: Delete a project
  method: DELETE
  name: deleteproject
  path: /projects/{objectId}
- description: List activities
  method: GET
  name: listactivities
  path: /activities
- description: Create an activity
  method: POST
  name: createactivity
  path: /activities
- description: Get an activity
  method: GET
  name: getactivity
  path: /activities/{objectId}
- description: Update an activity
  method: PUT
  name: updateactivity
  path: /activities/{objectId}
- description: List WBS elements
  method: GET
  name: listwbs
  path: /wbss
- description: List resources
  method: GET
  name: listresources
  path: /resources
- description: List resource assignments
  method: GET
  name: listresourceassignments
  path: /resourceassignments
- description: List baselines
  method: GET
  name: listbaselines
  path: /baselines
personas: []
provider_name: Oracle Primavera
provider_slug: oracle-primavera
search_terms:
- list resource assignments
- engineering
- getproject
- portfolio management
- list baselines
- api
- construction
- create a project
- get a project
- list resources
- primavera
- project management
- listresources
- updateproject
- list projects
- listactivities
- createactivity
- listbaselines
- create an activity
- get an activity
- deleteproject
- update a project
- list wbs elements
- list activities
- listwbs
- listresourceassignments
- update an activity
- listprojects
- scheduling
- getactivity
- oracle
- delete a project
- updateactivity
- createproject
slug: oracle-primavera-capability
source_filename: oracle-primavera-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Primavera P6 EPPM REST API\n  description: Oracle Primavera P6 EPPM REST API provides programmatic access to enterprise project portfolio management data\n    including WBS structures, activity schedules, resource assignments, critical path analysis, and portfolio dashboards.\n    Available for both cloud and on-premises deployments.\n  tags:\n  - Oracle\n  - Primavera\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-primavera\n    baseUri: https://primavera.example.com/p6ws/rest/v1\n    description: Oracle Primavera P6 EPPM REST API HTTP API.\n    authentication:\n      type: basic\n      username: '{{ORACLE_PRIMAVERA_USERNAME}}'\n      password: '{{ORACLE_PRIMAVERA_PASSWORD}}'\n    resources:\n    - name: projects\n      path: /projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: List projects\n        inputParameters:\n\
  \        - name: Fields\n          in: query\n          type: string\n          description: Comma-separated list of fields to return\n        - name: Filter\n          in: query\n          type: string\n          description: RSQL filter expression\n        - name: OrderBy\n          in: query\n          type: string\n          description: Field to sort by\n        - name: offset\n          in: query\n          type: integer\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum records to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Create a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-objectid\n      path: /projects/{objectId}\n\
  \      operations:\n      - name: getproject\n        method: GET\n        description: Get a project\n        inputParameters:\n        - name: Fields\n          in: query\n          type: string\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PUT\n        description: Update a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproject\n        method: DELETE\n        description: Delete a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activities\n      path: /activities\n      operations:\n      - name: listactivities\n        method: GET\n        description: List activities\n        inputParameters:\n\
  \        - name: Fields\n          in: query\n          type: string\n        - name: Filter\n          in: query\n          type: string\n          description: Filter by project or WBS; e.g. ProjectObjectId eq 12345\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createactivity\n        method: POST\n        description: Create an activity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activities-objectid\n      path: /activities/{objectId}\n      operations:\n      - name: getactivity\n        method: GET\n        description: Get an activity\n        inputParameters:\n        - name: Fields\n          in: query\n          type: string\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateactivity\n        method: PUT\n        description: Update an activity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wbss\n      path: /wbss\n      operations:\n      - name: listwbs\n        method: GET\n        description: List WBS elements\n        inputParameters:\n        - name: Fields\n          in: query\n          type: string\n        - name: Filter\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources\n      path: /resources\n      operations:\n      - name: listresources\n        method: GET\n\
  \        description: List resources\n        inputParameters:\n        - name: Fields\n          in: query\n          type: string\n        - name: Filter\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resourceassignments\n      path: /resourceassignments\n      operations:\n      - name: listresourceassignments\n        method: GET\n        description: List resource assignments\n        inputParameters:\n        - name: Fields\n          in: query\n          type: string\n        - name: Filter\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: baselines\n      path: /baselines\n      operations:\n      - name: listbaselines\n        method: GET\n        description: List baselines\n        inputParameters:\n        - name: Fields\n          in: query\n          type: string\n        - name: Filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-primavera-rest\n    description: REST adapter for Oracle Primavera P6 EPPM REST API.\n    resources:\n    - path: /projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List projects\n        call: oracle-primavera.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n\
  \      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Create a project\n        call: oracle-primavera.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{objectId}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Get a project\n        call: oracle-primavera.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{objectId}\n      name: updateproject\n      operations:\n      - method: PUT\n        name: updateproject\n        description: Update a project\n        call: oracle-primavera.updateproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{objectId}\n      name: deleteproject\n      operations:\n      - method: DELETE\n        name: deleteproject\n        description: Delete a project\n    \
  \    call: oracle-primavera.deleteproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /activities\n      name: listactivities\n      operations:\n      - method: GET\n        name: listactivities\n        description: List activities\n        call: oracle-primavera.listactivities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /activities\n      name: createactivity\n      operations:\n      - method: POST\n        name: createactivity\n        description: Create an activity\n        call: oracle-primavera.createactivity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /activities/{objectId}\n      name: getactivity\n      operations:\n      - method: GET\n        name: getactivity\n        description: Get an activity\n        call: oracle-primavera.getactivity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /activities/{objectId}\n\
  \      name: updateactivity\n      operations:\n      - method: PUT\n        name: updateactivity\n        description: Update an activity\n        call: oracle-primavera.updateactivity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wbss\n      name: listwbs\n      operations:\n      - method: GET\n        name: listwbs\n        description: List WBS elements\n        call: oracle-primavera.listwbs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resources\n      name: listresources\n      operations:\n      - method: GET\n        name: listresources\n        description: List resources\n        call: oracle-primavera.listresources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resourceassignments\n      name: listresourceassignments\n      operations:\n      - method: GET\n        name: listresourceassignments\n        description: List resource assignments\n      \
  \  call: oracle-primavera.listresourceassignments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /baselines\n      name: listbaselines\n      operations:\n      - method: GET\n        name: listbaselines\n        description: List baselines\n        call: oracle-primavera.listbaselines\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oracle-primavera-mcp\n    transport: http\n    description: MCP adapter for Oracle Primavera P6 EPPM REST API for AI agent use.\n    tools:\n    - name: listprojects\n      description: List projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-primavera.listprojects\n      with:\n        Fields: tools.Fields\n        Filter: tools.Filter\n        OrderBy: tools.OrderBy\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: Fields\n      \
  \  type: string\n        description: Comma-separated list of fields to return\n      - name: Filter\n        type: string\n        description: RSQL filter expression\n      - name: OrderBy\n        type: string\n        description: Field to sort by\n      - name: offset\n        type: integer\n        description: Pagination offset\n      - name: limit\n        type: integer\n        description: Maximum records to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: Create a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-primavera.createproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Get a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-primavera.getproject\n      with:\n        Fields: tools.Fields\n\
  \      inputParameters:\n      - name: Fields\n        type: string\n        description: Comma-separated list of fields to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproject\n      description: Update a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: oracle-primavera.updateproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproject\n      description: Delete a project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: oracle-primavera.deleteproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listactivities\n      description: List activities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-primavera.listactivities\n      with:\n        Fields: tools.Fields\n        Filter: tools.Filter\n\
  \        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: Fields\n        type: string\n        description: Fields\n      - name: Filter\n        type: string\n        description: Filter by project or WBS; e.g. ProjectObjectId eq 12345\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createactivity\n      description: Create an activity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-primavera.createactivity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getactivity\n      description: Get an activity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-primavera.getactivity\n      with:\n        Fields: tools.Fields\n\
  \      inputParameters:\n      - name: Fields\n        type: string\n        description: Fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateactivity\n      description: Update an activity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: oracle-primavera.updateactivity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listwbs\n      description: List WBS elements\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-primavera.listwbs\n      with:\n        Fields: tools.Fields\n        Filter: tools.Filter\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: Fields\n        type: string\n        description: Fields\n      - name: Filter\n        type: string\n        description: Filter\n      - name: offset\n        type: integer\n        description: offset\n\
  \      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listresources\n      description: List resources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-primavera.listresources\n      with:\n        Fields: tools.Fields\n        Filter: tools.Filter\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: Fields\n        type: string\n        description: Fields\n      - name: Filter\n        type: string\n        description: Filter\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listresourceassignments\n      description: List resource assignments\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: oracle-primavera.listresourceassignments\n      with:\n        Fields: tools.Fields\n        Filter: tools.Filter\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: Fields\n        type: string\n        description: Fields\n      - name: Filter\n        type: string\n        description: Filter\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbaselines\n      description: List baselines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-primavera.listbaselines\n      with:\n        Fields: tools.Fields\n        Filter: tools.Filter\n      inputParameters:\n      - name: Fields\n        type: string\n        description: Fields\n      - name: Filter\n        type:\
  \ string\n        description: Filter\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ORACLE_PRIMAVERA_USERNAME: ORACLE_PRIMAVERA_USERNAME\n    ORACLE_PRIMAVERA_PASSWORD: ORACLE_PRIMAVERA_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-primavera/refs/heads/main/capabilities/oracle-primavera-capability.yaml
tags:
- Oracle
- Primavera
- API
tools:
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Create a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Get a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Update a project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproject
- description: Delete a project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: List activities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listactivities
- description: Create an activity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createactivity
- description: Get an activity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getactivity
- description: Update an activity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateactivity
- description: List WBS elements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwbs
- description: List resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listresources
- description: List resource assignments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listresourceassignments
- description: List baselines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbaselines
---

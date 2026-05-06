---
categories: []
consumed_apis: []
description: Workflow capability for DevOps and platform engineering teams using Sumo Logic for log analytics, monitoring, alerting, and security observability. Covers search jobs, dashboards, monitors, user management, and ingestion.
layout: capability
name: Sumo Logic Log Analytics and Observability
operations:
- description: List all users in the organization
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user
  method: POST
  name: create-user
  path: /v1/users
- description: Get a user by ID
  method: GET
  name: get-user
  path: /v1/users/{id}
- description: Delete a user
  method: DELETE
  name: delete-user
  path: /v1/users/{id}
- description: List all roles
  method: GET
  name: list-roles
  path: /v1/roles
- description: Create a new role
  method: POST
  name: create-role
  path: /v1/roles
- description: List all monitors
  method: GET
  name: list-monitors
  path: /v1/monitors
- description: Create a new monitor
  method: POST
  name: create-monitor
  path: /v1/monitors
- description: List all dashboards
  method: GET
  name: list-dashboards
  path: /v2/dashboards
- description: Create a new dashboard
  method: POST
  name: create-dashboard
  path: /v2/dashboards
- description: Run a log search query
  method: POST
  name: create-search-job
  path: /v1/search-jobs
- description: List all access keys
  method: GET
  name: list-access-keys
  path: /v1/access-keys
- description: Create a new access key
  method: POST
  name: create-access-key
  path: /v1/access-keys
personas: []
provider_name: Sumo Logic
provider_slug: sumo-logic
search_terms:
- list all roles
- user account management
- create a new sumo logic user
- create a new access key
- individual user management
- list all roles for access control management
- create access key
- create a new dashboard
- get a user by id
- get a specific sumo logic user by id
- run a log search query
- analytics
- run log search
- devops
- list all dashboards
- list all sumo logic dashboards
- create a new observability dashboard
- execute a sumo logic log search query with time range
- list all access keys
- delete a user
- create a new user
- create user
- security
- monitoring
- create dashboard
- list access keys
- delete a sumo logic user
- log search execution
- create monitor
- delete user
- role-based access control
- list all users in the organization
- siem
- observability
- create a new role with specific capabilities and filter predicates
- list ingestion budgets for data volume management
- create a new role
- get user
- dashboard management
- access key management
- list all alerting monitors
- create role
- create a new api access key
- list users
- alerting monitors
- list dashboards
- list ingest budgets
- create a new monitor
- create a new alerting monitor with query and trigger conditions
- list all api access keys
- create search job
- list all monitors
- list monitors
- list all users in the sumo logic organization
- logging
- list roles
slug: log-analytics-observability
source_filename: log-analytics-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sumo Logic Log Analytics and Observability\n  description: Workflow capability for DevOps and platform engineering teams using Sumo Logic for log analytics, monitoring,\n    alerting, and security observability. Covers search jobs, dashboards, monitors, user management, and ingestion.\n  tags:\n  - Logging\n  - Observability\n  - Security\n  - Monitoring\n  - Analytics\n  - DevOps\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SUMO_LOGIC_ACCESS_ID: SUMO_LOGIC_ACCESS_ID\n    SUMO_LOGIC_ACCESS_KEY: SUMO_LOGIC_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sumo-logic\n    baseUri: https://api.sumologic.com/api\n    description: Sumo Logic cloud-native log analytics and observability platform API.\n    authentication:\n      type: basic\n      username: '{{SUMO_LOGIC_ACCESS_ID}}'\n      password: '{{SUMO_LOGIC_ACCESS_KEY}}'\n    resources:\n    - name: users\n      path: /v1/users\n\
  \      description: User account management\n      operations:\n      - name: list-users\n        method: GET\n        description: Get A List Of Users\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of users to return\n        - name: token\n          in: query\n          type: string\n          required: false\n          description: Continuation token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create A New User\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            firstName: '{{tools.firstName}}'\n   \
  \         lastName: '{{tools.lastName}}'\n            roleIds: '{{tools.roleIds}}'\n    - name: user\n      path: /v1/users/{id}\n      description: Individual user operations\n      operations:\n      - name: get-user\n        method: GET\n        description: Get A User\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-user\n        method: DELETE\n        description: Delete A User\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles\n      path: /v1/roles\n      description: Role-based access control management\n\
  \      operations:\n      - name: list-roles\n        method: GET\n        description: Get A List Of Roles\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-role\n        method: POST\n        description: Create A New Role\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            filterPredicate: '{{tools.filterPredicate}}'\n    - name: dashboards\n      path: /v2/dashboards\n      description: Dashboard management\n      operations:\n      - name: list-dashboards\n        method: GET\n        description: List Dashboards\n\
  \        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dashboard\n        method: POST\n        description: Create A New Dashboard\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n    - name: monitors\n      path: /v1/monitors\n      description: Alerting and monitoring management\n      operations:\n      - name: list-monitors\n        method: GET\n        description: List All Monitors\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-monitor\n        method: POST\n        description: Create\
  \ A Monitor\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            monitorType: '{{tools.monitorType}}'\n            queries: '{{tools.queries}}'\n            triggers: '{{tools.triggers}}'\n    - name: access-keys\n      path: /v1/accessKeys\n      description: Access key management\n      operations:\n      - name: list-access-keys\n        method: GET\n        description: List All Access Keys\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-access-key\n        method: POST\n        description: Create An Access Key\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n        body:\n          type: json\n          data:\n            label: '{{tools.label}}'\n    - name: search-jobs\n      path: /v1/search/jobs\n      description: Log search job execution\n      operations:\n      - name: create-search-job\n        method: POST\n        description: Create A Search Job\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            from: '{{tools.from}}'\n            to: '{{tools.to}}'\n            timeZone: '{{tools.timeZone}}'\n    - name: ingest-budgets\n      path: /v2/ingestBudgets\n      description: Ingestion budget management\n      operations:\n      - name: list-ingest-budgets\n        method: GET\n        description: Get A List Of Ingest Budgets\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sumo-logic-observability-api\n    description: Unified REST API for Sumo Logic log analytics and observability workflows.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User account management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users in the organization\n        call: sumo-logic.list-users\n        with:\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new user\n        call: sumo-logic.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{id}\n      name: user\n      description: Individual user management\n      operations:\n      - method: GET\n        name: get-user\n        description:\
  \ Get a user by ID\n        call: sumo-logic.get-user\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-user\n        description: Delete a user\n        call: sumo-logic.delete-user\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/roles\n      name: roles\n      description: Role-based access control\n      operations:\n      - method: GET\n        name: list-roles\n        description: List all roles\n        call: sumo-logic.list-roles\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-role\n        description: Create a new role\n        call: sumo-logic.create-role\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors\n      name: monitors\n      description: Alerting monitors\n      operations:\n\
  \      - method: GET\n        name: list-monitors\n        description: List all monitors\n        call: sumo-logic.list-monitors\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-monitor\n        description: Create a new monitor\n        call: sumo-logic.create-monitor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/dashboards\n      name: dashboards\n      description: Dashboard management\n      operations:\n      - method: GET\n        name: list-dashboards\n        description: List all dashboards\n        call: sumo-logic.list-dashboards\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dashboard\n        description: Create a new dashboard\n        call: sumo-logic.create-dashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search-jobs\n      name: search-jobs\n\
  \      description: Log search execution\n      operations:\n      - method: POST\n        name: create-search-job\n        description: Run a log search query\n        call: sumo-logic.create-search-job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/access-keys\n      name: access-keys\n      description: Access key management\n      operations:\n      - method: GET\n        name: list-access-keys\n        description: List all access keys\n        call: sumo-logic.list-access-keys\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-access-key\n        description: Create a new access key\n        call: sumo-logic.create-access-key\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sumo-logic-observability-mcp\n    transport: http\n    description: MCP server for AI-assisted log analytics and observability.\n\
  \    tools:\n    - name: list-users\n      description: List all users in the Sumo Logic organization\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sumo-logic.list-users\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get a specific Sumo Logic user by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sumo-logic.get-user\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new Sumo Logic user\n      hints:\n        readOnly: false\n      call: sumo-logic.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Delete a Sumo Logic user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sumo-logic.delete-user\n\
  \      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-roles\n      description: List all roles for access control management\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sumo-logic.list-roles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-role\n      description: Create a new role with specific capabilities and filter predicates\n      hints:\n        readOnly: false\n      call: sumo-logic.create-role\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-monitors\n      description: List all alerting monitors\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sumo-logic.list-monitors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-monitor\n      description: Create a new alerting monitor with query and trigger conditions\n      hints:\n        readOnly:\
  \ false\n      call: sumo-logic.create-monitor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dashboards\n      description: List all Sumo Logic dashboards\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sumo-logic.list-dashboards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-dashboard\n      description: Create a new observability dashboard\n      hints:\n        readOnly: false\n      call: sumo-logic.create-dashboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-log-search\n      description: Execute a Sumo Logic log search query with time range\n      hints:\n        readOnly: true\n        idempotent: false\n      call: sumo-logic.create-search-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-access-keys\n      description: List all API access keys\n      hints:\n        readOnly: true\n      \
  \  idempotent: true\n      call: sumo-logic.list-access-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-access-key\n      description: Create a new API access key\n      hints:\n        readOnly: false\n      call: sumo-logic.create-access-key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ingest-budgets\n      description: List ingestion budgets for data volume management\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sumo-logic.list-ingest-budgets\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sumo-logic/refs/heads/main/capabilities/log-analytics-observability.yaml
tags:
- Logging
- Observability
- Security
- Monitoring
- Analytics
- DevOps
tools:
- description: List all users in the Sumo Logic organization
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: Get a specific Sumo Logic user by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-user
- description: Create a new Sumo Logic user
  hints:
    readOnly: false
  name: create-user
- description: Delete a Sumo Logic user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-user
- description: List all roles for access control management
  hints:
    idempotent: true
    readOnly: true
  name: list-roles
- description: Create a new role with specific capabilities and filter predicates
  hints:
    readOnly: false
  name: create-role
- description: List all alerting monitors
  hints:
    idempotent: true
    readOnly: true
  name: list-monitors
- description: Create a new alerting monitor with query and trigger conditions
  hints:
    readOnly: false
  name: create-monitor
- description: List all Sumo Logic dashboards
  hints:
    idempotent: true
    readOnly: true
  name: list-dashboards
- description: Create a new observability dashboard
  hints:
    readOnly: false
  name: create-dashboard
- description: Execute a Sumo Logic log search query with time range
  hints:
    idempotent: false
    readOnly: true
  name: run-log-search
- description: List all API access keys
  hints:
    idempotent: true
    readOnly: true
  name: list-access-keys
- description: Create a new API access key
  hints:
    readOnly: false
  name: create-access-key
- description: List ingestion budgets for data volume management
  hints:
    idempotent: true
    readOnly: true
  name: list-ingest-budgets
---

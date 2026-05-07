---
categories: []
consumed_apis: []
description: Workflow capability for database administrators and platform engineers to manage Apache Ignite clusters, execute SQL queries, and configure distributed nodes.
layout: capability
name: Apache Ignite Cluster Management
operations:
- description: Get cluster state
  method: GET
  name: get-cluster-state
  path: /v1/cluster
- description: Execute SQL query
  method: POST
  name: execute-sql
  path: /v1/sql
- description: Get cluster configuration
  method: GET
  name: get-configuration
  path: /v1/configuration
personas: []
provider_name: Apache Ignite
provider_slug: apache-ignite
search_terms:
- get cluster configuration
- Database Administrator
- execute sql query
- in-memory database
- database administration
- dbas who manage ignite cluster health, configuration, and sql workloads
- retrieve the current state and health of the apache ignite cluster
- execute sql
- open source
- engineers who deploy and maintain ignite clusters in production
- retrieve the current apache ignite cluster configuration
- apache ignite
- update apache ignite cluster configuration parameters
- Platform Engineer
- sql
- get configuration
- initialize a new apache ignite cluster
- in-memory
- compute grid
- cluster management
- update configuration
- database administrators and platform engineers managing ignite clusters
- distributed database
- execute sql queries on the distributed ignite cluster
- init cluster
- caching
- get cluster state
slug: cluster-management
source_filename: cluster-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Ignite Cluster Management\n  description: Workflow capability for database administrators and platform engineers to manage Apache Ignite clusters, execute\n    SQL queries, and configure distributed nodes.\n  tags:\n  - Apache Ignite\n  - Cluster Management\n  - Database Administration\n  - In-Memory Database\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    IGNITE_BASIC_AUTH: IGNITE_BASIC_AUTH\ncapability:\n  consumes:\n  - type: http\n    namespace: ignite-rest-api\n    baseUri: http://localhost:10300\n    description: Apache Ignite 3 REST API for cluster and node management.\n    authentication:\n      type: basic\n      username: '{{IGNITE_USER}}'\n      password: '{{IGNITE_PASSWORD}}'\n    resources:\n    - name: cluster\n      path: /management/v1/cluster\n      description: Cluster lifecycle management\n      operations:\n      - name: get-cluster-state\n        method: GET\n     \
  \   description: Get cluster state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: init-cluster\n        method: POST\n        description: Initialize cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sql\n      path: /management/v1/sql\n      description: SQL query execution\n      operations:\n      - name: execute-sql\n        method: POST\n        description: Execute SQL query\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: SQL query to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration\n      path: /management/v1/configuration\n      description: Cluster configuration management\n      operations:\n\
  \      - name: get-configuration\n        method: GET\n        description: Get cluster configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-configuration\n        method: PATCH\n        description: Update cluster configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ignite-cluster-management-api\n    description: Unified REST API for Apache Ignite cluster management.\n    resources:\n    - path: /v1/cluster\n      name: cluster\n      operations:\n      - method: GET\n        name: get-cluster-state\n        description: Get cluster state\n        call: ignite-rest-api.get-cluster-state\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sql\n      name: sql\n      operations:\n      - method:\
  \ POST\n        name: execute-sql\n        description: Execute SQL query\n        call: ignite-rest-api.execute-sql\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/configuration\n      name: configuration\n      operations:\n      - method: GET\n        name: get-configuration\n        description: Get cluster configuration\n        call: ignite-rest-api.get-configuration\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ignite-cluster-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache Ignite cluster management.\n    tools:\n    - name: get-cluster-state\n      description: Retrieve the current state and health of the Apache Ignite cluster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ignite-rest-api.get-cluster-state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: init-cluster\n\
  \      description: Initialize a new Apache Ignite cluster\n      hints:\n        readOnly: false\n      call: ignite-rest-api.init-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-sql\n      description: Execute SQL queries on the distributed Ignite cluster\n      hints:\n        readOnly: false\n      call: ignite-rest-api.execute-sql\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-configuration\n      description: Retrieve the current Apache Ignite cluster configuration\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ignite-rest-api.get-configuration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-configuration\n      description: Update Apache Ignite cluster configuration parameters\n      hints:\n        readOnly: false\n        idempotent: true\n      call: ignite-rest-api.update-configuration\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-ignite/refs/heads/main/capabilities/cluster-management.yaml
tags:
- Apache Ignite
- Cluster Management
- Database Administration
- In-Memory Database
tools:
- description: Retrieve the current state and health of the Apache Ignite cluster
  hints:
    openWorld: true
    readOnly: true
  name: get-cluster-state
- description: Initialize a new Apache Ignite cluster
  hints:
    readOnly: false
  name: init-cluster
- description: Execute SQL queries on the distributed Ignite cluster
  hints:
    readOnly: false
  name: execute-sql
- description: Retrieve the current Apache Ignite cluster configuration
  hints:
    openWorld: true
    readOnly: true
  name: get-configuration
- description: Update Apache Ignite cluster configuration parameters
  hints:
    idempotent: true
    readOnly: false
  name: update-configuration
---

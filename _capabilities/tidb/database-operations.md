---
categories: []
consumed_apis: []
description: Unified capability for database administrators and developers to manage TiDB Cloud clusters, backups, and data imports alongside executing SQL queries via the Data Service API. Covers cluster lifecycle management, backup scheduling, and data access workflows.
layout: capability
name: TiDB Cloud Database Operations
operations:
- description: List all TiDB Cloud clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Get details for a specific cluster
  method: GET
  name: get-cluster
  path: /v1/clusters/{clusterId}
- description: List backups for a cluster
  method: GET
  name: list-backups
  path: /v1/clusters/{clusterId}/backups
- description: List data import tasks for a cluster
  method: GET
  name: list-imports
  path: /v1/clusters/{clusterId}/imports
- description: Execute a natural language query against a TiDB database
  method: POST
  name: chat2query
  path: /v1/query
personas: []
provider_name: tidb
provider_slug: tidb
search_terms:
- list backups for a cluster
- get cluster
- list all tidb cloud clusters across projects
- ai-powered sql queries
- individual cluster details
- list cluster backups
- list import tasks
- execute a natural language instruction against a tidb cloud database. the ai generates and runs sql automatically. ideal for ad-hoc analysis.
- list data import tasks for a cluster
- data import tasks
- get details for a specific cluster
- distributed sql
- list clusters
- query with natural language
- execute a natural language query against a tidb database
- chat2query
- tidb cloud cluster management
- cluster management
- list imports
- create a manual backup for a tidb cloud cluster
- database
- list backups
- cloud
- get detailed configuration and status for a specific tidb cloud cluster
- cluster backups
- tidb
- data access
- list all tidb cloud clusters
- list data import tasks for a tidb cloud cluster
- create backup
- list all backups for a tidb cloud cluster
slug: database-operations
source_filename: database-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TiDB Cloud Database Operations\n  description: Unified capability for database administrators and developers to manage TiDB Cloud clusters, backups, and data\n    imports alongside executing SQL queries via the Data Service API. Covers cluster lifecycle management, backup scheduling,\n    and data access workflows.\n  tags:\n  - TiDB\n  - Cloud\n  - Database\n  - Cluster Management\n  - Data Access\n  - Distributed SQL\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TIDB_CLOUD_PUBLIC_KEY: TIDB_CLOUD_PUBLIC_KEY\n    TIDB_CLOUD_PRIVATE_KEY: TIDB_CLOUD_PRIVATE_KEY\n    TIDB_DATA_APP_API_KEY: TIDB_DATA_APP_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: tidb-cloud\n    baseUri: https://api.tidbcloud.com\n    description: TiDB Cloud management REST API with digest authentication\n    authentication:\n      type: basic\n      username: '{{TIDB_CLOUD_PUBLIC_KEY}}'\n      password: '{{TIDB_CLOUD_PRIVATE_KEY}}'\n\
  \    resources:\n    - name: clusters\n      path: /api/v1beta/clusters\n      description: TiDB cluster management\n      operations:\n      - name: list-clusters\n        method: GET\n        description: List all TiDB Cloud clusters\n        inputParameters:\n        - name: projectId\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cluster\n        method: POST\n        description: Create a new TiDB Cloud cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n\
  \            cluster_type: '{{tools.cluster_type}}'\n            cloud_provider: '{{tools.cloud_provider}}'\n            region: '{{tools.region}}'\n            config: '{{tools.config}}'\n      - name: get-cluster\n        method: GET\n        description: Get details for a specific cluster\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-cluster\n        method: DELETE\n        description: Delete a TiDB Cloud cluster\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: backups\n      path: /api/v1beta/clusters/{clusterId}/backups\n      description: Cluster\
  \ backup management\n      operations:\n      - name: list-backups\n        method: GET\n        description: List backups for a cluster\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-backup\n        method: POST\n        description: Create a manual backup for a cluster\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: imports\n      path: /api/v1beta/clusters/{clusterId}/imports\n      description: Data import tasks\n      operations:\n      - name: list-imports\n \
  \       method: GET\n        description: List import tasks for a cluster\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: tidb-data-service\n    baseUri: https://data.tidbcloud.com\n    description: TiDB Cloud Data Service for custom SQL-backed API endpoints\n    authentication:\n      type: bearer\n      token: '{{TIDB_DATA_APP_API_KEY}}'\n    resources:\n    - name: endpoints\n      path: /api/v1beta/app/{dataAppId}/endpoint/{endpointPath}\n      description: Custom Data App endpoints\n      operations:\n      - name: call-endpoint\n        method: GET\n        description: Call a custom Data App GET endpoint\n        inputParameters:\n        - name: dataAppId\n          in: path\n          type: string\n          required: true\n        - name: endpointPath\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chat2data\n      path: /api/v1beta/app/{dataAppId}/endpoint/chat2data\n      description: AI-powered natural language to SQL\n      operations:\n      - name: chat2query\n        method: POST\n        description: Generate and execute SQL from natural language instruction\n        inputParameters:\n        - name: dataAppId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cluster_id: '{{tools.cluster_id}}'\n            database: '{{tools.database}}'\n            instruction: '{{tools.instruction}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tidb-operations-api\n\
  \    description: Unified REST API for TiDB Cloud cluster management and data service operations.\n    resources:\n    - path: /v1/clusters\n      name: clusters\n      description: TiDB Cloud cluster management\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List all TiDB Cloud clusters\n        call: tidb-cloud.list-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{clusterId}\n      name: cluster-detail\n      description: Individual cluster details\n      operations:\n      - method: GET\n        name: get-cluster\n        description: Get details for a specific cluster\n        call: tidb-cloud.get-cluster\n        with:\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{clusterId}/backups\n      name: cluster-backups\n      description: Cluster backups\n      operations:\n      - method: GET\n\
  \        name: list-backups\n        description: List backups for a cluster\n        call: tidb-cloud.list-backups\n        with:\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{clusterId}/imports\n      name: cluster-imports\n      description: Data import tasks\n      operations:\n      - method: GET\n        name: list-imports\n        description: List data import tasks for a cluster\n        call: tidb-cloud.list-imports\n        with:\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/query\n      name: natural-language-query\n      description: AI-powered SQL queries\n      operations:\n      - method: POST\n        name: chat2query\n        description: Execute a natural language query against a TiDB database\n        call: tidb-data-service.chat2query\n        with:\n          cluster_id: rest.cluster_id\n     \
  \     database: rest.database\n          instruction: rest.instruction\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tidb-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted TiDB Cloud database operations and data access.\n    tools:\n    - name: list-clusters\n      description: List all TiDB Cloud clusters across projects\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tidb-cloud.list-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster\n      description: Get detailed configuration and status for a specific TiDB Cloud cluster\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tidb-cloud.get-cluster\n      with:\n        clusterId: tools.clusterId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cluster-backups\n      description: List all backups\
  \ for a TiDB Cloud cluster\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tidb-cloud.list-backups\n      with:\n        clusterId: tools.clusterId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-backup\n      description: Create a manual backup for a TiDB Cloud cluster\n      hints:\n        readOnly: false\n        idempotent: false\n      call: tidb-cloud.create-backup\n      with:\n        clusterId: tools.clusterId\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-import-tasks\n      description: List data import tasks for a TiDB Cloud cluster\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tidb-cloud.list-imports\n      with:\n        clusterId: tools.clusterId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-with-natural-language\n      description: Execute a natural language instruction\
  \ against a TiDB Cloud database. The AI generates and runs SQL automatically.\n        Ideal for ad-hoc analysis.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tidb-data-service.chat2query\n      with:\n        cluster_id: tools.cluster_id\n        database: tools.database\n        instruction: tools.instruction\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tidb/refs/heads/main/capabilities/database-operations.yaml
tags:
- TiDB
- Cloud
- Database
- Cluster Management
- Data Access
- Distributed SQL
tools:
- description: List all TiDB Cloud clusters across projects
  hints:
    openWorld: false
    readOnly: true
  name: list-clusters
- description: Get detailed configuration and status for a specific TiDB Cloud cluster
  hints:
    openWorld: false
    readOnly: true
  name: get-cluster
- description: List all backups for a TiDB Cloud cluster
  hints:
    openWorld: false
    readOnly: true
  name: list-cluster-backups
- description: Create a manual backup for a TiDB Cloud cluster
  hints:
    idempotent: false
    readOnly: false
  name: create-backup
- description: List data import tasks for a TiDB Cloud cluster
  hints:
    openWorld: false
    readOnly: true
  name: list-import-tasks
- description: Execute a natural language instruction against a TiDB Cloud database. The AI generates and runs SQL automatically. Ideal for ad-hoc analysis.
  hints:
    openWorld: false
    readOnly: true
  name: query-with-natural-language
---

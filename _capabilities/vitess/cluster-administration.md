---
categories: []
consumed_apis: []
description: Workflow capability for administering Vitess database clusters via the VTAdmin API. Combines cluster topology inspection, tablet management, keyspace and schema administration, VReplication workflow monitoring, backup auditing, and VTGate management into a unified interface. Used by database administrators, site reliability engineers, and platform engineers managing large-scale MySQL deployments on Kubernetes.
layout: capability
name: Vitess Cluster Administration
operations:
- description: List all registered Vitess clusters
  method: GET
  name: get-clusters
  path: /v1/clusters
- description: List all VTTablet instances with cluster and shard info
  method: GET
  name: get-tablets
  path: /v1/tablets
- description: Get details of a specific tablet by alias
  method: GET
  name: get-tablet
  path: /v1/tablets/{tablet}
- description: List all keyspaces across clusters
  method: GET
  name: get-keyspaces
  path: /v1/keyspaces
- description: List all keyspace schemas
  method: GET
  name: get-schemas
  path: /v1/schemas
- description: Get table definitions for a keyspace
  method: GET
  name: get-schema
  path: /v1/schemas/{cluster_id}/{keyspace}
- description: List all VReplication workflows
  method: GET
  name: get-workflows
  path: /v1/workflows
- description: List all tablet backups
  method: GET
  name: get-backups
  path: /v1/backups
- description: List all cells across clusters
  method: GET
  name: get-cells
  path: /v1/cells
- description: List all VTGate instances
  method: GET
  name: get-gates
  path: /v1/gates
- description: Get complete topology for a cluster
  method: GET
  name: get-cluster-topology
  path: /v1/topology/{cluster_id}
personas: []
provider_name: Vitess
provider_slug: vitess
search_terms:
- get the complete topology of a vitess cluster including all keyspaces, shards, and tablets
- full cluster topology
- get cluster topology
- individual tablet details
- distributed systems
- registered vitess clusters
- availability zones and data centers
- get table definitions and index information for a specific keyspace
- list all cells across clusters
- get keyspaces
- tablet backup inventory
- list all vttablet instances with cluster and shard info
- list all keyspace schemas
- list all keyspaces across clusters
- vttablet instances
- get table definitions for a keyspace
- get cells
- get gates
- cluster management
- get tablets
- vtgate proxy instances
- list all vreplication workflows
- cloud native
- get complete topology for a cluster
- list all cells (availability zones and data center locations) across clusters
- list database schemas for all keyspaces across clusters
- database
- vreplication workflows
- list all vitess keyspaces (logical databases) and their sharding configuration
- sharding
- get clusters
- get schema
- mysql
- schema for a specific keyspace
- get backups
- cncf
- get schemas
- list all registered vitess clusters and their identifiers
- backups
- get workflows
- get detailed information about a specific tablet including health and replication status
- database schemas for all keyspaces
- vitess keyspaces (logical databases)
- list all vttablet instances with type (primary/replica), shard, keyspace, and state
- vitess
- get details of a specific tablet by alias
- list all registered vitess clusters
- list all tablet backups
- list all tablet backups to audit backup coverage and find latest backup per shard
- list all vtgate proxy instances and their configured keyspaces
- list all vtgate instances
- graduated
- list vreplication workflows including movetables, reshard, and materialize operations
- get tablet
slug: cluster-administration
source_filename: cluster-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vitess Cluster Administration\n  description: Workflow capability for administering Vitess database clusters via the VTAdmin API. Combines cluster topology\n    inspection, tablet management, keyspace and schema administration, VReplication workflow monitoring, backup auditing,\n    and VTGate management into a unified interface. Used by database administrators, site reliability engineers, and platform\n    engineers managing large-scale MySQL deployments on Kubernetes.\n  tags:\n  - Backups\n  - Cluster Management\n  - Cloud Native\n  - CNCF\n  - Database\n  - Distributed Systems\n  - MySQL\n  - Sharding\n  - Vitess\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VTADMIN_TOKEN: VTADMIN_TOKEN\n    VTADMIN_HOST: VTADMIN_HOST\n    VTADMIN_PORT: VTADMIN_PORT\ncapability:\n  consumes:\n  - type: http\n    namespace: vitess-vtadmin\n    baseUri: http://{{VTADMIN_HOST}}:{{VTADMIN_PORT}}/api\n    description:\
  \ Vitess VTAdmin REST API for cluster administration\n    authentication:\n      type: bearer\n      token: '{{VTADMIN_TOKEN}}'\n    resources:\n    - name: clusters\n      path: /clusters\n      description: Vitess cluster listing\n      operations:\n      - name: get-clusters\n        method: GET\n        description: List all registered Vitess clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tablets\n      path: /tablets\n      description: VTTablet instance management\n      operations:\n      - name: get-tablets\n        method: GET\n        description: List all VTTablet instances\n        inputParameters:\n        - name: cluster_id\n          in: query\n          type: array\n          required: false\n          description: Filter by cluster IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ tablet\n      path: /tablet/{tablet}\n      description: Individual tablet operations\n      operations:\n      - name: get-tablet\n        method: GET\n        description: Get a specific tablet by alias\n        inputParameters:\n        - name: tablet\n          in: path\n          type: string\n          required: true\n          description: Tablet alias (cluster/cell-uid)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: keyspaces\n      path: /keyspaces\n      description: Keyspace listing\n      operations:\n      - name: get-keyspaces\n        method: GET\n        description: List all keyspaces\n        inputParameters:\n        - name: cluster_id\n          in: query\n          type: array\n          required: false\n          description: Filter by cluster IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: schemas\n      path: /schemas\n      description: Database schema listing\n      operations:\n      - name: get-schemas\n        method: GET\n        description: List all keyspace schemas\n        inputParameters:\n        - name: cluster_id\n          in: query\n          type: array\n          required: false\n          description: Filter by cluster IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema\n      path: /schema/{cluster_id}/{keyspace}\n      description: Per-keyspace schema\n      operations:\n      - name: get-schema\n        method: GET\n        description: Get schema for a specific keyspace\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier\n        - name: keyspace\n          in: path\n          type: string\n          required: true\n       \
  \   description: Keyspace name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows\n      path: /workflows\n      description: VReplication workflow listing\n      operations:\n      - name: get-workflows\n        method: GET\n        description: List all VReplication workflows\n        inputParameters:\n        - name: cluster_id\n          in: query\n          type: array\n          required: false\n          description: Filter by cluster IDs\n        - name: active_only\n          in: query\n          type: boolean\n          required: false\n          description: Return only active workflows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: backups\n      path: /backups\n      description: Tablet backup listing\n      operations:\n      - name: get-backups\n        method: GET\n        description:\
  \ List all tablet backups\n        inputParameters:\n        - name: cluster_id\n          in: query\n          type: array\n          required: false\n          description: Filter by cluster IDs\n        - name: keyspace\n          in: query\n          type: string\n          required: false\n          description: Filter by keyspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cells\n      path: /cells\n      description: Cell listing\n      operations:\n      - name: get-cells\n        method: GET\n        description: List all cells (availability zones)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gates\n      path: /gates\n      description: VTGate instance listing\n      operations:\n      - name: get-gates\n        method: GET\n        description: List all VTGate instances\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topology\n      path: /topology/{cluster_id}\n      description: Cluster topology\n      operations:\n      - name: get-cluster-topology\n        method: GET\n        description: Get full cluster topology\n        inputParameters:\n        - name: cluster_id\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vitess-cluster-admin-api\n    description: Unified REST API for Vitess cluster administration and observability.\n    resources:\n    - path: /v1/clusters\n      name: clusters\n      description: Registered Vitess clusters\n      operations:\n      - method: GET\n        name: get-clusters\n        description: List all registered\
  \ Vitess clusters\n        call: vitess-vtadmin.get-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tablets\n      name: tablets\n      description: VTTablet instances\n      operations:\n      - method: GET\n        name: get-tablets\n        description: List all VTTablet instances with cluster and shard info\n        call: vitess-vtadmin.get-tablets\n        with:\n          cluster_id: rest.cluster_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tablets/{tablet}\n      name: tablet\n      description: Individual tablet details\n      operations:\n      - method: GET\n        name: get-tablet\n        description: Get details of a specific tablet by alias\n        call: vitess-vtadmin.get-tablet\n        with:\n          tablet: rest.tablet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/keyspaces\n      name: keyspaces\n      description: Vitess\
  \ keyspaces (logical databases)\n      operations:\n      - method: GET\n        name: get-keyspaces\n        description: List all keyspaces across clusters\n        call: vitess-vtadmin.get-keyspaces\n        with:\n          cluster_id: rest.cluster_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/schemas\n      name: schemas\n      description: Database schemas for all keyspaces\n      operations:\n      - method: GET\n        name: get-schemas\n        description: List all keyspace schemas\n        call: vitess-vtadmin.get-schemas\n        with:\n          cluster_id: rest.cluster_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/schemas/{cluster_id}/{keyspace}\n      name: schema\n      description: Schema for a specific keyspace\n      operations:\n      - method: GET\n        name: get-schema\n        description: Get table definitions for a keyspace\n        call: vitess-vtadmin.get-schema\n\
  \        with:\n          cluster_id: rest.cluster_id\n          keyspace: rest.keyspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows\n      name: workflows\n      description: VReplication workflows\n      operations:\n      - method: GET\n        name: get-workflows\n        description: List all VReplication workflows\n        call: vitess-vtadmin.get-workflows\n        with:\n          cluster_id: rest.cluster_id\n          active_only: rest.active_only\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/backups\n      name: backups\n      description: Tablet backup inventory\n      operations:\n      - method: GET\n        name: get-backups\n        description: List all tablet backups\n        call: vitess-vtadmin.get-backups\n        with:\n          cluster_id: rest.cluster_id\n          keyspace: rest.keyspace\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/cells\n      name: cells\n      description: Availability zones and data centers\n      operations:\n      - method: GET\n        name: get-cells\n        description: List all cells across clusters\n        call: vitess-vtadmin.get-cells\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gates\n      name: gates\n      description: VTGate proxy instances\n      operations:\n      - method: GET\n        name: get-gates\n        description: List all VTGate instances\n        call: vitess-vtadmin.get-gates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/topology/{cluster_id}\n      name: topology\n      description: Full cluster topology\n      operations:\n      - method: GET\n        name: get-cluster-topology\n        description: Get complete topology for a cluster\n        call: vitess-vtadmin.get-cluster-topology\n        with:\n          cluster_id: rest.cluster_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vitess-cluster-admin-mcp\n    transport: http\n    description: MCP server for AI-assisted Vitess cluster administration and troubleshooting.\n    tools:\n    - name: get-clusters\n      description: List all registered Vitess clusters and their identifiers\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vitess-vtadmin.get-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tablets\n      description: List all VTTablet instances with type (PRIMARY/REPLICA), shard, keyspace, and state\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vitess-vtadmin.get-tablets\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tablet\n      description: Get detailed information about a specific tablet including health and replication\
  \ status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vitess-vtadmin.get-tablet\n      with:\n        tablet: tools.tablet\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-keyspaces\n      description: List all Vitess keyspaces (logical databases) and their sharding configuration\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vitess-vtadmin.get-keyspaces\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-schemas\n      description: List database schemas for all keyspaces across clusters\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vitess-vtadmin.get-schemas\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-schema\n      description: Get table definitions and index information for a specific\
  \ keyspace\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vitess-vtadmin.get-schema\n      with:\n        cluster_id: tools.cluster_id\n        keyspace: tools.keyspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workflows\n      description: List VReplication workflows including MoveTables, Reshard, and Materialize operations\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vitess-vtadmin.get-workflows\n      with:\n        cluster_id: tools.cluster_id\n        active_only: tools.active_only\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-backups\n      description: List all tablet backups to audit backup coverage and find latest backup per shard\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vitess-vtadmin.get-backups\n      with:\n        cluster_id: tools.cluster_id\n        keyspace: tools.keyspace\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-cells\n      description: List all cells (availability zones and data center locations) across clusters\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vitess-vtadmin.get-cells\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-gates\n      description: List all VTGate proxy instances and their configured keyspaces\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vitess-vtadmin.get-gates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster-topology\n      description: Get the complete topology of a Vitess cluster including all keyspaces, shards, and tablets\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vitess-vtadmin.get-cluster-topology\n      with:\n        cluster_id: tools.cluster_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vitess/refs/heads/main/capabilities/cluster-administration.yaml
tags:
- Backups
- Cluster Management
- Cloud Native
- CNCF
- Database
- Distributed Systems
- MySQL
- Sharding
- Vitess
tools:
- description: List all registered Vitess clusters and their identifiers
  hints:
    idempotent: true
    readOnly: true
  name: get-clusters
- description: List all VTTablet instances with type (PRIMARY/REPLICA), shard, keyspace, and state
  hints:
    idempotent: true
    readOnly: true
  name: get-tablets
- description: Get detailed information about a specific tablet including health and replication status
  hints:
    idempotent: true
    readOnly: true
  name: get-tablet
- description: List all Vitess keyspaces (logical databases) and their sharding configuration
  hints:
    idempotent: true
    readOnly: true
  name: get-keyspaces
- description: List database schemas for all keyspaces across clusters
  hints:
    idempotent: true
    readOnly: true
  name: get-schemas
- description: Get table definitions and index information for a specific keyspace
  hints:
    idempotent: true
    readOnly: true
  name: get-schema
- description: List VReplication workflows including MoveTables, Reshard, and Materialize operations
  hints:
    idempotent: true
    readOnly: true
  name: get-workflows
- description: List all tablet backups to audit backup coverage and find latest backup per shard
  hints:
    idempotent: true
    readOnly: true
  name: get-backups
- description: List all cells (availability zones and data center locations) across clusters
  hints:
    idempotent: true
    readOnly: true
  name: get-cells
- description: List all VTGate proxy instances and their configured keyspaces
  hints:
    idempotent: true
    readOnly: true
  name: get-gates
- description: Get the complete topology of a Vitess cluster including all keyspaces, shards, and tablets
  hints:
    idempotent: true
    readOnly: true
  name: get-cluster-topology
---

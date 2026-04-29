---
categories: []
consumed_apis: []
description: Workflow capability for managing Amazon Aurora relational database clusters including creation, scaling, snapshots, and global database configurations.
layout: capability
name: Relational Database Management Workflow
operations:
- description: Create a new Aurora DB cluster
  method: POST
  name: create-db-cluster
  path: /v1/clusters
- description: List Aurora DB clusters
  method: GET
  name: describe-db-clusters
  path: /v1/clusters
personas: []
provider_name: Amazon Aurora
provider_slug: amazon-aurora
search_terms:
- create db cluster
- list all db instances in aurora clusters.
- relational database
- mysql
- create a snapshot of an aurora db cluster for backup or cloning.
- modify db cluster
- list all aurora db clusters to understand available databases and their status.
- restore an aurora db cluster from a snapshot for disaster recovery.
- create a new aurora db cluster
- restore db cluster from snapshot
- stop an aurora db cluster to reduce costs when not in use.
- describe db clusters
- describe db instances
- aurora db cluster management
- aws
- describe db cluster snapshots
- modify the configuration of an existing aurora db cluster.
- list aurora db clusters
- postgresql
- start db cluster
- list available aurora db cluster snapshots for backup management.
- create db instance
- start a stopped aurora db cluster to resume database operations.
- amazon aurora
- add a new read replica or writer instance to an aurora db cluster.
- create db cluster snapshot
- stop db cluster
- create a new aurora mysql or postgresql compatible db cluster.
slug: relational-database-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Relational Database Management Workflow\n  description: Workflow capability for managing Amazon Aurora relational database clusters including creation, scaling, snapshots, and global database configurations.\n  tags:\n    - Amazon Aurora\n    - MySQL\n    - PostgreSQL\n    - Relational Database\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nimports:\n  - namespace: aurora\n    from: shared/aurora-api.yaml\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: relational-db-rest\n      resources:\n        - path: /v1/clusters\n          name: clusters\n          description: Aurora DB cluster management\n          operations:\n            - method: POST\n              name: create-db-cluster\n              description: Create a new Aurora DB cluster\n              call: \"aurora.create-db-cluster\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n            - method: GET\n              name: describe-db-clusters\n              description: List Aurora DB clusters\n              call: \"aurora.describe-db-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: relational-db-mcp\n      transport: http\n      tools:\n        - name: describe-db-clusters\n          description: List all Aurora DB clusters to understand available databases and their status.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aurora.describe-db-clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-db-cluster\n          description: Create a new Aurora MySQL or PostgreSQL compatible DB cluster.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"aurora.create-db-cluster\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: modify-db-cluster\n          description: Modify the configuration of an existing Aurora DB cluster.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"aurora.modify-db-cluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-db-cluster\n          description: Start a stopped Aurora DB cluster to resume database operations.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"aurora.start-db-cluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stop-db-cluster\n          description: Stop an Aurora DB cluster to reduce costs when not in use.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"aurora.stop-db-cluster\"\n         \
  \ outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-db-instance\n          description: Add a new read replica or writer instance to an Aurora DB cluster.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"aurora.create-db-instance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-db-instances\n          description: List all DB instances in Aurora clusters.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aurora.describe-db-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-db-cluster-snapshot\n          description: Create a snapshot of an Aurora DB cluster for backup or cloning.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"aurora.create-db-cluster-snapshot\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-db-cluster-snapshots\n          description: List available Aurora DB cluster snapshots for backup management.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aurora.describe-db-cluster-snapshots\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: restore-db-cluster-from-snapshot\n          description: Restore an Aurora DB cluster from a snapshot for disaster recovery.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"aurora.restore-db-cluster-from-snapshot\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\npersonas:\n  - name: Database Administrator\n    description: Manages Aurora DB clusters, instances, parameter groups, and backup configurations.\n    tools:\n      - describe-db-clusters\n\
  \      - create-db-cluster\n      - modify-db-cluster\n      - start-db-cluster\n      - stop-db-cluster\n      - create-db-instance\n      - describe-db-instances\n      - create-db-cluster-snapshot\n      - describe-db-cluster-snapshots\n\n  - name: Cloud Architect\n    description: Designs multi-region Aurora architectures and manages global database deployments.\n    tools:\n      - describe-db-clusters\n      - create-db-cluster\n      - restore-db-cluster-from-snapshot\n      - describe-db-cluster-snapshots\n      - describe-db-instances\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-aurora/refs/heads/main/capabilities/relational-database-management.yaml
tags:
- Amazon Aurora
- MySQL
- PostgreSQL
- Relational Database
- AWS
tools:
- description: List all Aurora DB clusters to understand available databases and their status.
  hints:
    openWorld: true
    readOnly: true
  name: describe-db-clusters
- description: Create a new Aurora MySQL or PostgreSQL compatible DB cluster.
  hints:
    openWorld: false
    readOnly: false
  name: create-db-cluster
- description: Modify the configuration of an existing Aurora DB cluster.
  hints:
    openWorld: false
    readOnly: false
  name: modify-db-cluster
- description: Start a stopped Aurora DB cluster to resume database operations.
  hints:
    openWorld: false
    readOnly: false
  name: start-db-cluster
- description: Stop an Aurora DB cluster to reduce costs when not in use.
  hints:
    openWorld: false
    readOnly: false
  name: stop-db-cluster
- description: Add a new read replica or writer instance to an Aurora DB cluster.
  hints:
    openWorld: false
    readOnly: false
  name: create-db-instance
- description: List all DB instances in Aurora clusters.
  hints:
    openWorld: true
    readOnly: true
  name: describe-db-instances
- description: Create a snapshot of an Aurora DB cluster for backup or cloning.
  hints:
    openWorld: false
    readOnly: false
  name: create-db-cluster-snapshot
- description: List available Aurora DB cluster snapshots for backup management.
  hints:
    openWorld: true
    readOnly: true
  name: describe-db-cluster-snapshots
- description: Restore an Aurora DB cluster from a snapshot for disaster recovery.
  hints:
    openWorld: false
    readOnly: false
  name: restore-db-cluster-from-snapshot
---

---
categories: []
consumed_apis: []
description: Workflow capability for creating and managing distributed SQL clusters with Amazon Aurora DSQL including multi-region configurations.
layout: capability
name: Distributed SQL Management Workflow
operations:
- description: Create a new cluster
  method: POST
  name: create-cluster
  path: /v1/clusters
- description: List all clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
personas: []
provider_name: Amazon Aurora DSQL
provider_slug: amazon-aurora-dsql
search_terms:
- delete an aurora dsql cluster when it is no longer needed.
- delete cluster
- amazon aurora dsql
- get the postgresql-compatible connection endpoint for an aurora dsql cluster.
- get the current status and configuration of an aurora dsql cluster.
- list clusters
- aws
- serverless
- get cluster endpoint
- distributed sql cluster management
- distributed sql
- update the configuration of an aurora dsql cluster.
- list all clusters
- create cluster
- create a new aurora dsql cluster for distributed sql workloads.
- update cluster
- create linked aurora dsql clusters across multiple aws regions for global distribution.
- create multi region clusters
- create a new cluster
- list all aurora dsql clusters to understand available databases.
- get cluster
- postgresql
slug: distributed-sql-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Distributed SQL Management Workflow\n  description: Workflow capability for creating and managing distributed SQL clusters with Amazon Aurora DSQL including multi-region configurations.\n  tags:\n    - Amazon Aurora DSQL\n    - Distributed SQL\n    - PostgreSQL\n    - Serverless\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nimports:\n  - namespace: dsql\n    from: shared/aurora-dsql-api.yaml\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: distributed-sql-rest\n      resources:\n        - path: /v1/clusters\n          name: clusters\n          description: Distributed SQL cluster management\n          operations:\n            - method: POST\n              name: create-cluster\n              description: Create a new cluster\n              call: \"dsql.create-cluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n       \
  \     - method: GET\n              name: list-clusters\n              description: List all clusters\n              call: \"dsql.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: distributed-sql-mcp\n      transport: http\n      tools:\n        - name: list-clusters\n          description: List all Aurora DSQL clusters to understand available databases.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dsql.list-clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-cluster\n          description: Create a new Aurora DSQL cluster for distributed SQL workloads.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"dsql.create-cluster\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: get-cluster\n          description: Get the current status and configuration of an Aurora DSQL cluster.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dsql.get-cluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-cluster-endpoint\n          description: Get the PostgreSQL-compatible connection endpoint for an Aurora DSQL cluster.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dsql.get-cluster-endpoint\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-cluster\n          description: Update the configuration of an Aurora DSQL cluster.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"dsql.update-cluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n\n        - name: create-multi-region-clusters\n          description: Create linked Aurora DSQL clusters across multiple AWS regions for global distribution.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"dsql.create-multi-region-clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-cluster\n          description: Delete an Aurora DSQL cluster when it is no longer needed.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"dsql.delete-cluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\npersonas:\n  - name: Database Administrator\n    description: Manages Aurora DSQL clusters for transactional workloads and configures cluster properties.\n    tools:\n      - list-clusters\n      - create-cluster\n      - get-cluster\n      - get-cluster-endpoint\n      - update-cluster\n   \
  \   - delete-cluster\n\n  - name: Cloud Architect\n    description: Designs and deploys multi-region distributed SQL architectures for global applications.\n    tools:\n      - list-clusters\n      - create-multi-region-clusters\n      - get-cluster\n      - get-cluster-endpoint\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-aurora-dsql/refs/heads/main/capabilities/distributed-sql-management.yaml
tags:
- Amazon Aurora DSQL
- Distributed SQL
- PostgreSQL
- Serverless
- AWS
tools:
- description: List all Aurora DSQL clusters to understand available databases.
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: Create a new Aurora DSQL cluster for distributed SQL workloads.
  hints:
    openWorld: false
    readOnly: false
  name: create-cluster
- description: Get the current status and configuration of an Aurora DSQL cluster.
  hints:
    openWorld: true
    readOnly: true
  name: get-cluster
- description: Get the PostgreSQL-compatible connection endpoint for an Aurora DSQL cluster.
  hints:
    openWorld: true
    readOnly: true
  name: get-cluster-endpoint
- description: Update the configuration of an Aurora DSQL cluster.
  hints:
    openWorld: false
    readOnly: false
  name: update-cluster
- description: Create linked Aurora DSQL clusters across multiple AWS regions for global distribution.
  hints:
    openWorld: false
    readOnly: false
  name: create-multi-region-clusters
- description: Delete an Aurora DSQL cluster when it is no longer needed.
  hints:
    openWorld: false
    readOnly: false
  name: delete-cluster
---

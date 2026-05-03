---
categories: []
consumed_apis:
- goldengate-veridata
- goldengate-rest
description: Unified workflow for verifying data consistency between source and target databases. Combines Veridata for data comparison and repair with core GoldenGate monitoring for data quality engineers and DBAs ensuring replication integrity.
layout: capability
name: Oracle GoldenGate Data Verification
operations:
- description: List Veridata database connections
  method: GET
  name: list-connections
  path: /v1/connections
- description: List compare groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: List comparison jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: List replication process performance metrics
  method: GET
  name: list-process-metrics
  path: /v1/metrics
personas: []
provider_name: Oracle GoldenGate
provider_slug: oracle-goldengate
search_terms:
- repair job
- get comparison job statistics
- data synchronization
- create a new veridata database connection
- list connections
- run job
- database connections for verification
- cdc
- list compare groups
- comparison jobs
- replication process metrics
- create group
- get details of out-of-sync data
- get out of sync data
- list jobs
- get goldengate process performance metrics for monitoring replication health
- execute a comparison job
- list comparison jobs
- data verification
- data integration
- list compare groups for data verification
- enterprise
- compliance
- database
- compare groups
- create a new comparison job
- create connection
- repair out-of-sync data identified by a comparison job
- oracle goldengate
- real-time replication
- list veridata database connections
- list replication process performance metrics
- list groups
- data quality
- get job statistics
- get veridata server information
- list process metrics
- get server info
- create a new compare group
- create job
slug: data-verification
source_filename: data-verification.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Oracle GoldenGate Data Verification\"\n  description: \"Unified workflow for verifying data consistency between source and target databases. Combines Veridata for data comparison and repair with core GoldenGate monitoring for data quality engineers and DBAs ensuring replication integrity.\"\n  tags:\n    - Oracle GoldenGate\n    - Data Verification\n    - Data Quality\n    - Compliance\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      VERIDATA_USERNAME: VERIDATA_USERNAME\n      VERIDATA_PASSWORD: VERIDATA_PASSWORD\n      OGG_USERNAME: OGG_USERNAME\n      OGG_PASSWORD: OGG_PASSWORD\n\ncapability:\n  consumes:\n    - import: goldengate-veridata\n      location: ./shared/goldengate-veridata.yaml\n    - import: goldengate-rest\n      location: ./shared/goldengate-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: data-verification-api\n      description:\
  \ \"Unified REST API for Oracle GoldenGate data verification workflows.\"\n      resources:\n        - path: /v1/connections\n          name: connections\n          description: \"Database connections for verification\"\n          operations:\n            - method: GET\n              name: list-connections\n              description: \"List Veridata database connections\"\n              call: \"goldengate-veridata.list-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: \"Compare groups\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List compare groups\"\n              call: \"goldengate-veridata.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n          description: \"Comparison\
  \ jobs\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List comparison jobs\"\n              call: \"goldengate-veridata.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics\n          name: metrics\n          description: \"Replication process metrics\"\n          operations:\n            - method: GET\n              name: list-process-metrics\n              description: \"List replication process performance metrics\"\n              call: \"goldengate-rest.list-process-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: data-verification-mcp\n      transport: http\n      description: \"MCP server for AI-assisted data verification and comparison.\"\n      tools:\n        - name: list-connections\n          description: \"List\
  \ Veridata database connections\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-veridata.list-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-connection\n          description: \"Create a new Veridata database connection\"\n          hints:\n            readOnly: false\n          call: \"goldengate-veridata.create-connection\"\n          with:\n            name: \"tools.name\"\n            host: \"tools.host\"\n            port: \"tools.port\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List compare groups for data verification\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-veridata.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ create-group\n          description: \"Create a new compare group\"\n          hints:\n            readOnly: false\n          call: \"goldengate-veridata.create-group\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-jobs\n          description: \"List comparison jobs\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-veridata.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-job\n          description: \"Create a new comparison job\"\n          hints:\n            readOnly: false\n          call: \"goldengate-veridata.create-job\"\n          with:\n            name: \"tools.name\"\n            groupName: \"tools.groupName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-job\n       \
  \   description: \"Execute a comparison job\"\n          hints:\n            readOnly: false\n          call: \"goldengate-veridata.run-job\"\n          with:\n            jobName: \"tools.jobName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-statistics\n          description: \"Get comparison job statistics\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-veridata.get-job-statistics\"\n          with:\n            jobName: \"tools.jobName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-out-of-sync-data\n          description: \"Get details of out-of-sync data\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-veridata.get-out-of-sync-data\"\n          with:\n            jobName: \"tools.jobName\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: repair-job\n          description: \"Repair out-of-sync data identified by a comparison job\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"goldengate-veridata.repair-job\"\n          with:\n            jobName: \"tools.jobName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-server-info\n          description: \"Get Veridata server information\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-veridata.get-server-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-process-metrics\n          description: \"Get GoldenGate process performance metrics for monitoring replication health\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-rest.list-process-metrics\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-goldengate/refs/heads/main/capabilities/data-verification.yaml
tags:
- Oracle GoldenGate
- Data Verification
- Data Quality
- Compliance
tools:
- description: List Veridata database connections
  hints:
    openWorld: true
    readOnly: true
  name: list-connections
- description: Create a new Veridata database connection
  hints:
    readOnly: false
  name: create-connection
- description: List compare groups for data verification
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Create a new compare group
  hints:
    readOnly: false
  name: create-group
- description: List comparison jobs
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Create a new comparison job
  hints:
    readOnly: false
  name: create-job
- description: Execute a comparison job
  hints:
    readOnly: false
  name: run-job
- description: Get comparison job statistics
  hints:
    openWorld: true
    readOnly: true
  name: get-job-statistics
- description: Get details of out-of-sync data
  hints:
    openWorld: true
    readOnly: true
  name: get-out-of-sync-data
- description: Repair out-of-sync data identified by a comparison job
  hints:
    destructive: true
    readOnly: false
  name: repair-job
- description: Get Veridata server information
  hints:
    openWorld: true
    readOnly: true
  name: get-server-info
- description: Get GoldenGate process performance metrics for monitoring replication health
  hints:
    openWorld: true
    readOnly: true
  name: list-process-metrics
---

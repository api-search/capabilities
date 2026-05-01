---
categories:
- data-engineering
consumed_apis:
- goldengate-rest
- goldengate-big-data
- goldengate-data-streams
description: Unified workflow for managing real-time data replication across on-premises and cloud environments. Combines the core GoldenGate REST API, Big Data API, and Data Streams API for data integration engineers managing CDC pipelines, extract/replicat processes, and data distribution.
layout: capability
name: Oracle GoldenGate Data Replication
operations:
- description: List all Extract processes
  method: GET
  name: list-extracts
  path: /v1/extracts
- description: Create a new Extract process
  method: POST
  name: create-extract
  path: /v1/extracts
- description: Get a specific Extract process
  method: GET
  name: get-extract
  path: /v1/extracts/{extract}
- description: Delete an Extract process
  method: DELETE
  name: delete-extract
  path: /v1/extracts/{extract}
- description: List all Replicat processes
  method: GET
  name: list-replicats
  path: /v1/replicats
- description: List all big data Replicat processes
  method: GET
  name: list-big-data-replicats
  path: /v1/big-data-replicats
- description: List all data streams
  method: GET
  name: list-data-streams
  path: /v1/data-streams
- description: List available big data target types
  method: GET
  name: list-data-target-types
  path: /v1/data-target-types
- description: List credential domains
  method: GET
  name: list-credential-domains
  path: /v1/credentials
- description: List distribution paths
  method: GET
  name: list-distribution-paths
  path: /v1/distribution-paths
- description: Get service health details
  method: GET
  name: get-service-health
  path: /v1/health
personas: []
provider_name: Oracle GoldenGate
provider_slug: oracle-goldengate
search_terms:
- get details of a specific replicat process
- core list extracts
- bigdata get replicat
- credential store management
- core issue replicat command
- list available big data target types (kafka, hdfs, mongodb, etc.)
- execute a ggsci-style goldengate command
- list big data replicats
- replicat process management
- delete extract
- list data streams
- service health
- list all replicat processes
- list all extract processes from the core goldengate deployment
- create a new replicat process
- real-time replication
- get a specific extract process
- create a new extract process
- get configuration of a specific data stream
- big data replicat processes
- issue a command (start, stop, kill) to an extract
- create data stream
- list distribution paths
- data replication
- cdc
- list available big data target types
- core get replicat
- available big data target types
- delete an extract process
- list replicats
- execute command
- enterprise
- list all big data replicat processes
- list all extract processes
- data stream management
- bigdata list replicats
- extract process management across core and big data deployments
- data integration
- issue a command to a replicat process
- core list replicats
- oracle goldengate
- get extract
- core get extract
- list extracts
- core create extract
- list data target types
- get details of a specific extract process
- get a big data replicat process
- create extract
- individual extract operations
- list data distribution paths
- list credential store domains
- core create replicat
- database
- core issue extract command
- distribution path management
- create a new data stream for downstream distribution
- get performance metrics for all running processes
- list all configured data streams
- data synchronization
- list all data streams
- get data stream
- get service health details
- list process metrics
- get service health
- list credential domains
slug: data-replication
source_filename: data-replication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Oracle GoldenGate Data Replication\"\n  description: \"Unified workflow for managing real-time data replication across on-premises and cloud environments. Combines the core GoldenGate REST API, Big Data API, and Data Streams API for data integration engineers managing CDC pipelines, extract/replicat processes, and data distribution.\"\n  tags:\n    - Oracle GoldenGate\n    - Data Replication\n    - CDC\n    - Data Integration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      OGG_USERNAME: OGG_USERNAME\n      OGG_PASSWORD: OGG_PASSWORD\n      OGG_BD_USERNAME: OGG_BD_USERNAME\n      OGG_BD_PASSWORD: OGG_BD_PASSWORD\n      OGG_DS_USERNAME: OGG_DS_USERNAME\n      OGG_DS_PASSWORD: OGG_DS_PASSWORD\n\ncapability:\n  consumes:\n    - import: goldengate-rest\n      location: ./shared/goldengate-rest.yaml\n    - import: goldengate-big-data\n      location: ./shared/goldengate-big-data.yaml\n\
  \    - import: goldengate-data-streams\n      location: ./shared/goldengate-data-streams.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: data-replication-api\n      description: \"Unified REST API for Oracle GoldenGate data replication workflows.\"\n      resources:\n        - path: /v1/extracts\n          name: extracts\n          description: \"Extract process management across core and big data deployments\"\n          operations:\n            - method: GET\n              name: list-extracts\n              description: \"List all Extract processes\"\n              call: \"goldengate-rest.list-extracts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-extract\n              description: \"Create a new Extract process\"\n              call: \"goldengate-rest.create-extract\"\n              with:\n                extract: \"rest.extract\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/extracts/{extract}\n          name: extract-detail\n          description: \"Individual extract operations\"\n          operations:\n            - method: GET\n              name: get-extract\n              description: \"Get a specific Extract process\"\n              call: \"goldengate-rest.get-extract\"\n              with:\n                extract: \"rest.extract\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-extract\n              description: \"Delete an Extract process\"\n              call: \"goldengate-rest.delete-extract\"\n              with:\n                extract: \"rest.extract\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/replicats\n          name: replicats\n          description: \"Replicat process\
  \ management\"\n          operations:\n            - method: GET\n              name: list-replicats\n              description: \"List all Replicat processes\"\n              call: \"goldengate-rest.list-replicats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/big-data-replicats\n          name: big-data-replicats\n          description: \"Big data Replicat processes\"\n          operations:\n            - method: GET\n              name: list-big-data-replicats\n              description: \"List all big data Replicat processes\"\n              call: \"goldengate-big-data.list-replicats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-streams\n          name: data-streams\n          description: \"Data stream management\"\n          operations:\n            - method: GET\n              name: list-data-streams\n              description:\
  \ \"List all data streams\"\n              call: \"goldengate-data-streams.list-data-streams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-target-types\n          name: data-target-types\n          description: \"Available big data target types\"\n          operations:\n            - method: GET\n              name: list-data-target-types\n              description: \"List available big data target types\"\n              call: \"goldengate-big-data.list-data-target-types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/credentials\n          name: credentials\n          description: \"Credential store management\"\n          operations:\n            - method: GET\n              name: list-credential-domains\n              description: \"List credential domains\"\n              call: \"goldengate-rest.list-credential-domains\"\n    \
  \          outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/distribution-paths\n          name: distribution-paths\n          description: \"Distribution path management\"\n          operations:\n            - method: GET\n              name: list-distribution-paths\n              description: \"List distribution paths\"\n              call: \"goldengate-rest.list-distribution-paths\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/health\n          name: health\n          description: \"Service health\"\n          operations:\n            - method: GET\n              name: get-service-health\n              description: \"Get service health details\"\n              call: \"goldengate-big-data.get-service-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace:\
  \ data-replication-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Oracle GoldenGate data replication management.\"\n      tools:\n        - name: core-list-extracts\n          description: \"List all Extract processes from the core GoldenGate deployment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-rest.list-extracts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: core-get-extract\n          description: \"Get details of a specific Extract process\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-rest.get-extract\"\n          with:\n            extract: \"tools.extract\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: core-create-extract\n          description: \"Create a new Extract process\"\n          hints:\n            readOnly:\
  \ false\n          call: \"goldengate-rest.create-extract\"\n          with:\n            extract: \"tools.extract\"\n            type: \"tools.type\"\n            trail: \"tools.trail\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: core-issue-extract-command\n          description: \"Issue a command (START, STOP, KILL) to an Extract\"\n          hints:\n            readOnly: false\n          call: \"goldengate-rest.issue-extract-command\"\n          with:\n            extract: \"tools.extract\"\n            action: \"tools.action\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: core-list-replicats\n          description: \"List all Replicat processes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-rest.list-replicats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n    \
  \    - name: core-get-replicat\n          description: \"Get details of a specific Replicat process\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-rest.get-replicat\"\n          with:\n            replicat: \"tools.replicat\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: core-create-replicat\n          description: \"Create a new Replicat process\"\n          hints:\n            readOnly: false\n          call: \"goldengate-rest.create-replicat\"\n          with:\n            replicat: \"tools.replicat\"\n            type: \"tools.type\"\n            trail: \"tools.trail\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: core-issue-replicat-command\n          description: \"Issue a command to a Replicat process\"\n          hints:\n            readOnly: false\n          call: \"goldengate-rest.issue-replicat-command\"\
  \n          with:\n            replicat: \"tools.replicat\"\n            action: \"tools.action\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: bigdata-list-replicats\n          description: \"List all big data Replicat processes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-big-data.list-replicats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: bigdata-get-replicat\n          description: \"Get a big data Replicat process\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-big-data.get-replicat\"\n          with:\n            replicat: \"tools.replicat\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-target-types\n          description: \"List available big data target types (Kafka, HDFS,\
  \ MongoDB, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-big-data.list-data-target-types\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-streams\n          description: \"List all configured data streams\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-data-streams.list-data-streams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-data-stream\n          description: \"Get configuration of a specific data stream\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-data-streams.get-data-stream\"\n          with:\n            streamname: \"tools.streamname\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-data-stream\n  \
  \        description: \"Create a new data stream for downstream distribution\"\n          hints:\n            readOnly: false\n          call: \"goldengate-data-streams.create-data-stream\"\n          with:\n            streamname: \"tools.streamname\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-distribution-paths\n          description: \"List data distribution paths\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-rest.list-distribution-paths\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-credential-domains\n          description: \"List credential store domains\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-rest.list-credential-domains\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ execute-command\n          description: \"Execute a GGSCI-style GoldenGate command\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"goldengate-rest.execute-command\"\n          with:\n            command: \"tools.command\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-process-metrics\n          description: \"Get performance metrics for all running processes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-rest.list-process-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-goldengate/refs/heads/main/capabilities/data-replication.yaml
tags:
- Oracle GoldenGate
- Data Replication
- CDC
- Data Integration
tools:
- description: List all Extract processes from the core GoldenGate deployment
  hints:
    openWorld: true
    readOnly: true
  name: core-list-extracts
- description: Get details of a specific Extract process
  hints:
    openWorld: true
    readOnly: true
  name: core-get-extract
- description: Create a new Extract process
  hints:
    readOnly: false
  name: core-create-extract
- description: Issue a command (START, STOP, KILL) to an Extract
  hints:
    readOnly: false
  name: core-issue-extract-command
- description: List all Replicat processes
  hints:
    openWorld: true
    readOnly: true
  name: core-list-replicats
- description: Get details of a specific Replicat process
  hints:
    openWorld: true
    readOnly: true
  name: core-get-replicat
- description: Create a new Replicat process
  hints:
    readOnly: false
  name: core-create-replicat
- description: Issue a command to a Replicat process
  hints:
    readOnly: false
  name: core-issue-replicat-command
- description: List all big data Replicat processes
  hints:
    openWorld: true
    readOnly: true
  name: bigdata-list-replicats
- description: Get a big data Replicat process
  hints:
    openWorld: true
    readOnly: true
  name: bigdata-get-replicat
- description: List available big data target types (Kafka, HDFS, MongoDB, etc.)
  hints:
    openWorld: true
    readOnly: true
  name: list-data-target-types
- description: List all configured data streams
  hints:
    openWorld: true
    readOnly: true
  name: list-data-streams
- description: Get configuration of a specific data stream
  hints:
    openWorld: true
    readOnly: true
  name: get-data-stream
- description: Create a new data stream for downstream distribution
  hints:
    readOnly: false
  name: create-data-stream
- description: List data distribution paths
  hints:
    openWorld: true
    readOnly: true
  name: list-distribution-paths
- description: List credential store domains
  hints:
    openWorld: true
    readOnly: true
  name: list-credential-domains
- description: Execute a GGSCI-style GoldenGate command
  hints:
    openWorld: true
    readOnly: false
  name: execute-command
- description: Get performance metrics for all running processes
  hints:
    openWorld: true
    readOnly: true
  name: list-process-metrics
---

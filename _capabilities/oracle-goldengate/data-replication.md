---
categories:
- data-engineering
consumed_apis: []
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
- credential store management
- create a new data stream for downstream distribution
- oracle goldengate
- get details of a specific extract process
- list all extract processes from the core goldengate deployment
- list all data streams
- core get replicat
- execute command
- cdc
- core issue replicat command
- bigdata list replicats
- list available big data target types (kafka, hdfs, mongodb, etc.)
- list replicats
- get a specific extract process
- list distribution paths
- data replication
- list all replicat processes
- bigdata get replicat
- list big data replicats
- create data stream
- replicat process management
- data stream management
- list data distribution paths
- list extracts
- get configuration of a specific data stream
- individual extract operations
- get extract
- get details of a specific replicat process
- create a new replicat process
- issue a command to a replicat process
- get data stream
- data synchronization
- enterprise
- big data replicat processes
- get service health
- list all big data replicat processes
- list data target types
- extract process management across core and big data deployments
- get service health details
- get performance metrics for all running processes
- database
- service health
- core issue extract command
- list available big data target types
- core get extract
- list all configured data streams
- get a big data replicat process
- list process metrics
- list credential store domains
- list credential domains
- list all extract processes
- create a new extract process
- delete an extract process
- execute a ggsci-style goldengate command
- real-time replication
- data integration
- core list replicats
- core list extracts
- issue a command (start, stop, kill) to an extract
- delete extract
- available big data target types
- create extract
- core create extract
- core create replicat
- distribution path management
- list data streams
slug: data-replication
source_filename: data-replication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle GoldenGate Data Replication\n  description: Unified workflow for managing real-time data replication across on-premises and cloud environments. Combines\n    the core GoldenGate REST API, Big Data API, and Data Streams API for data integration engineers managing CDC pipelines,\n    extract/replicat processes, and data distribution.\n  tags:\n  - Oracle GoldenGate\n  - Data Replication\n  - CDC\n  - Data Integration\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    OGG_USERNAME: OGG_USERNAME\n    OGG_PASSWORD: OGG_PASSWORD\n    OGG_BD_USERNAME: OGG_BD_USERNAME\n    OGG_BD_PASSWORD: OGG_BD_PASSWORD\n    OGG_DS_USERNAME: OGG_DS_USERNAME\n    OGG_DS_PASSWORD: OGG_DS_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: goldengate-rest\n    baseUri: https://{goldengate-host}:{port}\n    description: Oracle GoldenGate Microservices REST API\n    authentication:\n      type: basic\n\
  \      username: '{{OGG_USERNAME}}'\n      password: '{{OGG_PASSWORD}}'\n    resources:\n    - name: configuration\n      path: /services\n      description: API version and configuration management\n      operations:\n      - name: get-api-versions\n        method: GET\n        description: Returns the list of available REST API versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-api-version\n        method: GET\n        description: Returns details for a specific API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-config-summary\n        method: GET\n        description: Returns configuration summary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /services/v2/config/health\n\
  \      description: Service health monitoring\n      operations:\n      - name: get-service-health-details\n        method: GET\n        description: Returns detailed health information for the GoldenGate service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-service-health-check\n        method: GET\n        description: Returns a quick health check status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /services/v2/deployments\n      description: GoldenGate deployment management\n      operations:\n      - name: list-deployments\n        method: GET\n        description: Returns a list of GoldenGate deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-deployment\n    \
  \    method: GET\n        description: Returns details of a specific deployment\n        inputParameters:\n        - name: deployment\n          in: path\n          type: string\n          required: true\n          description: Deployment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description: Creates a new GoldenGate deployment\n        inputParameters:\n        - name: deployment\n          in: path\n          type: string\n          required: true\n          description: Deployment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            config: '{{tools.config}}'\n      - name: update-deployment\n        method: PATCH\n        description: Updates an existing deployment\n        inputParameters:\n\
  \        - name: deployment\n          in: path\n          type: string\n          required: true\n          description: Deployment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            config: '{{tools.config}}'\n      - name: delete-deployment\n        method: DELETE\n        description: Deletes a deployment\n        inputParameters:\n        - name: deployment\n          in: path\n          type: string\n          required: true\n          description: Deployment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extracts\n      path: /services/v2/extracts\n      description: Extract process management\n      operations:\n      - name: list-extracts\n        method: GET\n        description: Returns a list of all Extract processes\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-extract\n        method: GET\n        description: Returns configuration and status of a specific Extract\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-extract\n        method: POST\n        description: Creates a new Extract process\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n\
  \            trail: '{{tools.trail}}'\n            config: '{{tools.config}}'\n      - name: update-extract\n        method: PATCH\n        description: Updates an existing Extract process\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            config: '{{tools.config}}'\n      - name: delete-extract\n        method: DELETE\n        description: Deletes an Extract process\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: issue-extract-command\n\
  \        method: POST\n        description: Issues a command (START, STOP, KILL, STATUS) to an Extract\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            action: '{{tools.action}}'\n    - name: replicats\n      path: /services/v2/replicats\n      description: Replicat process management\n      operations:\n      - name: list-replicats\n        method: GET\n        description: Returns a list of all Replicat processes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-replicat\n        method: GET\n        description: Returns configuration and status of a specific Replicat\n        inputParameters:\n\
  \        - name: replicat\n          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-replicat\n        method: POST\n        description: Creates a new Replicat process\n        inputParameters:\n        - name: replicat\n          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            trail: '{{tools.trail}}'\n            config: '{{tools.config}}'\n      - name: update-replicat\n        method: PATCH\n        description: Updates an existing Replicat process\n        inputParameters:\n        - name: replicat\n\
  \          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            config: '{{tools.config}}'\n      - name: delete-replicat\n        method: DELETE\n        description: Deletes a Replicat process\n        inputParameters:\n        - name: replicat\n          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: issue-replicat-command\n        method: POST\n        description: Issues a command to a Replicat process\n        inputParameters:\n        - name: replicat\n          in: path\n          type: string\n          required: true\n          description:\
  \ Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            action: '{{tools.action}}'\n    - name: credentials\n      path: /services/v2/credentials\n      description: Credential store management\n      operations:\n      - name: list-credential-domains\n        method: GET\n        description: Returns all credential store domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-credential-alias\n        method: GET\n        description: Returns a credential alias\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n          description: Credential store domain\n        - name: alias\n          in: path\n          type: string\n          required: true\n          description:\
  \ Credential alias name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-credential-alias\n        method: POST\n        description: Creates a credential alias\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n          description: Credential store domain\n        - name: alias\n          in: path\n          type: string\n          required: true\n          description: Credential alias name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userid: '{{tools.userid}}'\n            password: '{{tools.password}}'\n    - name: distribution\n      path: /services/v2/sources\n      description: Distribution path management\n      operations:\n      - name: list-distribution-paths\n\
  \        method: GET\n        description: Returns distribution paths\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-distribution-path\n        method: GET\n        description: Returns a specific distribution path\n        inputParameters:\n        - name: distpath\n          in: path\n          type: string\n          required: true\n          description: Distribution path name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring\n      path: /services/v2/mpoints\n      description: Performance metrics and monitoring\n      operations:\n      - name: list-process-metrics\n        method: GET\n        description: Returns performance metrics for all running processes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: get-process-metrics\n        method: GET\n        description: Returns metrics for a specific process\n        inputParameters:\n        - name: item\n          in: path\n          type: string\n          required: true\n          description: Process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commands\n      path: /services/v2/commands\n      description: Execute GoldenGate commands\n      operations:\n      - name: execute-command\n        method: POST\n        description: Executes a GGSCI-style command\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            command: '{{tools.command}}'\n  - type: http\n    namespace: goldengate-big-data\n    baseUri: https://{goldengate-host}:{port}\n    description: Oracle GoldenGate for Big Data\
  \ REST API\n    authentication:\n      type: basic\n      username: '{{OGG_BD_USERNAME}}'\n      password: '{{OGG_BD_PASSWORD}}'\n    resources:\n    - name: health\n      path: /services/v2/config/health\n      description: Service health monitoring\n      operations:\n      - name: get-service-health\n        method: GET\n        description: Returns health information for the Big Data service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extracts\n      path: /services/v2/extracts\n      description: Extract process management for source data capture\n      operations:\n      - name: list-extracts\n        method: GET\n        description: Returns a list of all Extract processes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-extract\n        method: GET\n        description: Returns a specific\
  \ Extract process\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-extract\n        method: POST\n        description: Creates a new Extract process\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            trail: '{{tools.trail}}'\n      - name: delete-extract\n        method: DELETE\n        description: Deletes an Extract process\n        inputParameters:\n        - name: extract\n        \
  \  in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: issue-extract-command\n        method: POST\n        description: Issues a command to an Extract process\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            action: '{{tools.action}}'\n    - name: replicats\n      path: /services/v2/replicats\n      description: Replicat process management for big data targets\n      operations:\n      - name: list-replicats\n        method: GET\n        description: Returns a list of all Replicat processes\
  \ for big data targets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-replicat\n        method: GET\n        description: Returns a Replicat targeting a big data system\n        inputParameters:\n        - name: replicat\n          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-replicat\n        method: POST\n        description: Creates a new Replicat with a big data handler\n        inputParameters:\n        - name: replicat\n          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n   \
  \       type: json\n          data:\n            type: '{{tools.type}}'\n            trail: '{{tools.trail}}'\n      - name: delete-replicat\n        method: DELETE\n        description: Deletes a Replicat process\n        inputParameters:\n        - name: replicat\n          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-replicat-status\n        method: GET\n        description: Returns runtime status of a big data Replicat\n        inputParameters:\n        - name: replicat\n          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-targets\n      path: /services/v2/dataTargetTypes\n  \
  \    description: Big data target type configurations\n      operations:\n      - name: list-data-target-types\n        method: GET\n        description: Returns available big data target types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-data-target-type-schema\n        method: GET\n        description: Returns JSON schema for a data target type\n        inputParameters:\n        - name: dataTargetType\n          in: path\n          type: string\n          required: true\n          description: Data target type name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credentials\n      path: /services/v2/credentials\n      description: Credential store for big data target authentication\n      operations:\n      - name: list-credential-domains\n        method: GET\n        description: Returns all credential\
  \ store domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring\n      path: /services/v2/mpoints\n      description: Performance metrics and monitoring\n      operations:\n      - name: list-process-metrics\n        method: GET\n        description: Returns performance metrics for all running processes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-replicat-stats\n        method: GET\n        description: Returns handler-level statistics for a big data Replicat\n        inputParameters:\n        - name: item\n          in: path\n          type: string\n          required: true\n          description: Process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: goldengate-data-streams\n\
  \    baseUri: https://{goldengate-host}:{port}\n    description: Oracle GoldenGate Data Streams REST API\n    authentication:\n      type: basic\n      username: '{{OGG_DS_USERNAME}}'\n      password: '{{OGG_DS_PASSWORD}}'\n    resources:\n    - name: data-streams\n      path: /services/v2/stream\n      description: Data stream configuration management\n      operations:\n      - name: list-data-streams\n        method: GET\n        description: Returns a list of all configured data streams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-data-stream\n        method: GET\n        description: Returns configuration of a specific data stream\n        inputParameters:\n        - name: streamname\n          in: path\n          type: string\n          required: true\n          description: Data stream name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: create-data-stream\n        method: POST\n        description: Creates a new data stream configuration\n        inputParameters:\n        - name: streamname\n          in: path\n          type: string\n          required: true\n          description: Data stream name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            description: '{{tools.description}}'\n            source: '{{tools.source}}'\n            target: '{{tools.target}}'\n      - name: update-data-stream\n        method: PATCH\n        description: Updates an existing data stream\n        inputParameters:\n        - name: streamname\n          in: path\n          type: string\n          required: true\n          description: Data stream name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n        body:\n          type: json\n          data:\n            description: '{{tools.description}}'\n      - name: delete-data-stream\n        method: DELETE\n        description: Deletes a data stream\n        inputParameters:\n        - name: streamname\n          in: path\n          type: string\n          required: true\n          description: Data stream name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: asyncapi\n      path: /services/v2/stream\n      description: AsyncAPI specification management\n      operations:\n      - name: get-asyncapi-spec\n        method: GET\n        description: Retrieves the AsyncAPI specification for a data stream\n        inputParameters:\n        - name: streamname\n          in: path\n          type: string\n          required: true\n          description: Data stream name\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-asyncapi-spec\n        method: PATCH\n        description: Updates the AsyncAPI specification for a data stream\n        inputParameters:\n        - name: streamname\n          in: path\n          type: string\n          required: true\n          description: Data stream name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: data-replication-api\n    description: Unified REST API for Oracle GoldenGate data replication workflows.\n    resources:\n    - path: /v1/extracts\n      name: extracts\n      description: Extract process management across core and big data deployments\n      operations:\n      - method: GET\n        name: list-extracts\n        description: List all Extract processes\n        call: goldengate-rest.list-extracts\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-extract\n        description: Create a new Extract process\n        call: goldengate-rest.create-extract\n        with:\n          extract: rest.extract\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/extracts/{extract}\n      name: extract-detail\n      description: Individual extract operations\n      operations:\n      - method: GET\n        name: get-extract\n        description: Get a specific Extract process\n        call: goldengate-rest.get-extract\n        with:\n          extract: rest.extract\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-extract\n        description: Delete an Extract process\n        call: goldengate-rest.delete-extract\n        with:\n          extract: rest.extract\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/replicats\n      name: replicats\n      description: Replicat process management\n      operations:\n      - method: GET\n        name: list-replicats\n        description: List all Replicat processes\n        call: goldengate-rest.list-replicats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/big-data-replicats\n      name: big-data-replicats\n      description: Big data Replicat processes\n      operations:\n      - method: GET\n        name: list-big-data-replicats\n        description: List all big data Replicat processes\n        call: goldengate-big-data.list-replicats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-streams\n      name: data-streams\n      description: Data stream management\n      operations:\n      - method: GET\n        name: list-data-streams\n        description: List all data streams\n        call: goldengate-data-streams.list-data-streams\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-target-types\n      name: data-target-types\n      description: Available big data target types\n      operations:\n      - method: GET\n        name: list-data-target-types\n        description: List available big data target types\n        call: goldengate-big-data.list-data-target-types\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/credentials\n      name: credentials\n      description: Credential store management\n      operations:\n      - method: GET\n        name: list-credential-domains\n        description: List credential domains\n        call: goldengate-rest.list-credential-domains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/distribution-paths\n      name: distribution-paths\n      description: Distribution path management\n      operations:\n      - method: GET\n        name: list-distribution-paths\n\
  \        description: List distribution paths\n        call: goldengate-rest.list-distribution-paths\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health\n      name: health\n      description: Service health\n      operations:\n      - method: GET\n        name: get-service-health\n        description: Get service health details\n        call: goldengate-big-data.get-service-health\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: data-replication-mcp\n    transport: http\n    description: MCP server for AI-assisted Oracle GoldenGate data replication management.\n    tools:\n    - name: core-list-extracts\n      description: List all Extract processes from the core GoldenGate deployment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-rest.list-extracts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ core-get-extract\n      description: Get details of a specific Extract process\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-rest.get-extract\n      with:\n        extract: tools.extract\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: core-create-extract\n      description: Create a new Extract process\n      hints:\n        readOnly: false\n      call: goldengate-rest.create-extract\n      with:\n        extract: tools.extract\n        type: tools.type\n        trail: tools.trail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: core-issue-extract-command\n      description: Issue a command (START, STOP, KILL) to an Extract\n      hints:\n        readOnly: false\n      call: goldengate-rest.issue-extract-command\n      with:\n        extract: tools.extract\n        action: tools.action\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: core-list-replicats\n\
  \      description: List all Replicat processes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-rest.list-replicats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: core-get-replicat\n      description: Get details of a specific Replicat process\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-rest.get-replicat\n      with:\n        replicat: tools.replicat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: core-create-replicat\n      description: Create a new Replicat process\n      hints:\n        readOnly: false\n      call: goldengate-rest.create-replicat\n      with:\n        replicat: tools.replicat\n        type: tools.type\n        trail: tools.trail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: core-issue-replicat-command\n      description: Issue a command to a Replicat process\n      hints:\n        readOnly:\
  \ false\n      call: goldengate-rest.issue-replicat-command\n      with:\n        replicat: tools.replicat\n        action: tools.action\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bigdata-list-replicats\n      description: List all big data Replicat processes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-big-data.list-replicats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bigdata-get-replicat\n      description: Get a big data Replicat process\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-big-data.get-replicat\n      with:\n        replicat: tools.replicat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-data-target-types\n      description: List available big data target types (Kafka, HDFS, MongoDB, etc.)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-big-data.list-data-target-types\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-data-streams\n      description: List all configured data streams\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-data-streams.list-data-streams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-data-stream\n      description: Get configuration of a specific data stream\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-data-streams.get-data-stream\n      with:\n        streamname: tools.streamname\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-data-stream\n      description: Create a new data stream for downstream distribution\n      hints:\n        readOnly: false\n      call: goldengate-data-streams.create-data-stream\n      with:\n        streamname: tools.streamname\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-distribution-paths\n\
  \      description: List data distribution paths\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-rest.list-distribution-paths\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-credential-domains\n      description: List credential store domains\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-rest.list-credential-domains\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-command\n      description: Execute a GGSCI-style GoldenGate command\n      hints:\n        readOnly: false\n        openWorld: true\n      call: goldengate-rest.execute-command\n      with:\n        command: tools.command\n      outputParameters:\n     \n\n# --- truncated at 32 KB (32 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/oracle-goldengate/refs/heads/main/capabilities/data-replication.yaml\n"
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

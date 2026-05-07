---
categories: []
consumed_apis: []
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
- create group
- create a new comparison job
- create job
- database connections for verification
- get details of out-of-sync data
- list connections
- replication process metrics
- oracle goldengate
- execute a comparison job
- list groups
- get out of sync data
- get server info
- get goldengate process performance metrics for monitoring replication health
- cdc
- data quality
- get job statistics
- compare groups
- compliance
- list compare groups for data verification
- get comparison job statistics
- create connection
- create a new veridata database connection
- run job
- comparison jobs
- data synchronization
- list comparison jobs
- repair out-of-sync data identified by a comparison job
- enterprise
- list replication process performance metrics
- list compare groups
- database
- list jobs
- repair job
- get veridata server information
- list process metrics
- real-time replication
- data integration
- data verification
- create a new compare group
- list veridata database connections
slug: data-verification
source_filename: data-verification.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle GoldenGate Data Verification\n  description: Unified workflow for verifying data consistency between source and target databases. Combines Veridata for\n    data comparison and repair with core GoldenGate monitoring for data quality engineers and DBAs ensuring replication integrity.\n  tags:\n  - Oracle GoldenGate\n  - Data Verification\n  - Data Quality\n  - Compliance\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VERIDATA_USERNAME: VERIDATA_USERNAME\n    VERIDATA_PASSWORD: VERIDATA_PASSWORD\n    OGG_USERNAME: OGG_USERNAME\n    OGG_PASSWORD: OGG_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: goldengate-veridata\n    baseUri: https://{veridata-host}:{port}/veridata/v1\n    description: Oracle GoldenGate Veridata REST API\n    authentication:\n      type: basic\n      username: '{{VERIDATA_USERNAME}}'\n      password: '{{VERIDATA_PASSWORD}}'\n    resources:\n    - name:\
  \ server\n      path: /services/server\n      description: Server information and configuration\n      operations:\n      - name: get-server-info\n        method: GET\n        description: Returns server information including version and uptime\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-server-configuration\n        method: GET\n        description: Returns current server configuration settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /services/connections\n      description: Source and target database connection management\n      operations:\n      - name: list-connections\n        method: GET\n        description: Returns a list of database connections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: create-connection\n        method: POST\n        description: Creates a new database connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            host: '{{tools.host}}'\n            port: '{{tools.port}}'\n      - name: get-connection\n        method: GET\n        description: Returns a specific connection\n        inputParameters:\n        - name: connectionName\n          in: path\n          type: string\n          required: true\n          description: Connection name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-connection\n        method: DELETE\n        description: Deletes a database connection\n        inputParameters:\n        - name: connectionName\n          in: path\n\
  \          type: string\n          required: true\n          description: Connection name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /services/groups\n      description: Compare group management\n      operations:\n      - name: list-groups\n        method: GET\n        description: Returns a list of compare groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Creates a new compare group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: get-group\n        method: GET\n        description: Returns a specific compare group\n        inputParameters:\n\
  \        - name: groupName\n          in: path\n          type: string\n          required: true\n          description: Group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-group\n        method: DELETE\n        description: Deletes a compare group\n        inputParameters:\n        - name: groupName\n          in: path\n          type: string\n          required: true\n          description: Group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /services/jobs\n      description: Comparison job management\n      operations:\n      - name: list-jobs\n        method: GET\n        description: Returns a list of comparison jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-job\n\
  \        method: POST\n        description: Creates a new comparison job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            groupName: '{{tools.groupName}}'\n      - name: get-job\n        method: GET\n        description: Returns a specific job\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n          description: Job name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-job\n        method: DELETE\n        description: Deletes a comparison job\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n          description: Job name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: execution\n      path: /services/jobs\n      description: Run and stop comparison jobs\n      operations:\n      - name: run-job\n        method: POST\n        description: Executes a comparison job\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n          description: Job name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-job\n        method: POST\n        description: Stops a running comparison job\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n          description: Job name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring\n      path: /services/monitoring\n\
  \      description: Comparison and repair statistics\n      operations:\n      - name: get-job-statistics\n        method: GET\n        description: Returns statistics for a comparison job\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n          description: Job name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-out-of-sync-data\n        method: GET\n        description: Returns out-of-sync data details\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n          description: Job name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repair\n      path: /services/repair\n      description: Repair out-of-sync data\n      operations:\n      - name: repair-job\n\
  \        method: POST\n        description: Initiates repair for out-of-sync data\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n          description: Job name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: goldengate-rest\n    baseUri: https://{goldengate-host}:{port}\n    description: Oracle GoldenGate Microservices REST API\n    authentication:\n      type: basic\n      username: '{{OGG_USERNAME}}'\n      password: '{{OGG_PASSWORD}}'\n    resources:\n    - name: configuration\n      path: /services\n      description: API version and configuration management\n      operations:\n      - name: get-api-versions\n        method: GET\n        description: Returns the list of available REST API versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: describe-api-version\n        method: GET\n        description: Returns details for a specific API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-config-summary\n        method: GET\n        description: Returns configuration summary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /services/v2/config/health\n      description: Service health monitoring\n      operations:\n      - name: get-service-health-details\n        method: GET\n        description: Returns detailed health information for the GoldenGate service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-service-health-check\n        method: GET\n        description: Returns a quick\
  \ health check status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /services/v2/deployments\n      description: GoldenGate deployment management\n      operations:\n      - name: list-deployments\n        method: GET\n        description: Returns a list of GoldenGate deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-deployment\n        method: GET\n        description: Returns details of a specific deployment\n        inputParameters:\n        - name: deployment\n          in: path\n          type: string\n          required: true\n          description: Deployment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description:\
  \ Creates a new GoldenGate deployment\n        inputParameters:\n        - name: deployment\n          in: path\n          type: string\n          required: true\n          description: Deployment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            config: '{{tools.config}}'\n      - name: update-deployment\n        method: PATCH\n        description: Updates an existing deployment\n        inputParameters:\n        - name: deployment\n          in: path\n          type: string\n          required: true\n          description: Deployment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            config: '{{tools.config}}'\n      - name: delete-deployment\n        method: DELETE\n        description: Deletes\
  \ a deployment\n        inputParameters:\n        - name: deployment\n          in: path\n          type: string\n          required: true\n          description: Deployment name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extracts\n      path: /services/v2/extracts\n      description: Extract process management\n      operations:\n      - name: list-extracts\n        method: GET\n        description: Returns a list of all Extract processes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-extract\n        method: GET\n        description: Returns configuration and status of a specific Extract\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-extract\n        method: POST\n        description: Creates a new Extract process\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            trail: '{{tools.trail}}'\n            config: '{{tools.config}}'\n      - name: update-extract\n        method: PATCH\n        description: Updates an existing Extract process\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n        body:\n          type: json\n          data:\n            config: '{{tools.config}}'\n      - name: delete-extract\n        method: DELETE\n        description: Deletes an Extract process\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: issue-extract-command\n        method: POST\n        description: Issues a command (START, STOP, KILL, STATUS) to an Extract\n        inputParameters:\n        - name: extract\n          in: path\n          type: string\n          required: true\n          description: Extract process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            action: '{{tools.action}}'\n    - name: replicats\n      path: /services/v2/replicats\n      description: Replicat process management\n      operations:\n      - name: list-replicats\n        method: GET\n        description: Returns a list of all Replicat processes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-replicat\n        method: GET\n        description: Returns configuration and status of a specific Replicat\n        inputParameters:\n        - name: replicat\n          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-replicat\n        method: POST\n        description: Creates a new Replicat process\n        inputParameters:\n        - name: replicat\n\
  \          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            trail: '{{tools.trail}}'\n            config: '{{tools.config}}'\n      - name: update-replicat\n        method: PATCH\n        description: Updates an existing Replicat process\n        inputParameters:\n        - name: replicat\n          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            config: '{{tools.config}}'\n      - name: delete-replicat\n        method: DELETE\n        description: Deletes a\
  \ Replicat process\n        inputParameters:\n        - name: replicat\n          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: issue-replicat-command\n        method: POST\n        description: Issues a command to a Replicat process\n        inputParameters:\n        - name: replicat\n          in: path\n          type: string\n          required: true\n          description: Replicat process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            action: '{{tools.action}}'\n    - name: credentials\n      path: /services/v2/credentials\n      description: Credential store management\n      operations:\n      - name: list-credential-domains\n     \
  \   method: GET\n        description: Returns all credential store domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-credential-alias\n        method: GET\n        description: Returns a credential alias\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n          description: Credential store domain\n        - name: alias\n          in: path\n          type: string\n          required: true\n          description: Credential alias name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-credential-alias\n        method: POST\n        description: Creates a credential alias\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n          description: Credential\
  \ store domain\n        - name: alias\n          in: path\n          type: string\n          required: true\n          description: Credential alias name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userid: '{{tools.userid}}'\n            password: '{{tools.password}}'\n    - name: distribution\n      path: /services/v2/sources\n      description: Distribution path management\n      operations:\n      - name: list-distribution-paths\n        method: GET\n        description: Returns distribution paths\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-distribution-path\n        method: GET\n        description: Returns a specific distribution path\n        inputParameters:\n        - name: distpath\n          in: path\n          type: string\n  \
  \        required: true\n          description: Distribution path name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring\n      path: /services/v2/mpoints\n      description: Performance metrics and monitoring\n      operations:\n      - name: list-process-metrics\n        method: GET\n        description: Returns performance metrics for all running processes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-process-metrics\n        method: GET\n        description: Returns metrics for a specific process\n        inputParameters:\n        - name: item\n          in: path\n          type: string\n          required: true\n          description: Process name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ commands\n      path: /services/v2/commands\n      description: Execute GoldenGate commands\n      operations:\n      - name: execute-command\n        method: POST\n        description: Executes a GGSCI-style command\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            command: '{{tools.command}}'\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: data-verification-api\n    description: Unified REST API for Oracle GoldenGate data verification workflows.\n    resources:\n    - path: /v1/connections\n      name: connections\n      description: Database connections for verification\n      operations:\n      - method: GET\n        name: list-connections\n        description: List Veridata database connections\n        call: goldengate-veridata.list-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/groups\n      name: groups\n      description: Compare groups\n      operations:\n      - method: GET\n        name: list-groups\n        description: List compare groups\n        call: goldengate-veridata.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Comparison jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List comparison jobs\n        call: goldengate-veridata.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Replication process metrics\n      operations:\n      - method: GET\n        name: list-process-metrics\n        description: List replication process performance metrics\n        call: goldengate-rest.list-process-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n\
  \    namespace: data-verification-mcp\n    transport: http\n    description: MCP server for AI-assisted data verification and comparison.\n    tools:\n    - name: list-connections\n      description: List Veridata database connections\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-veridata.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-connection\n      description: Create a new Veridata database connection\n      hints:\n        readOnly: false\n      call: goldengate-veridata.create-connection\n      with:\n        name: tools.name\n        host: tools.host\n        port: tools.port\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List compare groups for data verification\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-veridata.list-groups\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: create-group\n      description: Create a new compare group\n      hints:\n        readOnly: false\n      call: goldengate-veridata.create-group\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List comparison jobs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-veridata.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-job\n      description: Create a new comparison job\n      hints:\n        readOnly: false\n      call: goldengate-veridata.create-job\n      with:\n        name: tools.name\n        groupName: tools.groupName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-job\n      description: Execute a comparison job\n      hints:\n        readOnly: false\n      call: goldengate-veridata.run-job\n      with:\n        jobName: tools.jobName\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-statistics\n      description: Get comparison job statistics\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-veridata.get-job-statistics\n      with:\n        jobName: tools.jobName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-out-of-sync-data\n      description: Get details of out-of-sync data\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-veridata.get-out-of-sync-data\n      with:\n        jobName: tools.jobName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: repair-job\n      description: Repair out-of-sync data identified by a comparison job\n      hints:\n        readOnly: false\n        destructive: true\n      call: goldengate-veridata.repair-job\n      with:\n        jobName: tools.jobName\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: get-server-info\n      description: Get Veridata server information\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-veridata.get-server-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-process-metrics\n      description: Get GoldenGate process performance metrics for monitoring replication health\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-rest.list-process-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

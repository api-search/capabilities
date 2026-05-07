---
categories:
- data-engineering
consumed_apis: []
description: Unified workflow capability for managing Airbyte data integration pipelines — sources, destinations, connections, and sync jobs. Used by data engineers and platform teams.
layout: capability
name: Airbyte Data Pipeline Management
operations:
- description: List all data sources.
  method: GET
  name: list-sources
  path: /v1/sources
- description: Create a new data source.
  method: POST
  name: create-source
  path: /v1/sources
- description: List all destinations.
  method: GET
  name: list-destinations
  path: /v1/destinations
- description: Create a new destination.
  method: POST
  name: create-destination
  path: /v1/destinations
- description: List all connections.
  method: GET
  name: list-connections
  path: /v1/connections
- description: Create a new connection.
  method: POST
  name: create-connection
  path: /v1/connections
- description: List sync jobs.
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Trigger a sync job.
  method: POST
  name: trigger-job
  path: /v1/jobs
- description: List workspaces.
  method: GET
  name: list-workspaces
  path: /v1/workspaces
personas: []
provider_name: Airbyte
provider_slug: airbyte
search_terms:
- list workspaces
- delete source
- check the status of an airbyte sync job.
- trigger an airbyte sync job for a connection.
- user, workspace, and organizational management.
- list destinations
- manage workspaces.
- create a new data source.
- list connections
- create a new airbyte data destination connector.
- data engineering
- list airbyte sync jobs with optional status filtering.
- list all airbyte data source connectors.
- list sync jobs
- create an airbyte connection between a source and destination.
- moving data between sources and destinations.
- manage data source connectors.
- manage data destination connectors.
- list sync jobs.
- list all airbyte data destination connectors.
- open source
- create destination
- create connection
- list airbyte workspaces.
- list all data sources.
- manage source-to-destination connections.
- create a new destination.
- list workspaces.
- create a new airbyte data source connector.
- monitoring and operating sync pipelines.
- connectors
- list sources
- monitor and trigger sync jobs.
- get job status
- list jobs
- elt
- Data Engineer
- airbyte
- list all connections.
- etl
- trigger job
- trigger sync
- delete an airbyte source connector.
- manage airbyte sources, destinations, connections, and sync jobs.
- manages airbyte workspaces, users, permissions, and organizational settings.
- list all destinations.
- data
- data integration
- Platform Admin
- list airbyte connections between sources and destinations.
- data pipeline
- builds and maintains data pipelines using airbyte connectors and connections.
- create source
- create a new connection.
- trigger a sync job.
slug: data-pipeline-management
source_filename: data-pipeline-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Airbyte Data Pipeline Management\n  description: Unified workflow capability for managing Airbyte data integration pipelines — sources, destinations, connections,\n    and sync jobs. Used by data engineers and platform teams.\n  tags:\n  - Airbyte\n  - Data Integration\n  - ETL\n  - ELT\n  - Data Pipeline\n  - Data Engineering\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AIRBYTE_API_TOKEN: AIRBYTE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: airbyte\n    baseUri: https://api.airbyte.com/v1\n    description: Airbyte Public API for managing data integration pipelines.\n    authentication:\n      type: bearer\n      token: '{{AIRBYTE_API_TOKEN}}'\n    resources:\n    - name: sources\n      path: /sources\n      description: Manage data source connectors.\n      operations:\n      - name: list-sources\n        method: GET\n        description: List all sources in a workspace.\n\
  \        inputParameters:\n        - name: workspaceId\n          in: query\n          type: string\n          required: false\n          description: Filter by workspace ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-source\n        method: POST\n        description: Create a new data source.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            workspaceId: '{{tools.workspaceId}}'\n            name: '{{tools.name}}'\n            configuration: '{{tools.configuration}}'\n      - name: get-source\n        method: GET\n        description: Get a source by ID.\n        inputParameters:\n        - name: sourceId\n          in: path\n          type: string\n          required: true\n          description: Source ID.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-source\n        method: DELETE\n        description: Delete a source by ID.\n        inputParameters:\n        - name: sourceId\n          in: path\n          type: string\n          required: true\n          description: Source ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: destinations\n      path: /destinations\n      description: Manage data destination connectors.\n      operations:\n      - name: list-destinations\n        method: GET\n        description: List all destinations in a workspace.\n        inputParameters:\n        - name: workspaceId\n          in: query\n          type: string\n          required: false\n          description: Filter by workspace ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: create-destination\n        method: POST\n        description: Create a new destination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            workspaceId: '{{tools.workspaceId}}'\n            name: '{{tools.name}}'\n            configuration: '{{tools.configuration}}'\n    - name: connections\n      path: /connections\n      description: Manage connections between sources and destinations.\n      operations:\n      - name: list-connections\n        method: GET\n        description: List all connections in a workspace.\n        inputParameters:\n        - name: workspaceId\n          in: query\n          type: string\n          required: false\n          description: Filter by workspace ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: create-connection\n        method: POST\n        description: Create a connection between a source and destination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            sourceId: '{{tools.sourceId}}'\n            destinationId: '{{tools.destinationId}}'\n            name: '{{tools.name}}'\n      - name: get-connection\n        method: GET\n        description: Get a connection by ID.\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: Connection ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs\n      description: Monitor and trigger sync jobs.\n      operations:\n      - name: list-jobs\n        method: GET\n     \
  \   description: List sync jobs with optional filtering.\n        inputParameters:\n        - name: connectionId\n          in: query\n          type: string\n          required: false\n          description: Filter by connection ID.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by job status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-job\n        method: POST\n        description: Trigger a new sync job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            connectionId: '{{tools.connectionId}}'\n            jobType: '{{tools.jobType}}'\n      - name: get-job\n        method: GET\n        description: Get job status by ID.\n        inputParameters:\n        - name:\
  \ jobId\n          in: path\n          type: integer\n          required: true\n          description: Job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n      description: Manage workspaces for organizing resources.\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: List all workspaces.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-workspace\n        method: GET\n        description: Get a workspace by ID.\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: Workspace ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n\
  \      path: /organizations\n      description: Manage organizations and users.\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List organizations the current user belongs to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: airbyte-pipeline-api\n    description: Unified REST API for Airbyte data pipeline management.\n    resources:\n    - path: /v1/sources\n      name: sources\n      description: Manage data source connectors.\n      operations:\n      - method: GET\n        name: list-sources\n        description: List all data sources.\n        call: airbyte.list-sources\n        with:\n          workspaceId: rest.workspaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-source\n        description: Create a new data source.\n  \
  \      call: airbyte.create-source\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/destinations\n      name: destinations\n      description: Manage data destination connectors.\n      operations:\n      - method: GET\n        name: list-destinations\n        description: List all destinations.\n        call: airbyte.list-destinations\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-destination\n        description: Create a new destination.\n        call: airbyte.create-destination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections\n      name: connections\n      description: Manage source-to-destination connections.\n      operations:\n      - method: GET\n        name: list-connections\n        description: List all connections.\n        call: airbyte.list-connections\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n      - method: POST\n        name: create-connection\n        description: Create a new connection.\n        call: airbyte.create-connection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Monitor and trigger sync jobs.\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List sync jobs.\n        call: airbyte.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: trigger-job\n        description: Trigger a sync job.\n        call: airbyte.create-job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces\n      name: workspaces\n      description: Manage workspaces.\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: List workspaces.\n        call: airbyte.list-workspaces\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: airbyte-pipeline-mcp\n    transport: http\n    description: MCP server for AI-assisted Airbyte data pipeline management.\n    tools:\n    - name: list-sources\n      description: List all Airbyte data source connectors.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airbyte.list-sources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-source\n      description: Create a new Airbyte data source connector.\n      hints:\n        readOnly: false\n      call: airbyte.create-source\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-destinations\n      description: List all Airbyte data destination connectors.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airbyte.list-destinations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-destination\n\
  \      description: Create a new Airbyte data destination connector.\n      hints:\n        readOnly: false\n      call: airbyte.create-destination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connections\n      description: List Airbyte connections between sources and destinations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airbyte.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-connection\n      description: Create an Airbyte connection between a source and destination.\n      hints:\n        readOnly: false\n      call: airbyte.create-connection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sync-jobs\n      description: List Airbyte sync jobs with optional status filtering.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airbyte.list-jobs\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: trigger-sync\n      description: Trigger an Airbyte sync job for a connection.\n      hints:\n        readOnly: false\n      call: airbyte.create-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-status\n      description: Check the status of an Airbyte sync job.\n      hints:\n        readOnly: true\n      call: airbyte.get-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List Airbyte workspaces.\n      hints:\n        readOnly: true\n      call: airbyte.list-workspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-source\n      description: Delete an Airbyte source connector.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: airbyte.delete-source\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/airbyte/refs/heads/main/capabilities/data-pipeline-management.yaml
tags:
- Airbyte
- Data Integration
- ETL
- ELT
- Data Pipeline
- Data Engineering
tools:
- description: List all Airbyte data source connectors.
  hints:
    openWorld: true
    readOnly: true
  name: list-sources
- description: Create a new Airbyte data source connector.
  hints:
    readOnly: false
  name: create-source
- description: List all Airbyte data destination connectors.
  hints:
    openWorld: true
    readOnly: true
  name: list-destinations
- description: Create a new Airbyte data destination connector.
  hints:
    readOnly: false
  name: create-destination
- description: List Airbyte connections between sources and destinations.
  hints:
    openWorld: true
    readOnly: true
  name: list-connections
- description: Create an Airbyte connection between a source and destination.
  hints:
    readOnly: false
  name: create-connection
- description: List Airbyte sync jobs with optional status filtering.
  hints:
    openWorld: true
    readOnly: true
  name: list-sync-jobs
- description: Trigger an Airbyte sync job for a connection.
  hints:
    readOnly: false
  name: trigger-sync
- description: Check the status of an Airbyte sync job.
  hints:
    readOnly: true
  name: get-job-status
- description: List Airbyte workspaces.
  hints:
    readOnly: true
  name: list-workspaces
- description: Delete an Airbyte source connector.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-source
---

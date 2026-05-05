---
categories:
- data-engineering
consumed_apis:
- airbyte
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
- list workspaces.
- create a new airbyte data destination connector.
- list connections
- manage data source connectors.
- list all destinations.
- list sync jobs.
- trigger a sync job.
- list sync jobs
- list jobs
- user, workspace, and organizational management.
- create a new data source.
- elt
- data integration
- list all data sources.
- data engineering
- manage airbyte sources, destinations, connections, and sync jobs.
- open source
- data
- manages airbyte workspaces, users, permissions, and organizational settings.
- create an airbyte connection between a source and destination.
- trigger an airbyte sync job for a connection.
- moving data between sources and destinations.
- Data Engineer
- list all airbyte data destination connectors.
- trigger job
- list sources
- list all airbyte data source connectors.
- list airbyte connections between sources and destinations.
- list airbyte sync jobs with optional status filtering.
- monitoring and operating sync pipelines.
- etl
- get job status
- list all connections.
- monitor and trigger sync jobs.
- connectors
- manage source-to-destination connections.
- delete an airbyte source connector.
- list destinations
- create connection
- create destination
- create a new airbyte data source connector.
- check the status of an airbyte sync job.
- create source
- create a new destination.
- list airbyte workspaces.
- delete source
- builds and maintains data pipelines using airbyte connectors and connections.
- list workspaces
- manage data destination connectors.
- airbyte
- Platform Admin
- create a new connection.
- manage workspaces.
- trigger sync
- data pipeline
slug: data-pipeline-management
source_filename: data-pipeline-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Airbyte Data Pipeline Management\"\n  description: \"Unified workflow capability for managing Airbyte data integration pipelines — sources, destinations, connections, and sync jobs. Used by data engineers and platform teams.\"\n  tags:\n    - Airbyte\n    - Data Integration\n    - ETL\n    - ELT\n    - Data Pipeline\n    - Data Engineering\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AIRBYTE_API_TOKEN: AIRBYTE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: airbyte\n      location: ./shared/airbyte-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: airbyte-pipeline-api\n      description: \"Unified REST API for Airbyte data pipeline management.\"\n      resources:\n        - path: /v1/sources\n          name: sources\n          description: \"Manage data source connectors.\"\n          operations:\n            - method: GET\n              name:\
  \ list-sources\n              description: \"List all data sources.\"\n              call: \"airbyte.list-sources\"\n              with:\n                workspaceId: \"rest.workspaceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-source\n              description: \"Create a new data source.\"\n              call: \"airbyte.create-source\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/destinations\n          name: destinations\n          description: \"Manage data destination connectors.\"\n          operations:\n            - method: GET\n              name: list-destinations\n              description: \"List all destinations.\"\n              call: \"airbyte.list-destinations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method:\
  \ POST\n              name: create-destination\n              description: \"Create a new destination.\"\n              call: \"airbyte.create-destination\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connections\n          name: connections\n          description: \"Manage source-to-destination connections.\"\n          operations:\n            - method: GET\n              name: list-connections\n              description: \"List all connections.\"\n              call: \"airbyte.list-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-connection\n              description: \"Create a new connection.\"\n              call: \"airbyte.create-connection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n\
  \          description: \"Monitor and trigger sync jobs.\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List sync jobs.\"\n              call: \"airbyte.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: trigger-job\n              description: \"Trigger a sync job.\"\n              call: \"airbyte.create-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"Manage workspaces.\"\n          operations:\n            - method: GET\n              name: list-workspaces\n              description: \"List workspaces.\"\n              call: \"airbyte.list-workspaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n\
  \      port: 9090\n      namespace: airbyte-pipeline-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Airbyte data pipeline management.\"\n      tools:\n        - name: list-sources\n          description: \"List all Airbyte data source connectors.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"airbyte.list-sources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-source\n          description: \"Create a new Airbyte data source connector.\"\n          hints:\n            readOnly: false\n          call: \"airbyte.create-source\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-destinations\n          description: \"List all Airbyte data destination connectors.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"airbyte.list-destinations\"\n   \
  \       outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-destination\n          description: \"Create a new Airbyte data destination connector.\"\n          hints:\n            readOnly: false\n          call: \"airbyte.create-destination\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connections\n          description: \"List Airbyte connections between sources and destinations.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"airbyte.list-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-connection\n          description: \"Create an Airbyte connection between a source and destination.\"\n          hints:\n            readOnly: false\n          call: \"airbyte.create-connection\"\n          outputParameters:\n            - type: object\n          \
  \    mapping: \"$.\"\n        - name: list-sync-jobs\n          description: \"List Airbyte sync jobs with optional status filtering.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"airbyte.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: trigger-sync\n          description: \"Trigger an Airbyte sync job for a connection.\"\n          hints:\n            readOnly: false\n          call: \"airbyte.create-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-status\n          description: \"Check the status of an Airbyte sync job.\"\n          hints:\n            readOnly: true\n          call: \"airbyte.get-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workspaces\n          description: \"List Airbyte workspaces.\"\n          hints:\n     \
  \       readOnly: true\n          call: \"airbyte.list-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-source\n          description: \"Delete an Airbyte source connector.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"airbyte.delete-source\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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

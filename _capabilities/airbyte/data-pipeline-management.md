---
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
- create destination
- data integration
- list sync jobs
- manage workspaces.
- create a new data source.
- manage airbyte sources, destinations, connections, and sync jobs.
- create a new destination.
- get job status
- list connections
- list all destinations.
- monitor and trigger sync jobs.
- user, workspace, and organizational management.
- elt
- list airbyte workspaces.
- create a new airbyte data source connector.
- moving data between sources and destinations.
- list airbyte sync jobs with optional status filtering.
- list sync jobs.
- connectors
- list all airbyte data destination connectors.
- list workspaces
- etl
- manage data destination connectors.
- list workspaces.
- manage data source connectors.
- airbyte
- Platform Admin
- create a new airbyte data destination connector.
- trigger sync
- delete an airbyte source connector.
- create a new connection.
- create connection
- data engineering
- create an airbyte connection between a source and destination.
- manages airbyte workspaces, users, permissions, and organizational settings.
- Data Engineer
- builds and maintains data pipelines using airbyte connectors and connections.
- data
- create source
- delete source
- check the status of an airbyte sync job.
- trigger job
- list all airbyte data source connectors.
- list all data sources.
- list sources
- list all connections.
- list jobs
- trigger an airbyte sync job for a connection.
- monitoring and operating sync pipelines.
- list destinations
- manage source-to-destination connections.
- list airbyte connections between sources and destinations.
- data pipeline
- trigger a sync job.
- open source
slug: data-pipeline-management
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

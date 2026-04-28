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
- list all destinations.
- manage source-to-destination connections.
- create a new data source.
- list connections
- data engineering
- create a new airbyte data source connector.
- builds and maintains data pipelines using airbyte connectors and connections.
- monitoring and operating sync pipelines.
- list destinations
- airbyte
- data integration
- list all connections.
- trigger job
- trigger sync
- data pipeline
- Platform Admin
- create a new destination.
- delete an airbyte source connector.
- manage airbyte sources, destinations, connections, and sync jobs.
- user, workspace, and organizational management.
- list workspaces.
- connectors
- list airbyte connections between sources and destinations.
- list all data sources.
- create a new airbyte data destination connector.
- create destination
- trigger an airbyte sync job for a connection.
- create connection
- list sources
- monitor and trigger sync jobs.
- elt
- open source
- trigger a sync job.
- list workspaces
- list all airbyte data source connectors.
- delete source
- list sync jobs.
- data
- list all airbyte data destination connectors.
- create a new connection.
- list airbyte sync jobs with optional status filtering.
- check the status of an airbyte sync job.
- get job status
- list airbyte workspaces.
- Data Engineer
- manage data source connectors.
- list jobs
- etl
- create an airbyte connection between a source and destination.
- list sync jobs
- create source
- manage workspaces.
- moving data between sources and destinations.
- manage data destination connectors.
- manages airbyte workspaces, users, permissions, and organizational settings.
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

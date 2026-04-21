---
consumed_apis:
- cloud-control
description: Unified workflow for monitoring, incident response, and maintenance management across Oracle infrastructure using Enterprise Manager Cloud Control APIs. Designed for infrastructure administrators and operations teams.
layout: capability
name: Oracle Enterprise Manager Infrastructure Management
operations:
- description: List monitored targets
  method: GET
  name: list-targets
  path: /v1/targets
- description: Create a monitored target
  method: POST
  name: create-target
  path: /v1/targets
- description: Get target details
  method: GET
  name: get-target
  path: /v1/targets/{targetId}
- description: List incidents
  method: GET
  name: list-incidents
  path: /v1/incidents
- description: Get incident details
  method: GET
  name: get-incident
  path: /v1/incidents/{incidentId}
- description: List blackouts
  method: GET
  name: list-blackouts
  path: /v1/blackouts
- description: Get metric time series data
  method: GET
  name: get-metric-time-series
  path: /v1/metrics
personas: []
provider_name: Oracle Enterprise Manager
provider_slug: oracle-enterprise-manager
search_terms:
- get blackout
- infrastructure management
- list targets
- suppress an incident from active views
- delete blackout
- cloud management
- list incidents
- list monitored targets
- create a monitored target
- get target
- get target details
- enterprise manager
- infrastructure incidents
- maintenance windows
- monitored targets
- create a new monitored target
- performance metrics
- list metric groups available for a target
- oracle
- get metric time series
- get metric time series data for performance analysis
- get event
- clear an incident marking it as resolved
- get incident
- get incident details
- create target
- create a new blackout (maintenance window)
- delete a scheduled blackout
- clear incident
- enterprise management
- list global target properties for classification
- get metric time series data
- list global target properties
- suppress incident
- get details of a specific incident
- list monitored targets in enterprise manager
- monitoring
- database management
- incident details
- get details of a specific monitored target
- get configuration properties of a target
- get details of a specific monitoring event
- list blackouts (maintenance windows)
- list blackouts
- get target properties
- get details of a specific blackout
- list incidents in enterprise manager
- target details
- list metric groups
- create blackout
slug: infrastructure-management
tags:
- Oracle
- Enterprise Manager
- Infrastructure Management
- Monitoring
tools:
- description: List monitored targets in Enterprise Manager
  hints:
    openWorld: true
    readOnly: true
  name: list-targets
- description: Get details of a specific monitored target
  hints:
    readOnly: true
  name: get-target
- description: Create a new monitored target
  hints:
    readOnly: false
  name: create-target
- description: List incidents in Enterprise Manager
  hints:
    openWorld: true
    readOnly: true
  name: list-incidents
- description: Get details of a specific incident
  hints:
    readOnly: true
  name: get-incident
- description: Clear an incident marking it as resolved
  hints:
    readOnly: false
  name: clear-incident
- description: Suppress an incident from active views
  hints:
    readOnly: false
  name: suppress-incident
- description: List blackouts (maintenance windows)
  hints:
    openWorld: true
    readOnly: true
  name: list-blackouts
- description: Get details of a specific blackout
  hints:
    readOnly: true
  name: get-blackout
- description: Create a new blackout (maintenance window)
  hints:
    readOnly: false
  name: create-blackout
- description: Delete a scheduled blackout
  hints:
    destructive: true
    idempotent: true
  name: delete-blackout
- description: Get metric time series data for performance analysis
  hints:
    readOnly: true
  name: get-metric-time-series
- description: List metric groups available for a target
  hints:
    readOnly: true
  name: list-metric-groups
- description: Get details of a specific monitoring event
  hints:
    readOnly: true
  name: get-event
- description: Get configuration properties of a target
  hints:
    readOnly: true
  name: get-target-properties
- description: List global target properties for classification
  hints:
    readOnly: true
  name: list-global-target-properties
---

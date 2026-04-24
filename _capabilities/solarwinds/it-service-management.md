---
consumed_apis:
- service-desk
- orion
description: Workflow for IT service management combining Service Desk incident/change management with Orion infrastructure data for IT support and service delivery teams.
layout: capability
name: SolarWinds IT Service Management
operations:
- description: List incidents
  method: GET
  name: list-incidents
  path: /v1/incidents
- description: List service requests
  method: GET
  name: list-service-requests
  path: /v1/service-requests
- description: List change requests
  method: GET
  name: list-changes
  path: /v1/changes
- description: List hardware assets
  method: GET
  name: list-assets
  path: /v1/assets
personas: []
provider_name: SolarWinds
provider_slug: solarwinds
search_terms:
- observability
- ip address management
- log management
- list assets
- list service requests
- service desk
- get incident details
- create incident
- infrastructure
- get incident
- create a new incident
- incident management
- application monitoring
- itsm
- it management
- database monitoring
- change management
- list hardware assets
- query orion infrastructure data via swql
- query infrastructure
- network monitoring
- solarwinds
- asset management
- service request management
- list change requests
- list incidents
- list changes
- list service desk incidents
slug: it-service-management
tags:
- SolarWinds
- ITSM
- Service Desk
- Incident Management
tools:
- description: List service desk incidents
  hints:
    readOnly: true
  name: list-incidents
- description: Get incident details
  hints:
    readOnly: true
  name: get-incident
- description: Create a new incident
  hints:
    readOnly: false
  name: create-incident
- description: List service requests
  hints:
    readOnly: true
  name: list-service-requests
- description: List change requests
  hints:
    readOnly: true
  name: list-changes
- description: List hardware assets
  hints:
    readOnly: true
  name: list-assets
- description: Query Orion infrastructure data via SWQL
  hints:
    readOnly: true
  name: query-infrastructure
---

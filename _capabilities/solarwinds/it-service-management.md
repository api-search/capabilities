---
categories:
- incident-management
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
- service desk
- itsm
- query orion infrastructure data via swql
- database monitoring
- get incident details
- it management
- observability
- infrastructure
- get incident
- list hardware assets
- list changes
- log management
- solarwinds
- list service desk incidents
- change management
- query infrastructure
- create a new incident
- list assets
- list incidents
- incident management
- list change requests
- list service requests
- ip address management
- asset management
- create incident
- service request management
- application monitoring
- network monitoring
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

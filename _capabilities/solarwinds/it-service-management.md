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
- create incident
- itsm
- list service requests
- solarwinds
- incident management
- it management
- list incidents
- list assets
- service request management
- query infrastructure
- list hardware assets
- query orion infrastructure data via swql
- database monitoring
- create a new incident
- ip address management
- asset management
- service desk
- get incident details
- log management
- observability
- network monitoring
- infrastructure
- application monitoring
- get incident
- list changes
- change management
- list service desk incidents
- list change requests
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

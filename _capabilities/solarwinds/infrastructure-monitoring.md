---
categories: []
consumed_apis:
- orion
- pingdom
description: Workflow for monitoring network infrastructure and website uptime combining Orion Platform SWQL queries with Pingdom synthetic monitoring for network and IT operations teams.
layout: capability
name: SolarWinds Infrastructure Monitoring
operations:
- description: Execute a SWQL query
  method: GET
  name: query-swis
  path: /v1/query
- description: List Pingdom checks
  method: GET
  name: list-checks
  path: /v1/checks
- description: Get check details
  method: GET
  name: get-check
  path: /v1/checks
- description: Get check results
  method: GET
  name: get-results
  path: /v1/results
personas: []
provider_name: SolarWinds
provider_slug: solarwinds
search_terms:
- infrastructure monitoring
- get pingdom check results
- itsm
- get check details
- query swis
- solarwinds
- it management
- create a new pingdom monitoring check
- execute a swql query
- get results
- get check results
- get check
- uptime monitoring checks
- execute a swql query against orion platform
- get pingdom performance summary
- database monitoring
- ip address management
- check results
- list pingdom checks
- query orion
- log management
- create a monitored entity in orion
- observability
- network monitoring
- infrastructure
- application monitoring
- get pingdom check details
- list pingdom uptime monitoring checks
- create orion entity
- create check
- list checks
- get summary average
- swql query execution
- uptime monitoring
slug: infrastructure-monitoring
tags:
- SolarWinds
- Infrastructure Monitoring
- Network Monitoring
- Uptime Monitoring
tools:
- description: Execute a SWQL query against Orion Platform
  hints:
    readOnly: true
  name: query-orion
- description: Create a monitored entity in Orion
  hints:
    readOnly: false
  name: create-orion-entity
- description: List Pingdom uptime monitoring checks
  hints:
    readOnly: true
  name: list-checks
- description: Get Pingdom check details
  hints:
    readOnly: true
  name: get-check
- description: Create a new Pingdom monitoring check
  hints:
    readOnly: false
  name: create-check
- description: Get Pingdom check results
  hints:
    readOnly: true
  name: get-check-results
- description: Get Pingdom performance summary
  hints:
    readOnly: true
  name: get-summary-average
---

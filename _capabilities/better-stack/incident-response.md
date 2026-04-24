---
consumed_apis:
- better-stack
description: Unified incident response workflow combining Better Stack uptime monitoring, heartbeat monitoring, and incident management. Used by SRE teams and on-call engineers to detect, acknowledge, and resolve infrastructure incidents.
layout: capability
name: Better Stack Incident Response
operations:
- description: List all uptime monitors
  method: GET
  name: list-monitors
  path: /v1/monitors
- description: Create a new uptime monitor
  method: POST
  name: create-monitor
  path: /v1/monitors
- description: Get monitor details
  method: GET
  name: get-monitor
  path: /v1/monitors/{id}
- description: Update a monitor
  method: PATCH
  name: update-monitor
  path: /v1/monitors/{id}
- description: Delete a monitor
  method: DELETE
  name: delete-monitor
  path: /v1/monitors/{id}
- description: Get monitor availability summary
  method: GET
  name: get-monitor-availability
  path: /v1/monitors/{id}/availability
- description: List all heartbeats
  method: GET
  name: list-heartbeats
  path: /v1/heartbeats
- description: Create a heartbeat monitor
  method: POST
  name: create-heartbeat
  path: /v1/heartbeats
- description: List all incidents
  method: GET
  name: list-incidents
  path: /v1/incidents
- description: Create a manual incident
  method: POST
  name: create-incident
  path: /v1/incidents
- description: Get incident details
  method: GET
  name: get-incident
  path: /v1/incidents/{id}
- description: Delete an incident
  method: DELETE
  name: delete-incident
  path: /v1/incidents/{id}
- description: Acknowledge an active incident
  method: POST
  name: acknowledge-incident
  path: /v1/incidents/{id}/acknowledge
- description: Resolve an active incident
  method: POST
  name: resolve-incident
  path: /v1/incidents/{id}/resolve
personas:
- description: Site Reliability Engineer managing infrastructure uptime and incident response
  id: sre-engineer
  name: SRE Engineer
- description: Engineer on-call rotation responsible for responding to incidents
  id: on-call-engineer
  name: On-Call Engineer
provider_name: Better Stack
provider_slug: better-stack
search_terms:
- observability
- single incident operations
- create a new uptime monitor
- single monitor operations
- acknowledge an incident
- on call engineer
- monitor detection, incident acknowledgement, and resolution workflow for sre teams
- list all uptime monitors to check what is being monitored
- communicating service health to customers and stakeholders
- delete an incident
- create a heartbeat monitor
- acknowledge an active incident to indicate someone is working on it
- get details for a specific incident
- monitor management for uptime checks
- delete monitor
- monitoring
- create incident
- get incident details
- get availability for a heartbeat monitor
- list monitors
- get incident
- engineer on-call rotation responsible for responding to incidents
- acknowledge incident
- resolve incident
- delete a monitor
- incidents
- uptime and availability monitoring for services and scheduled jobs
- list heartbeats
- detection, acknowledgement, and resolution of service incidents
- update monitor
- get monitor
- get monitor details
- incident management
- get monitor availability summary
- get monitor availability
- resolve an incident
- list all heartbeat monitors for scheduled jobs
- delete incident
- create monitor
- list all heartbeats
- list all incidents
- create a manual incident
- site reliability engineer managing infrastructure uptime and incident response
- better stack
- resolve an active incident
- get details for a specific uptime monitor
- create a new uptime monitor for a url or api
- heartbeats
- acknowledge an active incident
- uptime
- update a monitor
- list all uptime monitors
- heartbeat monitor management
- get availability metrics for a monitor
- sre
- sre engineer
- logs
- status
- get heartbeat availability
- list incidents with optional date and filter parameters
- platform
- list incidents
- on-call
- managing team access and membership
- incident response
- monitor availability metrics
- create heartbeat
- resolve an active incident once the issue is fixed
slug: incident-response
tags:
- Better Stack
- Incident Response
- Monitoring
- On-Call
- Sre
tools:
- description: List all uptime monitors to check what is being monitored
  hints:
    openWorld: true
    readOnly: true
  name: list-monitors
- description: Create a new uptime monitor for a URL or API
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-monitor
- description: Get details for a specific uptime monitor
  hints:
    openWorld: false
    readOnly: true
  name: get-monitor
- description: Get availability metrics for a monitor
  hints:
    openWorld: false
    readOnly: true
  name: get-monitor-availability
- description: List all heartbeat monitors for scheduled jobs
  hints:
    openWorld: true
    readOnly: true
  name: list-heartbeats
- description: Get availability for a heartbeat monitor
  hints:
    openWorld: false
    readOnly: true
  name: get-heartbeat-availability
- description: List incidents with optional date and filter parameters
  hints:
    openWorld: true
    readOnly: true
  name: list-incidents
- description: Get details for a specific incident
  hints:
    openWorld: false
    readOnly: true
  name: get-incident
- description: Create a manual incident
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-incident
- description: Acknowledge an active incident to indicate someone is working on it
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: acknowledge-incident
- description: Resolve an active incident once the issue is fixed
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resolve-incident
---

---
categories:
- incident-management
consumed_apis:
- dd-incidents
- dd-events
- dd-monitors
description: Unified workflow for incident management combining incidents, events, and monitors. Used by incident commanders and on-call engineers for creating incidents, correlating events, and managing monitor alerts during outages.
layout: capability
name: Datadog Incident Management
operations:
- description: List incidents
  method: GET
  name: listIncidents
  path: /v1/incidents
- description: Create an incident
  method: POST
  name: createIncident
  path: /v1/incidents
- description: Get an incident
  method: GET
  name: getIncident
  path: /v1/incidents/{incident_id}
- description: Update an incident
  method: PATCH
  name: updateIncident
  path: /v1/incidents/{incident_id}
- description: Delete an incident
  method: DELETE
  name: deleteIncident
  path: /v1/incidents/{incident_id}
- description: List events
  method: GET
  name: listEvents
  path: /v1/events
- description: Post an event
  method: POST
  name: createEvent
  path: /v1/events
- description: Search events
  method: POST
  name: searchEvents
  path: /v1/events/search
- description: List monitors
  method: GET
  name: listMonitors
  path: /v1/monitors
- description: Get a monitor
  method: GET
  name: getMonitor
  path: /v1/monitors/{monitor_id}
- description: Mute a monitor
  method: POST
  name: muteMonitor
  path: /v1/monitors/{monitor_id}/mute
personas: []
provider_name: Datadog
provider_slug: datadog
search_terms:
- get monitor status
- create incident
- delete an incident
- events
- create event
- incident management
- muteMonitor
- update incident
- list incidents
- listEvents
- mute monitor
- get monitor
- platform
- list events for correlation
- unmute monitor
- createEvent
- updateIncident
- searchEvents
- listIncidents
- post an event
- create an incident
- individual incident operations
- create a new incident
- post an event during incident
- get a specific event
- search events
- getMonitor
- list incident teams
- get an incident
- listMonitors
- delete incident
- list monitors
- get incident details
- datadog
- mute monitor during incident
- dashboards
- t1
- deleteIncident
- getIncident
- list events
- get a monitor
- visualizations
- incidents
- monitor status
- analytics
- event correlation
- update an existing incident
- monitors
- get incident
- update an incident
- get event
- unmute a monitor after incident resolution
- mute a monitor
- individual monitor
- list monitors to check alert status
- createIncident
- monitoring
- search events related to incident
- mute a monitor during incident response
slug: incident-management
tags:
- Datadog
- Incident Management
- Incidents
- Events
- Monitors
tools:
- description: List incidents
  hints:
    readOnly: true
  name: list-incidents
- description: Get incident details
  hints:
    readOnly: true
  name: get-incident
- description: Create a new incident
  hints: {}
  name: create-incident
- description: Update an existing incident
  hints:
    idempotent: true
  name: update-incident
- description: Delete an incident
  hints:
    destructive: true
  name: delete-incident
- description: List incident teams
  hints:
    readOnly: true
  name: list-incident-teams
- description: List events for correlation
  hints:
    readOnly: true
  name: list-events
- description: Get a specific event
  hints:
    readOnly: true
  name: get-event
- description: Post an event during incident
  hints: {}
  name: create-event
- description: Search events related to incident
  hints:
    readOnly: true
  name: search-events
- description: List monitors to check alert status
  hints:
    readOnly: true
  name: list-monitors
- description: Get monitor status
  hints:
    readOnly: true
  name: get-monitor
- description: Mute a monitor during incident response
  hints: {}
  name: mute-monitor
- description: Unmute a monitor after incident resolution
  hints: {}
  name: unmute-monitor
---

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
- get an incident
- get incident details
- incidents
- get a monitor
- deleteIncident
- post an event
- searchEvents
- update an incident
- listEvents
- list monitors
- create incident
- platform
- list monitors to check alert status
- analytics
- create a new incident
- monitors
- get monitor status
- create event
- unmute monitor
- update an existing incident
- t1
- delete incident
- updateIncident
- events
- list events for correlation
- mute a monitor
- listMonitors
- post an event during incident
- visualizations
- individual monitor
- list incident teams
- list events
- get incident
- get monitor
- monitoring
- get a specific event
- dashboards
- incident management
- create an incident
- list incidents
- getIncident
- update incident
- get event
- datadog
- muteMonitor
- event correlation
- mute monitor during incident
- individual incident operations
- monitor status
- getMonitor
- search events
- search events related to incident
- listIncidents
- createIncident
- mute a monitor during incident response
- unmute a monitor after incident resolution
- mute monitor
- delete an incident
- createEvent
slug: incident-management
source_filename: incident-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Datadog Incident Management\"\n  description: \"Unified workflow for incident management combining incidents, events, and monitors. Used by incident commanders and on-call engineers for creating incidents, correlating events, and managing monitor alerts during outages.\"\n  tags:\n    - Datadog\n    - Incident Management\n    - Incidents\n    - Events\n    - Monitors\n  personas:\n    - Incident Commander\n    - On-Call Engineer\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      DATADOG_API_KEY: DATADOG_API_KEY\n      DATADOG_APP_KEY: DATADOG_APP_KEY\n\ncapability:\n  consumes:\n    - import: dd-incidents\n      location: \"./shared/incidents.yaml\"\n    - import: dd-events\n      location: \"./shared/events.yaml\"\n    - import: dd-monitors\n      location: \"./shared/monitors.yaml\"\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: dd-incident-mgmt-api\n  \
  \    description: \"Unified REST API for incident management workflows combining incidents, events, and monitors.\"\n      resources:\n        - path: /v1/incidents\n          name: incidents\n          description: \"Incident management\"\n          operations:\n            - method: GET\n              name: listIncidents\n              description: \"List incidents\"\n              call: \"dd-incidents.listIncidents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createIncident\n              description: \"Create an incident\"\n              call: \"dd-incidents.createIncident\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/incidents/{incident_id}\n          name: incident\n          description: \"Individual incident operations\"\n          operations:\n            - method: GET\n              name: getIncident\n\
  \              description: \"Get an incident\"\n              call: \"dd-incidents.getIncident\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: updateIncident\n              description: \"Update an incident\"\n              call: \"dd-incidents.updateIncident\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: deleteIncident\n              description: \"Delete an incident\"\n              call: \"dd-incidents.deleteIncident\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Event correlation\"\n          operations:\n            - method: GET\n              name: listEvents\n              description: \"List events\"\n              call: \"dd-events.listEvents\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createEvent\n              description: \"Post an event\"\n              call: \"dd-events.createEvent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events/search\n          name: events-search\n          description: \"Search events\"\n          operations:\n            - method: POST\n              name: searchEvents\n              description: \"Search events\"\n              call: \"dd-events.searchEvents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/monitors\n          name: monitors\n          description: \"Monitor status\"\n          operations:\n            - method: GET\n              name: listMonitors\n              description: \"List monitors\"\n              call: \"dd-monitors.listMonitors\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/monitors/{monitor_id}\n          name: monitor\n          description: \"Individual monitor\"\n          operations:\n            - method: GET\n              name: getMonitor\n              description: \"Get a monitor\"\n              call: \"dd-monitors.getMonitor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/monitors/{monitor_id}/mute\n          name: monitor-mute\n          description: \"Mute monitor during incident\"\n          operations:\n            - method: POST\n              name: muteMonitor\n              description: \"Mute a monitor\"\n              call: \"dd-monitors.muteMonitor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: dd-incident-mgmt-mcp\n      transport:\
  \ http\n      description: \"MCP server for AI-assisted incident management workflows.\"\n      tools:\n        - name: list-incidents\n          description: \"List incidents\"\n          call: \"dd-incidents.listIncidents\"\n          hints:\n            readOnly: true\n        - name: get-incident\n          description: \"Get incident details\"\n          call: \"dd-incidents.getIncident\"\n          hints:\n            readOnly: true\n        - name: create-incident\n          description: \"Create a new incident\"\n          call: \"dd-incidents.createIncident\"\n        - name: update-incident\n          description: \"Update an existing incident\"\n          call: \"dd-incidents.updateIncident\"\n          hints:\n            idempotent: true\n        - name: delete-incident\n          description: \"Delete an incident\"\n          call: \"dd-incidents.deleteIncident\"\n          hints:\n            destructive: true\n        - name: list-incident-teams\n          description:\
  \ \"List incident teams\"\n          call: \"dd-incidents.listIncidentTeams\"\n          hints:\n            readOnly: true\n        - name: list-events\n          description: \"List events for correlation\"\n          call: \"dd-events.listEvents\"\n          hints:\n            readOnly: true\n        - name: get-event\n          description: \"Get a specific event\"\n          call: \"dd-events.getEvent\"\n          hints:\n            readOnly: true\n        - name: create-event\n          description: \"Post an event during incident\"\n          call: \"dd-events.createEvent\"\n        - name: search-events\n          description: \"Search events related to incident\"\n          call: \"dd-events.searchEvents\"\n          hints:\n            readOnly: true\n        - name: list-monitors\n          description: \"List monitors to check alert status\"\n          call: \"dd-monitors.listMonitors\"\n          hints:\n            readOnly: true\n        - name: get-monitor\n         \
  \ description: \"Get monitor status\"\n          call: \"dd-monitors.getMonitor\"\n          hints:\n            readOnly: true\n        - name: mute-monitor\n          description: \"Mute a monitor during incident response\"\n          call: \"dd-monitors.muteMonitor\"\n        - name: unmute-monitor\n          description: \"Unmute a monitor after incident resolution\"\n          call: \"dd-monitors.unmuteMonitor\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/datadog/refs/heads/main/capabilities/incident-management.yaml
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

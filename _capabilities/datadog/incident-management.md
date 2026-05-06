---
categories:
- incident-management
consumed_apis: []
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
- create event
- list events
- incidents
- individual monitor
- update an incident
- update incident
- monitor status
- visualizations
- analytics
- listEvents
- get event
- mute a monitor
- deleteIncident
- search events related to incident
- event correlation
- create incident
- search events
- dashboards
- unmute a monitor after incident resolution
- individual incident operations
- list monitors
- list events for correlation
- updateIncident
- monitoring
- datadog
- post an event
- monitors
- getIncident
- delete incident
- muteMonitor
- list incident teams
- delete an incident
- mute a monitor during incident response
- create a new incident
- get a specific event
- update an existing incident
- t1
- unmute monitor
- get incident details
- createEvent
- get a monitor
- searchEvents
- getMonitor
- list monitors to check alert status
- create an incident
- get an incident
- platform
- post an event during incident
- get incident
- listIncidents
- list incidents
- mute monitor
- mute monitor during incident
- get monitor status
- incident management
- get monitor
- events
- listMonitors
- createIncident
slug: incident-management
source_filename: incident-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Datadog Incident Management\n  description: Unified workflow for incident management combining incidents, events, and monitors. Used by incident commanders\n    and on-call engineers for creating incidents, correlating events, and managing monitor alerts during outages.\n  tags:\n  - Datadog\n  - Incident Management\n  - Incidents\n  - Events\n  - Monitors\n  personas:\n  - Incident Commander\n  - On-Call Engineer\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DATADOG_API_KEY: DATADOG_API_KEY\n    DATADOG_APP_KEY: DATADOG_APP_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: dd-incidents\n    baseUri: https://api.datadoghq.com\n    description: Datadog Incidents API for managing incident records and incident teams.\n    authentication:\n      type: apikey\n      headers:\n        DD-API-KEY: '{{DATADOG_API_KEY}}'\n        DD-APPLICATION-KEY: '{{DATADOG_APP_KEY}}'\n    resources:\n\
  \    - name: incidents\n      path: /api/v2/incidents\n      description: Incident collection operations.\n      operations:\n      - name: createIncident\n        method: POST\n        description: Create an incident.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listIncidents\n        method: GET\n        description: List incidents.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incident\n      path: /api/v2/incidents/{incident_id}\n      description: Individual incident operations.\n      operations:\n      - name: getIncident\n        method: GET\n        description: Get the details of an incident.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateIncident\n   \
  \     method: PATCH\n        description: Update an existing incident.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteIncident\n        method: DELETE\n        description: Delete an existing incident.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incident-teams\n      path: /api/v2/teams\n      description: Incident team management.\n      operations:\n      - name: createIncidentTeam\n        method: POST\n        description: Create a new incident team.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listIncidentTeams\n        method: GET\n        description: List incident teams.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: getIncidentTeam\n        method: GET\n        path: /api/v2/teams/{team_id}\n        description: Get details of an incident team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateIncidentTeam\n        method: PATCH\n        path: /api/v2/teams/{team_id}\n        description: Update an existing incident team.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteIncidentTeam\n        method: DELETE\n        path: /api/v2/teams/{team_id}\n        description: Delete an existing incident team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: dd-events\n    baseUri: https://api.datadoghq.com\n\
  \    description: Datadog Events API for posting, listing, retrieving, and searching events.\n    authentication:\n      type: apikey\n      headers:\n        DD-API-KEY: '{{DATADOG_API_KEY}}'\n        DD-APPLICATION-KEY: '{{DATADOG_APP_KEY}}'\n    resources:\n    - name: events\n      path: /api/v2/events\n      description: Event collection operations.\n      operations:\n      - name: createEvent\n        method: POST\n        description: Post an event.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listEvents\n        method: GET\n        description: Get a list of events.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event\n      path: /api/v2/events/{event_id}\n      description: Individual event operations.\n      operations:\n      - name: getEvent\n    \
  \    method: GET\n        description: Get an event.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-search\n      path: /api/v2/events/search\n      description: Search events with structured queries.\n      operations:\n      - name: searchEvents\n        method: POST\n        description: Search events.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: dd-monitors\n    baseUri: https://api.datadoghq.com\n    description: Datadog Monitors API for creating, reading, updating, deleting, muting, unmuting, and validating monitors.\n    authentication:\n      type: apikey\n      headers:\n        DD-API-KEY: '{{DATADOG_API_KEY}}'\n        DD-APPLICATION-KEY: '{{DATADOG_APP_KEY}}'\n    resources:\n    - name: monitors\n      path: /api/v1/monitor\n\
  \      description: Monitor collection operations.\n      operations:\n      - name: createMonitor\n        method: POST\n        description: Create a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listMonitors\n        method: GET\n        description: List all monitors.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitor\n      path: /api/v1/monitor/{monitor_id}\n      description: Individual monitor operations.\n      operations:\n      - name: getMonitor\n        method: GET\n        description: Get a monitor.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateMonitor\n        method: PUT\n        description: Edit a monitor.\n        body:\n         \
  \ type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteMonitor\n        method: DELETE\n        description: Delete a monitor.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitor-muting\n      path: /api/v1/monitor/{monitor_id}\n      description: Mute and unmute monitor notifications.\n      operations:\n      - name: muteMonitor\n        method: POST\n        path: /api/v1/monitor/{monitor_id}/mute\n        description: Mute a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unmuteMonitor\n        method: POST\n        path: /api/v1/monitor/{monitor_id}/unmute\n        description: Unmute a monitor.\n        body:\n          type: json\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitor-validation\n      path: /api/v1/monitor/validate\n      description: Validate monitor configurations before creation.\n      operations:\n      - name: validateMonitor\n        method: POST\n        description: Validate a monitor.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: dd-incident-mgmt-api\n    description: Unified REST API for incident management workflows combining incidents, events, and monitors.\n    resources:\n    - path: /v1/incidents\n      name: incidents\n      description: Incident management\n      operations:\n      - method: GET\n        name: listIncidents\n        description: List incidents\n        call: dd-incidents.listIncidents\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n      - method: POST\n        name: createIncident\n        description: Create an incident\n        call: dd-incidents.createIncident\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/incidents/{incident_id}\n      name: incident\n      description: Individual incident operations\n      operations:\n      - method: GET\n        name: getIncident\n        description: Get an incident\n        call: dd-incidents.getIncident\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: updateIncident\n        description: Update an incident\n        call: dd-incidents.updateIncident\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: deleteIncident\n        description: Delete an incident\n        call: dd-incidents.deleteIncident\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/events\n      name: events\n      description: Event correlation\n      operations:\n      - method: GET\n        name: listEvents\n        description: List events\n        call: dd-events.listEvents\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: createEvent\n        description: Post an event\n        call: dd-events.createEvent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/search\n      name: events-search\n      description: Search events\n      operations:\n      - method: POST\n        name: searchEvents\n        description: Search events\n        call: dd-events.searchEvents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors\n      name: monitors\n      description: Monitor status\n      operations:\n      - method: GET\n        name: listMonitors\n        description: List monitors\n        call:\
  \ dd-monitors.listMonitors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors/{monitor_id}\n      name: monitor\n      description: Individual monitor\n      operations:\n      - method: GET\n        name: getMonitor\n        description: Get a monitor\n        call: dd-monitors.getMonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitors/{monitor_id}/mute\n      name: monitor-mute\n      description: Mute monitor during incident\n      operations:\n      - method: POST\n        name: muteMonitor\n        description: Mute a monitor\n        call: dd-monitors.muteMonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: dd-incident-mgmt-mcp\n    transport: http\n    description: MCP server for AI-assisted incident management workflows.\n    tools:\n    - name: list-incidents\n      description: List incidents\n      call:\
  \ dd-incidents.listIncidents\n      hints:\n        readOnly: true\n    - name: get-incident\n      description: Get incident details\n      call: dd-incidents.getIncident\n      hints:\n        readOnly: true\n    - name: create-incident\n      description: Create a new incident\n      call: dd-incidents.createIncident\n    - name: update-incident\n      description: Update an existing incident\n      call: dd-incidents.updateIncident\n      hints:\n        idempotent: true\n    - name: delete-incident\n      description: Delete an incident\n      call: dd-incidents.deleteIncident\n      hints:\n        destructive: true\n    - name: list-incident-teams\n      description: List incident teams\n      call: dd-incidents.listIncidentTeams\n      hints:\n        readOnly: true\n    - name: list-events\n      description: List events for correlation\n      call: dd-events.listEvents\n      hints:\n        readOnly: true\n    - name: get-event\n      description: Get a specific event\n    \
  \  call: dd-events.getEvent\n      hints:\n        readOnly: true\n    - name: create-event\n      description: Post an event during incident\n      call: dd-events.createEvent\n    - name: search-events\n      description: Search events related to incident\n      call: dd-events.searchEvents\n      hints:\n        readOnly: true\n    - name: list-monitors\n      description: List monitors to check alert status\n      call: dd-monitors.listMonitors\n      hints:\n        readOnly: true\n    - name: get-monitor\n      description: Get monitor status\n      call: dd-monitors.getMonitor\n      hints:\n        readOnly: true\n    - name: mute-monitor\n      description: Mute a monitor during incident response\n      call: dd-monitors.muteMonitor\n    - name: unmute-monitor\n      description: Unmute a monitor after incident resolution\n      call: dd-monitors.unmuteMonitor\n"
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

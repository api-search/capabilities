---
categories: []
consumed_apis: []
description: A capability mashing up event-platform attendee data (Cvent / Eventbrite) with CRM contact context for booth-staff agents.
layout: capability
name: Event Cloud Attendee Context Mashup
operations:
- description: ''
  method: GET
  name: list-attendees
  path: /events/{{event_id}}/attendees
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- list attendees
- events
- governance
- mcp
- capabilities
- naftiko
- api integration
- eventbrite
- ai
slug: event-cloud-attendee-context-mashup
source_filename: event-cloud-attendee-context-mashup.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Event Cloud Attendee Context Mashup\n  description: A capability mashing up event-platform attendee data (Cvent / Eventbrite) with CRM contact context for booth-staff agents.\n  tags: [Naftiko, Eventbrite, Events]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: eventbrite-env\n  keys: {EVENTBRITE_TOKEN: EVENTBRITE_TOKEN}\ncapability:\n  consumes:\n  - namespace: eventbrite\n    type: http\n    baseUri: https://www.eventbriteapi.com\n    authentication: {type: bearer, token: '{{EVENTBRITE_TOKEN}}'}\n    resources:\n    - name: event-attendees\n      path: '/v3/events/{{event_id}}/attendees'\n      operations:\n      - {name: list-attendees, method: GET, inputParameters: [{name: event_id, in: path}]}\n    - name: attendee\n      path: '/v3/events/{{event_id}}/attendees/{{attendee_id}}'\n      operations:\n      - {name: get-attendee, method: GET, inputParameters: [{name: event_id, in: path}, {name: attendee_id, in:\
  \ path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: event-cloud-attendee-context-mashup-rest\n    description: REST surface for attendee mashup.\n    resources:\n    - {name: attendees, path: '/events/{{event_id}}/attendees', operations: [{method: GET, name: list-attendees, inputParameters: [{name: event_id, in: path, type: string}], call: eventbrite.list-attendees}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: event-cloud-attendee-context-mashup-mcp\n    description: MCP for attendee mashup.\n    tools:\n    - name: list-attendees\n      hints: {readOnly: true}\n      inputParameters: [{name: event_id, type: string, required: true}]\n      call: eventbrite.list-attendees\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: event-cloud-attendee-context-mashup-skills\n    description: Skill for attendee mashup.\n    skills:\n    - name: event-cloud-attendee-context-mashup\n      description: Attendee + CRM\
  \ mashup.\n      location: file:///opt/naftiko/skills/event-cloud-attendee-context-mashup\n      allowed-tools: list-attendees\n      tools:\n      - {name: list-attendees, from: {sourceNamespace: event-cloud-attendee-context-mashup-mcp, action: list-attendees}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/event-cloud-attendee-context-mashup.yaml
tags:
- Naftiko
- Eventbrite
- Events
tools:
- description: ''
  hints:
    readOnly: true
  name: list-attendees
---

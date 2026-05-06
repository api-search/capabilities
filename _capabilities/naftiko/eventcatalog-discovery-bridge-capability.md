---
categories: []
consumed_apis: []
description: A bridge capability between EventCatalog (event documentation) and Naftiko — discovered events appear as Naftiko event-driven capabilities automatically.
layout: capability
name: Eventcatalog Discovery Bridge Capability
operations:
- description: ''
  method: GET
  name: list-discovered-events
  path: /events
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- eventcatalog
- discovery
- api integration
- governance
- spec-driven integration
- ai
- list discovered events
- mcp
- capabilities
- get event
slug: eventcatalog-discovery-bridge-capability
source_filename: eventcatalog-discovery-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Eventcatalog Discovery Bridge Capability\n  description: A bridge capability between EventCatalog (event documentation) and Naftiko — discovered events appear as Naftiko event-driven capabilities automatically.\n  tags: [Naftiko, EventCatalog, Discovery]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: eventcatalog-env\n  keys: {EVENTCATALOG_HOST: EVENTCATALOG_HOST}\ncapability:\n  consumes:\n  - namespace: eventcatalog\n    type: http\n    baseUri: https://{{EVENTCATALOG_HOST}}\n    resources:\n    - {name: events, path: /api/events, operations: [{name: list-events, method: GET}]}\n    - name: event\n      path: /api/events/{{event_name}}\n      operations:\n      - {name: get-event, method: GET, inputParameters: [{name: event_name, in: path}]}\n    - {name: services, path: /api/services, operations: [{name: list-services, method: GET}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace:\
  \ eventcatalog-discovery-bridge-capability-rest\n    description: REST surface bridging EventCatalog discovery into Naftiko.\n    resources:\n    - {name: events, path: /events, operations: [{method: GET, name: list-discovered-events, call: eventcatalog.list-events}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: eventcatalog-discovery-bridge-capability-mcp\n    description: MCP for EventCatalog discovery.\n    tools:\n    - {name: list-discovered-events, hints: {readOnly: true}, call: eventcatalog.list-events}\n    - name: get-event\n      hints: {readOnly: true}\n      inputParameters: [{name: event_name, type: string, required: true}]\n      call: eventcatalog.get-event\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: eventcatalog-discovery-bridge-capability-skills\n    description: Skill for EventCatalog bridge.\n    skills:\n    - name: eventcatalog-discovery-bridge-capability\n      description: EventCatalog discovery bridge.\n      location:\
  \ file:///opt/naftiko/skills/eventcatalog-discovery-bridge-capability\n      allowed-tools: list-discovered-events,get-event\n      tools:\n      - {name: list-discovered-events, from: {sourceNamespace: eventcatalog-discovery-bridge-capability-mcp, action: list-discovered-events}}\n      - {name: get-event, from: {sourceNamespace: eventcatalog-discovery-bridge-capability-mcp, action: get-event}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/eventcatalog-discovery-bridge-capability.yaml
tags:
- Naftiko
- EventCatalog
- Discovery
tools:
- description: ''
  hints:
    readOnly: true
  name: list-discovered-events
- description: ''
  hints:
    readOnly: true
  name: get-event
---

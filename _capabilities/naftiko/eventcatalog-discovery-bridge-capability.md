---
categories: []
consumed_apis: []
description: A capability that consumes EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable.
layout: capability
name: Eventcatalog Discovery Bridge Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- a capability that consumes eventcatalog inventory and exposes the event + schema-registry payload as mcp tools the ai assistant can query alongside rest endpoints, so event-driven and request-response surfaces are equally discoverable.
- ai
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: eventcatalog-discovery-bridge-capability
source_filename: eventcatalog-discovery-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Eventcatalog Discovery Bridge Capability\n  description: A capability that consumes EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: eventcatalog-discovery-bridge-capability-rest\n    description: REST API for\
  \ Eventcatalog Discovery Bridge Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: eventcatalog-discovery-bridge-capability-mcp\n    description: MCP server exposing Eventcatalog Discovery Bridge Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that consumes EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: eventcatalog-discovery-bridge-capability-skills\n    description: Agent Skill bundle for Eventcatalog Discovery Bridge Capability.\n    skills:\n    - name: eventcatalog-discovery-bridge-capability\n\
  \      description: A capability that consumes EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable.\n      location: file:///opt/naftiko/skills/eventcatalog-discovery-bridge-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that consumes EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable.\n        from:\n          sourceNamespace: eventcatalog-discovery-bridge-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/eventcatalog-discovery-bridge-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that consumes EventCatalog inventory and exposes the event + schema-registry payload as MCP tools the AI assistant can query alongside REST endpoints, so event-driven and request-response surfaces are equally discoverable.
  hints:
    readOnly: true
  name: example
---

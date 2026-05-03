---
categories: []
consumed_apis: []
description: A composite MCP tool that mashes Event Cloud attendee + session + registration endpoints into one business-case-driven agent surface (per Jeff's "composite tools, not 1:1 mirrors").
layout: capability
name: Event Cloud Attendee Context Mashup
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- example
- mcp
- ai
- naftiko
- a composite mcp tool that mashes event cloud attendee + session + registration endpoints into one business-case-driven agent surface (per jeff's "composite tools, not 1:1 mirrors").
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: event-cloud-attendee-context-mashup
source_filename: event-cloud-attendee-context-mashup.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Event Cloud Attendee Context Mashup\n  description: A composite MCP tool that mashes Event Cloud attendee + session + registration endpoints into one business-case-driven agent surface (per Jeff's \"composite tools, not 1:1 mirrors\").\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: event-cloud-attendee-context-mashup-rest\n    description: REST API for Event Cloud Attendee Context Mashup.\n    resources:\n    - name:\
  \ example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: event-cloud-attendee-context-mashup-mcp\n    description: MCP server exposing Event Cloud Attendee Context Mashup for AI agents.\n    tools:\n    - name: example\n      description: A composite MCP tool that mashes Event Cloud attendee + session + registration endpoints into one business-case-driven agent surface (per Jeff's \"composite tools, not 1:1 mirrors\").\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: event-cloud-attendee-context-mashup-skills\n    description: Agent Skill bundle for Event Cloud Attendee Context Mashup.\n    skills:\n    - name: event-cloud-attendee-context-mashup\n      description: A composite MCP tool that mashes Event Cloud attendee + session + registration endpoints\
  \ into one business-case-driven agent surface (per Jeff's \"composite tools, not 1:1 mirrors\").\n      location: file:///opt/naftiko/skills/event-cloud-attendee-context-mashup\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A composite MCP tool that mashes Event Cloud attendee + session + registration endpoints into one business-case-driven agent surface (per Jeff's \"composite tools, not 1:1 mirrors\").\n        from:\n          sourceNamespace: event-cloud-attendee-context-mashup-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/event-cloud-attendee-context-mashup.yaml
tags:
- Naftiko
tools:
- description: A composite MCP tool that mashes Event Cloud attendee + session + registration endpoints into one business-case-driven agent surface (per Jeff's "composite tools, not 1:1 mirrors").
  hints:
    readOnly: true
  name: example
---

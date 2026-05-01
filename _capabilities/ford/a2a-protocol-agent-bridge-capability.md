---
categories: []
consumed_apis:
- ford
description: A capability that exposes Ford's Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford A2a Protocol Agent Bridge Capability
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- exposes
- ford
- naftiko
slug: a2a-protocol-agent-bridge-capability
source_filename: a2a-protocol-agent-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford A2a Protocol Agent Bridge Capability
    description: A capability that exposes Ford's Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.
    tags:
    - Ford
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: ford-env
    description: Ford credentials.
    keys:
      FORD_API_KEY: FORD_API_KEY
  capability:
    consumes:
    - namespace: ford
      type: http
      baseUri: https://api.ford.com
      authentication:
        type: bearer
        token: '{{FORD_API_KEY}}'
      resources:
      - name: example
        path: /example
        operations:
        - name: example-op
          method: GET
    exposes:
    - type: rest
      address: 0.0.0.0
      port: 8080
      namespace: a2a-protocol-agent-bridge-capability-rest
      description: REST API for Ford A2a Protocol Agent Bridge Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: ford.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: a2a-protocol-agent-bridge-capability-mcp
      description: MCP server exposing Ford A2a Protocol Agent Bridge Capability for AI agents.
      tools:
      - name: example
        description: A capability that exposes Ford's Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: a2a-protocol-agent-bridge-capability-skills
      description: Agent Skill bundle for Ford A2a Protocol Agent Bridge Capability.
      skills:
      - name: a2a-protocol-agent-bridge-capability
        description: A capability that exposes Ford's Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.
        location: file:///opt/naftiko/skills/a2a-protocol-agent-bridge-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that exposes Ford's Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability.
          from:
            sourceNamespace: a2a-protocol-agent-bridge-capability-mcp
            action: example
---

A capability that exposes Ford's Naftiko-managed capabilities via Google's A2A (agent-to-agent) protocol in addition to MCP, so cross-vendor agent calls land on the same governed capability. Darrell Miller's A2A work at Microsoft is one of the cross-vendor anchors he is tracking; A2A exposure on Ford capabilities is the artifact that demonstrates Naftiko is a multi-protocol substrate, not a single-protocol gateway.

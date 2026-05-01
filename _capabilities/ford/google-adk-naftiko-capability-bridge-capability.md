---
categories: []
consumed_apis:
- ford
description: A capability that bridges Google's Agent Development Kit (ADK) into Ford's Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Google Adk Naftiko Capability Bridge Capability
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- bridges
- google
- agent
slug: google-adk-naftiko-capability-bridge-capability
source_filename: google-adk-naftiko-capability-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: |
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Google Adk Naftiko Capability Bridge Capability
    description: A capability that bridges Google's Agent Development Kit (ADK) into Ford's Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents.
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
      namespace: google-adk-naftiko-capability-bridge-capability-rest
      description: REST API for Ford Google Adk Naftiko Capability Bridge Capability.
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
      namespace: google-adk-naftiko-capability-bridge-capability-mcp
      description: MCP server exposing Ford Google Adk Naftiko Capability Bridge Capability for AI agents.
      tools:
      - name: example
        description: A capability that bridges Google's Agent Development Kit (ADK) into Ford's Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: google-adk-naftiko-capability-bridge-capability-skills
      description: Agent Skill bundle for Ford Google Adk Naftiko Capability Bridge Capability.
      skills:
      - name: google-adk-naftiko-capability-bridge-capability
        description: A capability that bridges Google's Agent Development Kit (ADK) into Ford's Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents.
        location: file:///opt/naftiko/skills/google-adk-naftiko-capability-bridge-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that bridges Google's Agent Development Kit (ADK) into Ford's Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents.
          from:
            sourceNamespace: google-adk-naftiko-capability-bridge-capability-mcp
            action: example
---

A capability that bridges Google's Agent Development Kit (ADK) into Ford's Naftiko capability layer so ADK-built agents call governed capabilities through the same MCP surface as Microsoft-built agents. His build-vs-buy / which-platform question across Microsoft + Google needs a Naftiko-side artifact that doesn't pick a side; this is the artifact that makes Naftiko look like multi-vendor agent substrate.

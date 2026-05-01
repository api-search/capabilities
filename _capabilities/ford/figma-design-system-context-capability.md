---
categories: []
consumed_apis:
- ford
description: A capability that consumes Ford's Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual Ford brand library instead of hallucinating component names.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Figma Design System Context Capability
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- consumes
- ford
- figma
slug: figma-design-system-context-capability
source_filename: figma-design-system-context-capability.yaml
source_heading: Capability Spec
source_yaml: |
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Figma Design System Context Capability
    description: A capability that consumes Ford's Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual Ford brand library instead of hallucinating component names.
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
      namespace: figma-design-system-context-capability-rest
      description: REST API for Ford Figma Design System Context Capability.
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
      namespace: figma-design-system-context-capability-mcp
      description: MCP server exposing Ford Figma Design System Context Capability for AI agents.
      tools:
      - name: example
        description: A capability that consumes Ford's Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual Ford brand library instead of hallucinating component names.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: figma-design-system-context-capability-skills
      description: Agent Skill bundle for Ford Figma Design System Context Capability.
      skills:
      - name: figma-design-system-context-capability
        description: A capability that consumes Ford's Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual Ford brand library instead of hallucinating component names.
        location: file:///opt/naftiko/skills/figma-design-system-context-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes Ford's Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual Ford brand library instead of hallucinating component names.
          from:
            sourceNamespace: figma-design-system-context-capability-mcp
            action: example
---

A capability that consumes Ford's Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual Ford brand library instead of hallucinating component names. The third-party MCP allow-list capability already brings the Figma MCP server in under security review; this is the Ford-shaped surface that makes Figma context callable as a governed Naftiko capability with the same identity, audit, and cost-attribution treatment as every other capability in the fleet.

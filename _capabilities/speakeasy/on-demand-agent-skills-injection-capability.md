---
categories: []
consumed_apis:
- speakeasy
description: A capability that consumes a Speakeasy-generated agent skill manifest and exposes a single MCP tool that injects it on-demand into a coding agent's context.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Daniel Kovac
name: Speakeasy On Demand Agent Skills Injection Capability
operations: []
personas: []
provider_name: Speakeasy
provider_slug: speakeasy
search_terms:
- capability
- that
- consumes
- speakeasy
- generated
slug: on-demand-agent-skills-injection-capability
source_filename: on-demand-agent-skills-injection-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Speakeasy On Demand Agent Skills Injection Capability
    description: A capability that consumes a Speakeasy-generated agent skill manifest and exposes a single MCP tool that injects it on-demand into a coding agent's context.
    tags:
    - Speakeasy
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: speakeasy-env
    description: Speakeasy credentials.
    keys:
      SPEAKEASY_API_KEY: SPEAKEASY_API_KEY
  capability:
    consumes:
    - namespace: speakeasy
      type: http
      baseUri: https://api.speakeasy.com
      authentication:
        type: bearer
        token: '{{SPEAKEASY_API_KEY}}'
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
      namespace: on-demand-agent-skills-injection-capability-rest
      description: REST API for Speakeasy On Demand Agent Skills Injection Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: speakeasy.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: on-demand-agent-skills-injection-capability-mcp
      description: MCP server exposing Speakeasy On Demand Agent Skills Injection Capability for AI agents.
      tools:
      - name: example
        description: A capability that consumes a Speakeasy-generated agent skill manifest and exposes a single MCP tool that injects it on-demand into a coding agent's context.
        hints:
          readOnly: true
        call: speakeasy.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: on-demand-agent-skills-injection-capability-skills
      description: Agent Skill bundle for Speakeasy On Demand Agent Skills Injection Capability.
      skills:
      - name: on-demand-agent-skills-injection-capability
        description: A capability that consumes a Speakeasy-generated agent skill manifest and exposes a single MCP tool that injects it on-demand into a coding agent's context.
        location: file:///opt/naftiko/skills/on-demand-agent-skills-injection-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes a Speakeasy-generated agent skill manifest and exposes a single MCP tool that injects it on-demand into a coding agent's context.
          from:
            sourceNamespace: on-demand-agent-skills-injection-capability-mcp
            action: example
---

A capability that consumes a Speakeasy-generated agent skill manifest and exposes a single MCP tool that injects it on-demand into a coding agent's context. His Speakeasy feature is exactly this on-demand pattern; making it Naftiko-callable is the joint reference architecture.

---
categories: []
consumed_apis:
- humana
description: A capability annotated against SDI "Deterministic Foundation for Agents" as the agentic-care thought-leadership hook.
layout: capability
naftiko_layer: proposed
naftiko_partner: Humana
name: Humana Deterministic Agentic Care Capability
operations: []
personas: []
provider_name: Humana
provider_slug: humana
search_terms:
- capability
- annotated
- against
- deterministic
- foundation
slug: deterministic-agentic-care-capability
source_filename: deterministic-agentic-care-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Humana Deterministic Agentic Care Capability
    description: A capability annotated against SDI "Deterministic Foundation for Agents" as the agentic-care thought-leadership hook.
    tags:
    - Humana
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: humana-env
    description: Humana credentials.
    keys:
      HUMANA_API_KEY: HUMANA_API_KEY
  capability:
    consumes:
    - namespace: humana
      type: http
      baseUri: https://api.humana.com
      authentication:
        type: bearer
        token: '{{HUMANA_API_KEY}}'
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
      namespace: deterministic-agentic-care-capability-rest
      description: REST API for Humana Deterministic Agentic Care Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: humana.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: deterministic-agentic-care-capability-mcp
      description: MCP server exposing Humana Deterministic Agentic Care Capability for AI agents.
      tools:
      - name: example
        description: A capability annotated against SDI "Deterministic Foundation for Agents" as the agentic-care thought-leadership hook.
        hints:
          readOnly: true
        call: humana.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: deterministic-agentic-care-capability-skills
      description: Agent Skill bundle for Humana Deterministic Agentic Care Capability.
      skills:
      - name: deterministic-agentic-care-capability
        description: A capability annotated against SDI "Deterministic Foundation for Agents" as the agentic-care thought-leadership hook.
        location: file:///opt/naftiko/skills/deterministic-agentic-care-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability annotated against SDI "Deterministic Foundation for Agents" as the agentic-care thought-leadership hook.
          from:
            sourceNamespace: deterministic-agentic-care-capability-mcp
            action: example
---

A capability annotated against SDI "Deterministic Foundation for Agents" as the agentic-care thought-leadership hook. Healthcare AI risk is the conversation; deterministic-vs-hallucinated is the differentiator.

---
categories: []
consumed_apis:
- vanguard
description: 'A capability that ticks the SA evaluation rubric: Multi-Step Orchestration + JSONPath + Circuit Breaker + Resilience Metrics + governance + observability dashboard.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Vanguard
name: Vanguard Solutions Architect Checklist Capability
operations: []
personas: []
provider_name: Vanguard
provider_slug: vanguard
search_terms:
- capability
- that
- ticks
- evaluation
- rubric
slug: solutions-architect-checklist-capability
source_filename: solutions-architect-checklist-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vanguard Solutions Architect Checklist Capability
    description: 'A capability that ticks the SA evaluation rubric: Multi-Step Orchestration + JSONPath + Circuit Breaker + Resilience Metrics + governance + observability dashboard.'
    tags:
    - Vanguard
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: vanguard-env
    description: Vanguard credentials.
    keys:
      VANGUARD_API_KEY: VANGUARD_API_KEY
  capability:
    consumes:
    - namespace: vanguard
      type: http
      baseUri: https://api.vanguard.com
      authentication:
        type: bearer
        token: '{{VANGUARD_API_KEY}}'
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
      namespace: solutions-architect-checklist-capability-rest
      description: REST API for Vanguard Solutions Architect Checklist Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: vanguard.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: solutions-architect-checklist-capability-mcp
      description: MCP server exposing Vanguard Solutions Architect Checklist Capability for AI agents.
      tools:
      - name: example
        description: 'A capability that ticks the SA evaluation rubric: Multi-Step Orchestration + JSONPath + Circuit Breaker + Resilience Metrics + governance + observability dashboard.'
        hints:
          readOnly: true
        call: vanguard.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: solutions-architect-checklist-capability-skills
      description: Agent Skill bundle for Vanguard Solutions Architect Checklist Capability.
      skills:
      - name: solutions-architect-checklist-capability
        description: 'A capability that ticks the SA evaluation rubric: Multi-Step Orchestration + JSONPath + Circuit Breaker + Resilience Metrics + governance + observability dashboard.'
        location: file:///opt/naftiko/skills/solutions-architect-checklist-capability
        allowed-tools: example
        tools:
        - name: example
          description: 'A capability that ticks the SA evaluation rubric: Multi-Step Orchestration + JSONPath + Circuit Breaker + Resilience Metrics + governance + observability dashboard.'
          from:
            sourceNamespace: solutions-architect-checklist-capability-mcp
            action: example
---

A capability that ticks the SA evaluation rubric: Multi-Step Orchestration + JSONPath + Circuit Breaker + Resilience Metrics + governance + observability dashboard. **Paul Tihansky's** Solutions Architect role evaluates integration patterns; his recommendations explicitly call this list out as the architect's checklist.

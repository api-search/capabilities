---
categories: []
consumed_apis:
- telstra
description: A capability with /metrics (Prometheus) + /health endpoints + Resilience Metrics wired in as platform-engineering acceptance criteria.
layout: capability
naftiko_layer: proposed
naftiko_partner: Ranjaka De Mel
name: Telstra Platform Ops Observability Capability
operations: []
personas: []
provider_name: Telstra
provider_slug: telstra
search_terms:
- capability
- with
- metrics
- prometheus
- health
slug: platform-ops-observability-capability
source_filename: platform-ops-observability-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Telstra Platform Ops Observability Capability
    description: A capability with /metrics (Prometheus) + /health endpoints + Resilience Metrics wired in as platform-engineering acceptance criteria.
    tags:
    - Telstra
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: telstra-env
    description: Telstra credentials.
    keys:
      TELSTRA_API_KEY: TELSTRA_API_KEY
  capability:
    consumes:
    - namespace: telstra
      type: http
      baseUri: https://api.telstra.com
      authentication:
        type: bearer
        token: '{{TELSTRA_API_KEY}}'
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
      namespace: platform-ops-observability-capability-rest
      description: REST API for Telstra Platform Ops Observability Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: telstra.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: platform-ops-observability-capability-mcp
      description: MCP server exposing Telstra Platform Ops Observability Capability for AI agents.
      tools:
      - name: example
        description: A capability with /metrics (Prometheus) + /health endpoints + Resilience Metrics wired in as platform-engineering acceptance criteria.
        hints:
          readOnly: true
        call: telstra.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: platform-ops-observability-capability-skills
      description: Agent Skill bundle for Telstra Platform Ops Observability Capability.
      skills:
      - name: platform-ops-observability-capability
        description: A capability with /metrics (Prometheus) + /health endpoints + Resilience Metrics wired in as platform-engineering acceptance criteria.
        location: file:///opt/naftiko/skills/platform-ops-observability-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability with /metrics (Prometheus) + /health endpoints + Resilience Metrics wired in as platform-engineering acceptance criteria.
          from:
            sourceNamespace: platform-ops-observability-capability-mcp
            action: example
---

A capability with /metrics (Prometheus) + /health endpoints + Resilience Metrics wired in as platform-engineering acceptance criteria. Platform engineers reject tools that don't expose ops surfaces; lead with what passes that test.

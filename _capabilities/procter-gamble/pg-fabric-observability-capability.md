---
categories: []
consumed_apis:
- procter-gamble
description: A capability wired into Cross-Engine Observability Dashboards + Federation Across Fabrics, used to argue the fabric-wide visibility story.
layout: capability
naftiko_layer: proposed
naftiko_partner: Norbert Anthony
name: Procter & Gamble Pg Fabric Observability Capability
operations: []
personas: []
provider_name: Procter & Gamble
provider_slug: procter-gamble
search_terms:
- capability
- wired
- into
- cross
- engine
slug: pg-fabric-observability-capability
source_filename: pg-fabric-observability-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Procter & Gamble Pg Fabric Observability Capability
    description: A capability wired into Cross-Engine Observability Dashboards + Federation Across Fabrics, used to argue the fabric-wide visibility story.
    tags:
    - Procter & Gamble
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: procter-gamble-env
    description: Procter & Gamble credentials.
    keys:
      PROCTER_GAMBLE_API_KEY: PROCTER_GAMBLE_API_KEY
  capability:
    consumes:
    - namespace: procter-gamble
      type: http
      baseUri: https://api.procter-gamble.com
      authentication:
        type: bearer
        token: '{{PROCTER_GAMBLE_API_KEY}}'
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
      namespace: pg-fabric-observability-capability-rest
      description: REST API for Procter & Gamble Pg Fabric Observability Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: procter-gamble.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: pg-fabric-observability-capability-mcp
      description: MCP server exposing Procter & Gamble Pg Fabric Observability Capability for AI agents.
      tools:
      - name: example
        description: A capability wired into Cross-Engine Observability Dashboards + Federation Across Fabrics, used to argue the fabric-wide visibility story.
        hints:
          readOnly: true
        call: procter-gamble.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: pg-fabric-observability-capability-skills
      description: Agent Skill bundle for Procter & Gamble Pg Fabric Observability Capability.
      skills:
      - name: pg-fabric-observability-capability
        description: A capability wired into Cross-Engine Observability Dashboards + Federation Across Fabrics, used to argue the fabric-wide visibility story.
        location: file:///opt/naftiko/skills/pg-fabric-observability-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability wired into Cross-Engine Observability Dashboards + Federation Across Fabrics, used to argue the fabric-wide visibility story.
          from:
            sourceNamespace: pg-fabric-observability-capability-mcp
            action: example
---

A capability wired into Cross-Engine Observability Dashboards + Federation Across Fabrics, used to argue the fabric-wide visibility story. Enterprise-integration leaders care about fabric-wide visibility; default Naftiko pitch underweights this.

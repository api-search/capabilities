---
categories: []
consumed_apis:
- telstra
description: A capability over Telstra's public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Ranjaka De Mel
name: Telstra Public Messaging Api Prometheus Instrumented Capability
operations: []
personas: []
provider_name: Telstra
provider_slug: telstra
search_terms:
- capability
- over
- telstra
- public
- messaging
slug: public-messaging-api-prometheus-instrumented-capability
source_filename: public-messaging-api-prometheus-instrumented-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Telstra Public Messaging Api Prometheus Instrumented Capability
    description: A capability over Telstra's public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics.
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
      namespace: public-messaging-api-prometheus-instrumented-capability-rest
      description: REST API for Telstra Public Messaging Api Prometheus Instrumented Capability.
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
      namespace: public-messaging-api-prometheus-instrumented-capability-mcp
      description: MCP server exposing Telstra Public Messaging Api Prometheus Instrumented Capability for AI agents.
      tools:
      - name: example
        description: A capability over Telstra's public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics.
        hints:
          readOnly: true
        call: telstra.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: public-messaging-api-prometheus-instrumented-capability-skills
      description: Agent Skill bundle for Telstra Public Messaging Api Prometheus Instrumented Capability.
      skills:
      - name: public-messaging-api-prometheus-instrumented-capability
        description: A capability over Telstra's public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics.
        location: file:///opt/naftiko/skills/public-messaging-api-prometheus-instrumented-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Telstra's public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics.
          from:
            sourceNamespace: public-messaging-api-prometheus-instrumented-capability-mcp
            action: example
---

A capability over Telstra's public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics. Platform engineers reject tools without ops surfaces; lead with what passes that test on a Telstra-public API.

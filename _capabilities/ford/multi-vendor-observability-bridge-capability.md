---
categories: []
consumed_apis:
- ford
description: A capability that fans out to Ford's existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Multi Vendor Observability Bridge Capability
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- fans
- ford
- existing
slug: multi-vendor-observability-bridge-capability
source_filename: multi-vendor-observability-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Multi Vendor Observability Bridge Capability
    description: A capability that fans out to Ford's existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
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
      namespace: multi-vendor-observability-bridge-capability-rest
      description: REST API for Ford Multi Vendor Observability Bridge Capability.
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
      namespace: multi-vendor-observability-bridge-capability-mcp
      description: MCP server exposing Ford Multi Vendor Observability Bridge Capability for AI agents.
      tools:
      - name: example
        description: A capability that fans out to Ford's existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: multi-vendor-observability-bridge-capability-skills
      description: Agent Skill bundle for Ford Multi Vendor Observability Bridge Capability.
      skills:
      - name: multi-vendor-observability-bridge-capability
        description: A capability that fans out to Ford's existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
        location: file:///opt/naftiko/skills/multi-vendor-observability-bridge-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that fans out to Ford's existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
          from:
            sourceNamespace: multi-vendor-observability-bridge-capability-mcp
            action: example
---

A capability that fans out to Ford's existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged. This answers his ranked priority #4 — observability across the full stack he actually runs, not a single-vendor pitch.

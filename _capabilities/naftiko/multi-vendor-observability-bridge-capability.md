---
categories: []
consumed_apis: []
description: A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Multi Vendor Observability Bridge Capability
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- that
- fans
- existing
- observability
slug: multi-vendor-observability-bridge-capability
source_filename: multi-vendor-observability-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Multi Vendor Observability Bridge Capability
  description: A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
  tags:
  Naftiko
  created:'2026-05-01'
  modified:'2026-05-01'
  binds:
  namespace: naftiko-env
  description: Naftiko credentials.
  keys:
  NAFTIKO_API_KEY: NAFTIKO_API_KEY
  capability:
  consumes:
  namespace: naftiko
  type: http
  baseUri: https://api.naftiko.com
  authentication:
  type: bearer
  token:'{{NAFTIKO_API_KEY}}'
  resources:
  name: example
  path: /example
  operations:
  name: example-op
  method: GET
  exposes:
  type: rest
  address: 0.0.0.0
  port: 8080
  namespace: multi-vendor-observability-bridge-capability-rest
  description: REST API for Multi Vendor Observability Bridge Capability.
  resources:
  name: example
  path: /example
  operations:
  method: GET
  name: example-op
  call: naftiko.example-op
  type: mcp
  address: 0.0.0.0
  port: 3010
  namespace: multi-vendor-observability-bridge-capability-mcp
  description: MCP server exposing Multi Vendor Observability Bridge Capability for AI agents.
  tools:
  name: example
  description: A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: multi-vendor-observability-bridge-capability-skills
  description: Agent Skill bundle for Multi Vendor Observability Bridge Capability.
  skills:
  name: multi-vendor-observability-bridge-capability
  description: A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
  location: file:///opt/naftiko/skills/multi-vendor-observability-bridge-capability
  allowed-tools: example
  tools:
  name: example
  description: A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.
  from:
  sourceNamespace: multi-vendor-observability-bridge-capability-mcp
  action: example
---

A capability that fans out to existing observability stack (New Relic + Datadog + Dynatrace + Google Cloud Logging) plus OpenTelemetry traces and returns a unified agent-driven-API-call view, sized for the Gartner-hasn't-caught-up gap John flagged.

---
categories: []
consumed_apis: []
description: A capability over public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Ranjaka De Mel
name: Public Messaging Api Prometheus Instrumented Capability
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- over
- public
- messaging
- developer
slug: public-messaging-api-prometheus-instrumented-capability
source_filename: public-messaging-api-prometheus-instrumented-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Public Messaging Api Prometheus Instrumented Capability
  description: A capability over public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics.
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
  namespace: public-messaging-api-prometheus-instrumented-capability-rest
  description: REST API for Public Messaging Api Prometheus Instrumented Capability.
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
  namespace: public-messaging-api-prometheus-instrumented-capability-mcp
  description: MCP server exposing Public Messaging Api Prometheus Instrumented Capability for AI agents.
  tools:
  name: example
  description: A capability over public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics.
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: public-messaging-api-prometheus-instrumented-capability-skills
  description: Agent Skill bundle for Public Messaging Api Prometheus Instrumented Capability.
  skills:
  name: public-messaging-api-prometheus-instrumented-capability
  description: A capability over public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics.
  location: file:///opt/naftiko/skills/public-messaging-api-prometheus-instrumented-capability
  allowed-tools: example
  tools:
  name: example
  description: A capability over public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics.
  from:
  sourceNamespace: public-messaging-api-prometheus-instrumented-capability-mcp
  action: example
---

A capability over public Messaging / SMS developer API instrumented with Prometheus /metrics + /health endpoints + Resilience Metrics.

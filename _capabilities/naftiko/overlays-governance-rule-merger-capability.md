---
categories: []
consumed_apis: []
description: A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a -fronted upstream.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Budhaditya (Budha) Bhattacharya
name: Overlays Governance Rule Merger Capability
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- that
- consumes
- base
- openapi
slug: overlays-governance-rule-merger-capability
source_filename: overlays-governance-rule-merger-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Overlays Governance Rule Merger Capability
  description: A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a -fronted upstream.
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
  namespace: overlays-governance-rule-merger-capability-rest
  description: REST API for Overlays Governance Rule Merger Capability.
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
  namespace: overlays-governance-rule-merger-capability-mcp
  description: MCP server exposing Overlays Governance Rule Merger Capability for AI agents.
  tools:
  name: example
  description: A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a -fronted upstream.
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: overlays-governance-rule-merger-capability-skills
  description: Agent Skill bundle for Overlays Governance Rule Merger Capability.
  skills:
  name: overlays-governance-rule-merger-capability
  description: A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a -fronted upstream.
  location: file:///opt/naftiko/skills/overlays-governance-rule-merger-capability
  allowed-tools: example
  tools:
  name: example
  description: A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a -fronted upstream.
  from:
  sourceNamespace: overlays-governance-rule-merger-capability-mcp
  action: example
---

A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a -fronted upstream.

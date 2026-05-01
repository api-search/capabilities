---
categories: []
consumed_apis: []
description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
layout: capability
naftiko_layer: proposed
naftiko_partner: Patrick Kelly
name: Mcp First Context Engineering Capability
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- implementing
- first
- context
- engineering
slug: mcp-first-context-engineering-capability
source_filename: mcp-first-context-engineering-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Mcp First Context Engineering Capability
  description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
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
  namespace: mcp-first-context-engineering-capability-rest
  description: REST API for Mcp First Context Engineering Capability.
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
  namespace: mcp-first-context-engineering-capability-mcp
  description: MCP server exposing Mcp First Context Engineering Capability for AI agents.
  tools:
  name: example
  description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: mcp-first-context-engineering-capability-skills
  description: Agent Skill bundle for Mcp First Context Engineering Capability.
  skills:
  name: mcp-first-context-engineering-capability
  description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
  location: file:///opt/naftiko/skills/mcp-first-context-engineering-capability
  allowed-tools: example
  tools:
  name: example
  description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
  from:
  sourceNamespace: mcp-first-context-engineering-capability-mcp
  action: example
---

A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.

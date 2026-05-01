---
categories: []
consumed_apis: []
description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
layout: capability
naftiko_layer: proposed
naftiko_partner: Cedric MONIER
name: Api First As Governance Surface Capability
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- annotated
- against
- specification
- governance
slug: api-first-as-governance-surface-capability
source_filename: api-first-as-governance-surface-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Api First As Governance Surface Capability
  description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
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
  namespace: api-first-as-governance-surface-capability-rest
  description: REST API for Api First As Governance Surface Capability.
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
  namespace: api-first-as-governance-surface-capability-mcp
  description: MCP server exposing Api First As Governance Surface Capability for AI agents.
  tools:
  name: example
  description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: api-first-as-governance-surface-capability-skills
  description: Agent Skill bundle for Api First As Governance Surface Capability.
  skills:
  name: api-first-as-governance-surface-capability
  description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
  location: file:///opt/naftiko/skills/api-first-as-governance-surface-capability
  allowed-tools: example
  tools:
  name: example
  description: A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.
  from:
  sourceNamespace: api-first-as-governance-surface-capability-mcp
  action: example
---

A capability annotated against the SDI "specification as governance surface" framing as the API-First Program reading.

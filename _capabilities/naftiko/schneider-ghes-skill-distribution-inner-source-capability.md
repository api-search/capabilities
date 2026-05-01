---
categories: []
consumed_apis: []
description: A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Manu PK
name: Schneider Ghes Skill Distribution Inner Source Capability
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- that
- mirrors
- enterprise
- agent
slug: schneider-ghes-skill-distribution-inner-source-capability
source_filename: schneider-ghes-skill-distribution-inner-source-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Schneider Ghes Skill Distribution Inner Source Capability
  description: A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken.
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
  namespace: schneider-ghes-skill-distribution-inner-source-capability-rest
  description: REST API for Schneider Ghes Skill Distribution Inner Source Capability.
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
  namespace: schneider-ghes-skill-distribution-inner-source-capability-mcp
  description: MCP server exposing Schneider Ghes Skill Distribution Inner Source Capability for AI agents.
  tools:
  name: example
  description: A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken.
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: schneider-ghes-skill-distribution-inner-source-capability-skills
  description: Agent Skill bundle for Schneider Ghes Skill Distribution Inner Source Capability.
  skills:
  name: schneider-ghes-skill-distribution-inner-source-capability
  description: A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken.
  location: file:///opt/naftiko/skills/schneider-ghes-skill-distribution-inner-source-capability
  allowed-tools: example
  tools:
  name: example
  description: A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken.
  from:
  sourceNamespace: schneider-ghes-skill-distribution-inner-source-capability-mcp
  action: example
---

A capability that mirrors enterprise agent skills as inner-source repos with allow-list + manifest semantics, filling the self-hosted GitHub Enterprise Server skill-distribution gap Manu flagged as broken.

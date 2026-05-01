---
categories: []
consumed_apis: []
description: A capability whose `exposes` block leads with governance rules + tags on Consumes/Exposes, designed as the "trust posture" artifact for re-engagement.
layout: capability
naftiko_layer: proposed
naftiko_partner: Ulrich Trinkaus
name: Trust Posture Governance Capability
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- whose
- exposes
- block
- leads
slug: trust-posture-governance-capability
source_filename: trust-posture-governance-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Trust Posture Governance Capability
  description: A capability whose `exposes` block leads with governance rules + tags on Consumes/Exposes, designed as the "trust posture" artifact for re-engagement.
  tags:
  Naftiko
  created:'2026-05-01'
  modified:'2026-05-01'
  binds:
  namespace: naftiko-env
  description: Naftiko credentials.
  k:
  NAFTIKO_API_K: NAFTIKO_API_K
  capability:
  consumes:
  namespace: naftiko
  type: http
  baseUri: https://api.naftiko.com
  authentication:
  type: bearer
  token:'{{NAFTIKO_API_K}}'
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
  namespace: trust-posture-governance-capability-rest
  description: REST API for Trust Posture Governance Capability.
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
  namespace: trust-posture-governance-capability-mcp
  description: MCP server exposing Trust Posture Governance Capability for AI agents.
  tools:
  name: example
  description: A capability whose `exposes` block leads with governance rules + tags on Consumes/Exposes, designed as the "trust posture" artifact for re-engagement.
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: trust-posture-governance-capability-skills
  description: Agent Skill bundle for Trust Posture Governance Capability.
  skills:
  name: trust-posture-governance-capability
  description: A capability whose `exposes` block leads with governance rules + tags on Consumes/Exposes, designed as the "trust posture" artifact for re-engagement.
  location: file:///opt/naftiko/skills/trust-posture-governance-capability
  allowed-tools: example
  tools:
  name: example
  description: A capability whose `exposes` block leads with governance rules + tags on Consumes/Exposes, designed as the "trust posture" artifact for re-engagement.
  from:
  sourceNamespace: trust-posture-governance-capability-mcp
  action: example
---

A capability whose `exposes` block leads with governance rules + tags on Consumes/Exposes, designed as the "trust posture" artifact for re-engagement.

---
categories: []
consumed_apis: []
description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Mark McAllister
name: Banking Governance Capability
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- built
- specifically
- show
- banking
slug: banking-governance-capability
source_filename: banking-governance-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Banking Governance Capability
  description:'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
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
  namespace: banking-governance-capability-rest
  description: REST API for Banking Governance Capability.
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
  namespace: banking-governance-capability-mcp
  description: MCP server exposing Banking Governance Capability for AI agents.
  tools:
  name: example
  description:'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: banking-governance-capability-skills
  description: Agent Skill bundle for Banking Governance Capability.
  skills:
  name: banking-governance-capability
  description:'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
  location: file:///opt/naftiko/skills/banking-governance-capability
  allowed-tools: example
  tools:
  name: example
  description:'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
  from:
  sourceNamespace: banking-governance-capability-mcp
  action: example
---

A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.

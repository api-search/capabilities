---
categories: []
consumed_apis: []
description: A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style).
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Ulrich Trinkaus
name: Sap S4hana Financial Close Governed Capability
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- over
- 4hana
- financial
- close
slug: sap-s4hana-financial-close-governed-capability
source_filename: sap-s4hana-financial-close-governed-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Sap S4hana Financial Close Governed Capability
  description: A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style).
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
  namespace: sap-s4hana-financial-close-governed-capability-rest
  description: REST API for Sap S4hana Financial Close Governed Capability.
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
  namespace: sap-s4hana-financial-close-governed-capability-mcp
  description: MCP server exposing Sap S4hana Financial Close Governed Capability for AI agents.
  tools:
  name: example
  description: A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style).
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: sap-s4hana-financial-close-governed-capability-skills
  description: Agent Skill bundle for Sap S4hana Financial Close Governed Capability.
  skills:
  name: sap-s4hana-financial-close-governed-capability
  description: A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style).
  location: file:///opt/naftiko/skills/sap-s4hana-financial-close-governed-capability
  allowed-tools: example
  tools:
  name: example
  description: A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style).
  from:
  sourceNamespace: sap-s4hana-financial-close-governed-capability-mcp
  action: example
---

A capability over SAP S/4HANA financial close postings, exposing read-only MCP tools with continuous-compliance reporting (NIST/SOC2/PCI-style).

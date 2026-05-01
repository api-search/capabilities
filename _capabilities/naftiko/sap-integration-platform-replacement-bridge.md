---
categories: []
consumed_apis: []
description: A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Norbert Anthony
name: Sap Integration Platform Replacement Bridge
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- over
- integration
- surface
- that
slug: sap-integration-platform-replacement-bridge
source_filename: sap-integration-platform-replacement-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Sap Integration Platform Replacement Bridge
  description: A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration.
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
  namespace: sap-integration-platform-replacement-bridge-rest
  description: REST API for Sap Integration Platform Replacement Bridge.
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
  namespace: sap-integration-platform-replacement-bridge-mcp
  description: MCP server exposing Sap Integration Platform Replacement Bridge for AI agents.
  tools:
  name: example
  description: A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration.
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: sap-integration-platform-replacement-bridge-skills
  description: Agent Skill bundle for Sap Integration Platform Replacement Bridge.
  skills:
  name: sap-integration-platform-replacement-bridge
  description: A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration.
  location: file:///opt/naftiko/skills/sap-integration-platform-replacement-bridge
  allowed-tools: example
  tools:
  name: example
  description: A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration.
  from:
  sourceNamespace: sap-integration-platform-replacement-bridge-mcp
  action: example
---

A capability over the SAP integration surface that exposes shaped MCP tools the next-gen replacement can call alongside legacy Boomi flows during the migration.

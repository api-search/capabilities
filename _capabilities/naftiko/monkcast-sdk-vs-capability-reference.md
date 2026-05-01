---
categories: []
consumed_apis: []
description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
layout: capability
naftiko_layer: proposed
naftiko_partner: Kate Holterhoff
name: Monkcast Sdk Vs Capability Reference
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- side
- reference
- capability
- that
- pairs
slug: monkcast-sdk-vs-capability-reference
source_filename: monkcast-sdk-vs-capability-reference.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Monkcast Sdk Vs Capability Reference
  description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
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
  namespace: monkcast-sdk-vs-capability-reference-rest
  description: REST API for Monkcast Sdk Vs Capability Reference.
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
  namespace: monkcast-sdk-vs-capability-reference-mcp
  description: MCP server exposing Monkcast Sdk Vs Capability Reference for AI agents.
  tools:
  name: example
  description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: monkcast-sdk-vs-capability-reference-skills
  description: Agent Skill bundle for Monkcast Sdk Vs Capability Reference.
  skills:
  name: monkcast-sdk-vs-capability-reference
  description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
  location: file:///opt/naftiko/skills/monkcast-sdk-vs-capability-reference
  allowed-tools: example
  tools:
  name: example
  description: A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."
  from:
  sourceNamespace: monkcast-sdk-vs-capability-reference-mcp
  action: example
---

A side-by-side reference capability that pairs a generated SDK with a Naftiko-exposed capability over the same upstream API, illustrating "Capabilities Are the New Abstraction Layer."

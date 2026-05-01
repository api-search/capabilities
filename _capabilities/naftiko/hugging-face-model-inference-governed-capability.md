---
categories: []
consumed_apis: []
description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Mamta Suri
name: Hugging Face Model Inference Governed Capability
operations: []
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- capability
- over
- hugging
- face
- inference
slug: hugging-face-model-inference-governed-capability
source_filename: hugging-face-model-inference-governed-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
  title: Hugging Face Model Inference Governed Capability
  description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
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
  namespace: hugging-face-model-inference-governed-capability-rest
  description: REST API for Hugging Face Model Inference Governed Capability.
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
  namespace: hugging-face-model-inference-governed-capability-mcp
  description: MCP server exposing Hugging Face Model Inference Governed Capability for AI agents.
  tools:
  name: example
  description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
  hints:
  readOnly: true
  call: naftiko.example-op
  type: skill
  address: 0.0.0.0
  port: 3011
  namespace: hugging-face-model-inference-governed-capability-skills
  description: Agent Skill bundle for Hugging Face Model Inference Governed Capability.
  skills:
  name: hugging-face-model-inference-governed-capability
  description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
  location: file:///opt/naftiko/skills/hugging-face-model-inference-governed-capability
  allowed-tools: example
  tools:
  name: example
  description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
  from:
  sourceNamespace: hugging-face-model-inference-governed-capability-mcp
  action: example
---

A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.

---
categories: []
consumed_apis:
- walmart-global-tech
description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Mamta Suri
name: Walmart Global Tech Walmart Hugging Face Model Inference Governed Capability
operations: []
personas: []
provider_name: Walmart Global Tech
provider_slug: walmart-global-tech
search_terms:
- capability
- over
- hugging
- face
- inference
slug: walmart-hugging-face-model-inference-governed-capability
source_filename: walmart-hugging-face-model-inference-governed-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Walmart Global Tech Walmart Hugging Face Model Inference Governed Capability
    description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
    tags:
    - Walmart Global Tech
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: walmart-global-tech-env
    description: Walmart Global Tech credentials.
    keys:
      WALMART_GLOBAL_TECH_API_KEY: WALMART_GLOBAL_TECH_API_KEY
  capability:
    consumes:
    - namespace: walmart-global-tech
      type: http
      baseUri: https://api.walmart-global-tech.com
      authentication:
        type: bearer
        token: '{{WALMART_GLOBAL_TECH_API_KEY}}'
      resources:
      - name: example
        path: /example
        operations:
        - name: example-op
          method: GET
    exposes:
    - type: rest
      address: 0.0.0.0
      port: 8080
      namespace: walmart-hugging-face-model-inference-governed-capability-rest
      description: REST API for Walmart Global Tech Walmart Hugging Face Model Inference Governed Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: walmart-global-tech.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: walmart-hugging-face-model-inference-governed-capability-mcp
      description: MCP server exposing Walmart Global Tech Walmart Hugging Face Model Inference Governed Capability for AI agents.
      tools:
      - name: example
        description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
        hints:
          readOnly: true
        call: walmart-global-tech.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: walmart-hugging-face-model-inference-governed-capability-skills
      description: Agent Skill bundle for Walmart Global Tech Walmart Hugging Face Model Inference Governed Capability.
      skills:
      - name: walmart-hugging-face-model-inference-governed-capability
        description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
        location: file:///opt/naftiko/skills/walmart-hugging-face-model-inference-governed-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
          from:
            sourceNamespace: walmart-hugging-face-model-inference-governed-capability-mcp
            action: example
---

A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic. A specific HF + Datadog topic gives her something concrete to say yes to instead of a generic podcast slot.

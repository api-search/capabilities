---
categories: []
consumed_apis:
- walmart-global-tech
description: A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story.
layout: capability
naftiko_layer: proposed
naftiko_partner: Mamta Suri
name: Walmart Global Tech Walmart Ml Output Shaping Capability
operations: []
personas: []
provider_name: Walmart Global Tech
provider_slug: walmart-global-tech
search_terms:
- capability
- featuring
- composition
- typed
- outputparameters
slug: walmart-ml-output-shaping-capability
source_filename: walmart-ml-output-shaping-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Walmart Global Tech Walmart Ml Output Shaping Capability
    description: A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story.
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
      namespace: walmart-ml-output-shaping-capability-rest
      description: REST API for Walmart Global Tech Walmart Ml Output Shaping Capability.
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
      namespace: walmart-ml-output-shaping-capability-mcp
      description: MCP server exposing Walmart Global Tech Walmart Ml Output Shaping Capability for AI agents.
      tools:
      - name: example
        description: A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story.
        hints:
          readOnly: true
        call: walmart-global-tech.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: walmart-ml-output-shaping-capability-skills
      description: Agent Skill bundle for Walmart Global Tech Walmart Ml Output Shaping Capability.
      skills:
      - name: walmart-ml-output-shaping-capability
        description: A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story.
        location: file:///opt/naftiko/skills/walmart-ml-output-shaping-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story.
          from:
            sourceNamespace: walmart-ml-output-shaping-capability-mcp
            action: example
---

A capability featuring Capability Composition + typed outputParameters + JSONPath as the ML pipeline context-shaping story. Her role maps directly to context-shaping for ML pipelines.

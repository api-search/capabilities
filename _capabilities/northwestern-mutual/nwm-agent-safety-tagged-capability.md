---
categories: []
consumed_apis:
- northwestern-mutual
description: Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data.
layout: capability
naftiko_layer: proposed
naftiko_partner: Supreet Nagi
name: Northwestern Mutual Nwm Agent Safety Tagged Capability
operations: []
personas: []
provider_name: Northwestern Mutual
provider_slug: northwestern-mutual
search_terms:
- insurance
- adjacent
- capability
- showing
- tags
slug: nwm-agent-safety-tagged-capability
source_filename: nwm-agent-safety-tagged-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Northwestern Mutual Nwm Agent Safety Tagged Capability
    description: Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data.
    tags:
    - Northwestern Mutual
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: northwestern-mutual-env
    description: Northwestern Mutual credentials.
    keys:
      NORTHWESTERN_MUTUAL_API_KEY: NORTHWESTERN_MUTUAL_API_KEY
  capability:
    consumes:
    - namespace: northwestern-mutual
      type: http
      baseUri: https://api.northwestern-mutual.com
      authentication:
        type: bearer
        token: '{{NORTHWESTERN_MUTUAL_API_KEY}}'
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
      namespace: nwm-agent-safety-tagged-capability-rest
      description: REST API for Northwestern Mutual Nwm Agent Safety Tagged Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: northwestern-mutual.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: nwm-agent-safety-tagged-capability-mcp
      description: MCP server exposing Northwestern Mutual Nwm Agent Safety Tagged Capability for AI agents.
      tools:
      - name: example
        description: Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data.
        hints:
          readOnly: true
        call: northwestern-mutual.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: nwm-agent-safety-tagged-capability-skills
      description: Agent Skill bundle for Northwestern Mutual Nwm Agent Safety Tagged Capability.
      skills:
      - name: nwm-agent-safety-tagged-capability
        description: Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data.
        location: file:///opt/naftiko/skills/nwm-agent-safety-tagged-capability
        allowed-tools: example
        tools:
        - name: example
          description: Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data.
          from:
            sourceNamespace: nwm-agent-safety-tagged-capability-mcp
            action: example
---

Insurance-adjacent capability showing tags-on-ExposedOperation (agent safety policy, effect classification) for AI-safe operations on financial data. Senior Director of SE at NW Mutual; agent-safety tagging is the integration concern that lands internally.

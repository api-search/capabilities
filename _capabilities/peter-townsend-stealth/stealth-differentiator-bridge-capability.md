---
categories: []
consumed_apis:
- peter-townsend-stealth
description: A capability that explicitly sits between the stealth product's differentiator and one upstream API, demonstrating Naftiko-handles-integration-while-they-focus-on-IP.
layout: capability
naftiko_layer: proposed
naftiko_partner: Peter Townsend
name: Peter Townsend Stealth Stealth Differentiator Bridge Capability
operations: []
personas: []
provider_name: Peter Townsend Stealth
provider_slug: peter-townsend-stealth
search_terms:
- capability
- that
- explicitly
- sits
- between
slug: stealth-differentiator-bridge-capability
source_filename: stealth-differentiator-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Peter Townsend Stealth Stealth Differentiator Bridge Capability
    description: A capability that explicitly sits between the stealth product's differentiator and one upstream API, demonstrating Naftiko-handles-integration-while-they-focus-on-IP.
    tags:
    - Peter Townsend Stealth
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: peter-townsend-stealth-env
    description: Peter Townsend Stealth credentials.
    keys:
      PETER_TOWNSEND_STEALTH_API_KEY: PETER_TOWNSEND_STEALTH_API_KEY
  capability:
    consumes:
    - namespace: peter-townsend-stealth
      type: http
      baseUri: https://api.peter-townsend-stealth.com
      authentication:
        type: bearer
        token: '{{PETER_TOWNSEND_STEALTH_API_KEY}}'
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
      namespace: stealth-differentiator-bridge-capability-rest
      description: REST API for Peter Townsend Stealth Stealth Differentiator Bridge Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: peter-townsend-stealth.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: stealth-differentiator-bridge-capability-mcp
      description: MCP server exposing Peter Townsend Stealth Stealth Differentiator Bridge Capability for AI agents.
      tools:
      - name: example
        description: A capability that explicitly sits between the stealth product's differentiator and one upstream API, demonstrating Naftiko-handles-integration-while-they-focus-on-IP.
        hints:
          readOnly: true
        call: peter-townsend-stealth.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: stealth-differentiator-bridge-capability-skills
      description: Agent Skill bundle for Peter Townsend Stealth Stealth Differentiator Bridge Capability.
      skills:
      - name: stealth-differentiator-bridge-capability
        description: A capability that explicitly sits between the stealth product's differentiator and one upstream API, demonstrating Naftiko-handles-integration-while-they-focus-on-IP.
        location: file:///opt/naftiko/skills/stealth-differentiator-bridge-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that explicitly sits between the stealth product's differentiator and one upstream API, demonstrating Naftiko-handles-integration-while-they-focus-on-IP.
          from:
            sourceNamespace: stealth-differentiator-bridge-capability-mcp
            action: example
---

A capability that explicitly sits between the stealth product's differentiator and one upstream API, demonstrating Naftiko-handles-integration-while-they-focus-on-IP. His next-step is a proposal on how capabilities help them build — this artifact is the proposal.

---
categories: []
consumed_apis:
- peter-townsend-stealth
description: A capability that fronts the stealth product's free-tier API surface for agents, applies credit-limit + rate-throttle policies, and returns a typed signal object back about what the agent tried.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Peter Townsend
name: Peter Townsend Stealth Stealth Agent Give To Get Credit Throttled Capability
operations: []
personas: []
provider_name: Peter Townsend Stealth
provider_slug: peter-townsend-stealth
search_terms:
- capability
- that
- fronts
- stealth
- product
slug: stealth-agent-give-to-get-credit-throttled-capability
source_filename: stealth-agent-give-to-get-credit-throttled-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Peter Townsend Stealth Stealth Agent Give To Get Credit Throttled Capability
    description: A capability that fronts the stealth product's free-tier API surface for agents, applies credit-limit + rate-throttle policies, and returns a typed signal object back about what the agent tried.
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
      namespace: stealth-agent-give-to-get-credit-throttled-capability-rest
      description: REST API for Peter Townsend Stealth Stealth Agent Give To Get Credit Throttled Capability.
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
      namespace: stealth-agent-give-to-get-credit-throttled-capability-mcp
      description: MCP server exposing Peter Townsend Stealth Stealth Agent Give To Get Credit Throttled Capability for AI agents.
      tools:
      - name: example
        description: A capability that fronts the stealth product's free-tier API surface for agents, applies credit-limit + rate-throttle policies, and returns a typed signal object back about what the agent tried.
        hints:
          readOnly: true
        call: peter-townsend-stealth.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: stealth-agent-give-to-get-credit-throttled-capability-skills
      description: Agent Skill bundle for Peter Townsend Stealth Stealth Agent Give To Get Credit Throttled Capability.
      skills:
      - name: stealth-agent-give-to-get-credit-throttled-capability
        description: A capability that fronts the stealth product's free-tier API surface for agents, applies credit-limit + rate-throttle policies, and returns a typed signal object back about what the agent tried.
        location: file:///opt/naftiko/skills/stealth-agent-give-to-get-credit-throttled-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that fronts the stealth product's free-tier API surface for agents, applies credit-limit + rate-throttle policies, and returns a typed signal object back about what the agent tried.
          from:
            sourceNamespace: stealth-agent-give-to-get-credit-throttled-capability-mcp
            action: example
---

A capability that fronts the stealth product's free-tier API surface for agents, applies credit-limit + rate-throttle policies, and returns a typed signal object back about what the agent tried. His own thesis is the agent-driven give-to-get model; this turns it into runnable infrastructure on day one.

---
categories: []
consumed_apis:
- schneider-electric
description: A reference capability mirroring Playwright MCP — Schneider's first deployed server — as the canonical "first MCP server to onboard" template for any enterprise standing up the registry pattern.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Manu PK
name: Schneider Electric Schneider Playwright Mcp No Auth Onboarding Template
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- reference
- capability
- mirroring
- playwright
- schneider
slug: schneider-playwright-mcp-no-auth-onboarding-template
source_filename: schneider-playwright-mcp-no-auth-onboarding-template.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider Playwright Mcp No Auth Onboarding Template
    description: A reference capability mirroring Playwright MCP — Schneider's first deployed server — as the canonical "first MCP server to onboard" template for any enterprise standing up the registry pattern.
    tags:
    - Schneider Electric
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: schneider-electric-env
    description: Schneider Electric credentials.
    keys:
      SCHNEIDER_ELECTRIC_API_KEY: SCHNEIDER_ELECTRIC_API_KEY
  capability:
    consumes:
    - namespace: schneider-electric
      type: http
      baseUri: https://api.schneider-electric.com
      authentication:
        type: bearer
        token: '{{SCHNEIDER_ELECTRIC_API_KEY}}'
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
      namespace: schneider-playwright-mcp-no-auth-onboarding-template-rest
      description: REST API for Schneider Electric Schneider Playwright Mcp No Auth Onboarding Template.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: schneider-electric.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: schneider-playwright-mcp-no-auth-onboarding-template-mcp
      description: MCP server exposing Schneider Electric Schneider Playwright Mcp No Auth Onboarding Template for AI agents.
      tools:
      - name: example
        description: A reference capability mirroring Playwright MCP — Schneider's first deployed server — as the canonical "first MCP server to onboard" template for any enterprise standing up the registry pattern.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-playwright-mcp-no-auth-onboarding-template-skills
      description: Agent Skill bundle for Schneider Electric Schneider Playwright Mcp No Auth Onboarding Template.
      skills:
      - name: schneider-playwright-mcp-no-auth-onboarding-template
        description: A reference capability mirroring Playwright MCP — Schneider's first deployed server — as the canonical "first MCP server to onboard" template for any enterprise standing up the registry pattern.
        location: file:///opt/naftiko/skills/schneider-playwright-mcp-no-auth-onboarding-template
        allowed-tools: example
        tools:
        - name: example
          description: A reference capability mirroring Playwright MCP — Schneider's first deployed server — as the canonical "first MCP server to onboard" template for any enterprise standing up the registry pattern.
          from:
            sourceNamespace: schneider-playwright-mcp-no-auth-onboarding-template-mcp
            action: example
---

A reference capability mirroring Playwright MCP — Schneider's first deployed server — as the canonical "first MCP server to onboard" template for any enterprise standing up the registry pattern. Playwright was his proof-of-concept choice precisely because it had no auth — codifying that "start with the simplest, no-identity server" pattern as a Naftiko reference makes his playbook reusable by any enterprise.

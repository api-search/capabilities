---
categories: []
consumed_apis:
- vonage
description: 'A capability tied to Guide-Use-Cases #1 (AI integration) as the podcast pitch hook for re-engagement.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Vonage
name: Vonage Podcast Ai Integration Capability
operations: []
personas: []
provider_name: Vonage
provider_slug: vonage
search_terms:
- capability
- tied
- guide
- cases
- integration
slug: podcast-ai-integration-capability
source_filename: podcast-ai-integration-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vonage Podcast Ai Integration Capability
    description: 'A capability tied to Guide-Use-Cases #1 (AI integration) as the podcast pitch hook for re-engagement.'
    tags:
    - Vonage
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: vonage-env
    description: Vonage credentials.
    keys:
      VONAGE_API_KEY: VONAGE_API_KEY
  capability:
    consumes:
    - namespace: vonage
      type: http
      baseUri: https://api.vonage.com
      authentication:
        type: bearer
        token: '{{VONAGE_API_KEY}}'
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
      namespace: podcast-ai-integration-capability-rest
      description: REST API for Vonage Podcast Ai Integration Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: vonage.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: podcast-ai-integration-capability-mcp
      description: MCP server exposing Vonage Podcast Ai Integration Capability for AI agents.
      tools:
      - name: example
        description: 'A capability tied to Guide-Use-Cases #1 (AI integration) as the podcast pitch hook for re-engagement.'
        hints:
          readOnly: true
        call: vonage.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: podcast-ai-integration-capability-skills
      description: Agent Skill bundle for Vonage Podcast Ai Integration Capability.
      skills:
      - name: podcast-ai-integration-capability
        description: 'A capability tied to Guide-Use-Cases #1 (AI integration) as the podcast pitch hook for re-engagement.'
        location: file:///opt/naftiko/skills/podcast-ai-integration-capability
        allowed-tools: example
        tools:
        - name: example
          description: 'A capability tied to Guide-Use-Cases #1 (AI integration) as the podcast pitch hook for re-engagement.'
          from:
            sourceNamespace: podcast-ai-integration-capability-mcp
            action: example
---

A capability tied to Guide-Use-Cases #1 (AI integration) as the podcast pitch hook for re-engagement. Next-step is to contact for a podcast then make a proposal; an AI integration story for a CPaaS is the strongest opening.

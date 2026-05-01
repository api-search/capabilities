---
categories: []
consumed_apis:
- microsoft
description: 'Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on stories and shorts.'
layout: capability
naftiko_layer: proposed
naftiko_partner: Sébastien Levert
name: Microsoft M365 Rightsize Copilot Context Capability
operations: []
personas: []
provider_name: Microsoft
provider_slug: microsoft
search_terms:
- implements
- guide
- cases
- rightsize
- context
slug: m365-rightsize-copilot-context-capability
source_filename: m365-rightsize-copilot-context-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microsoft M365 Rightsize Copilot Context Capability
    description: 'Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on stories and shorts.'
    tags:
    - Microsoft
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: microsoft-env
    description: Microsoft credentials.
    keys:
      MICROSOFT_API_KEY: MICROSOFT_API_KEY
  capability:
    consumes:
    - namespace: microsoft
      type: http
      baseUri: https://api.microsoft.com
      authentication:
        type: bearer
        token: '{{MICROSOFT_API_KEY}}'
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
      namespace: m365-rightsize-copilot-context-capability-rest
      description: REST API for Microsoft M365 Rightsize Copilot Context Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: microsoft.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: m365-rightsize-copilot-context-capability-mcp
      description: MCP server exposing Microsoft M365 Rightsize Copilot Context Capability for AI agents.
      tools:
      - name: example
        description: 'Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on stories and shorts.'
        hints:
          readOnly: true
        call: microsoft.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: m365-rightsize-copilot-context-capability-skills
      description: Agent Skill bundle for Microsoft M365 Rightsize Copilot Context Capability.
      skills:
      - name: m365-rightsize-copilot-context-capability
        description: 'Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on stories and shorts.'
        location: file:///opt/naftiko/skills/m365-rightsize-copilot-context-capability
        allowed-tools: example
        tools:
        - name: example
          description: 'Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on stories and shorts.'
          from:
            sourceNamespace: m365-rightsize-copilot-context-capability-mcp
            action: example
---

Implements Guide-Use-Cases #2 (Rightsize AI context) against a verbose Graph endpoint, used as the basis for the follow-on stories and shorts. Rightsizing context is the exact pain Copilot DevX customers experience; reusable content tied to his episode.

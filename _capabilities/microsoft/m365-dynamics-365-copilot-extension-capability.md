---
categories: []
consumed_apis:
- microsoft
description: A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's "two developer paths" pattern (line-of-business AND ISV).
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Sébastien Levert
name: Microsoft M365 Dynamics 365 Copilot Extension Capability
operations: []
personas: []
provider_name: Microsoft
provider_slug: microsoft
search_terms:
- capability
- that
- wraps
- dynamics
- sales
slug: m365-dynamics-365-copilot-extension-capability
source_filename: m365-dynamics-365-copilot-extension-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microsoft M365 Dynamics 365 Copilot Extension Capability
    description: A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's "two developer paths" pattern (line-of-business AND ISV).
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
      namespace: m365-dynamics-365-copilot-extension-capability-rest
      description: REST API for Microsoft M365 Dynamics 365 Copilot Extension Capability.
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
      namespace: m365-dynamics-365-copilot-extension-capability-mcp
      description: MCP server exposing Microsoft M365 Dynamics 365 Copilot Extension Capability for AI agents.
      tools:
      - name: example
        description: A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's "two developer paths" pattern (line-of-business AND ISV).
        hints:
          readOnly: true
        call: microsoft.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: m365-dynamics-365-copilot-extension-capability-skills
      description: Agent Skill bundle for Microsoft M365 Dynamics 365 Copilot Extension Capability.
      skills:
      - name: m365-dynamics-365-copilot-extension-capability
        description: A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's "two developer paths" pattern (line-of-business AND ISV).
        location: file:///opt/naftiko/skills/m365-dynamics-365-copilot-extension-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's "two developer paths" pattern (line-of-business AND ISV).
          from:
            sourceNamespace: m365-dynamics-365-copilot-extension-capability-mcp
            action: example
---

A capability that wraps a Dynamics 365 (Sales/Service) endpoint as both an ISV-style M365 Copilot extension AND an MCP tool, demonstrating Sébastien's "two developer paths" pattern (line-of-business AND ISV). His 2026-02-20 conversation explicitly named the line-of-business + ISV split — Dynamics 365 is the canonical ISV integration target.

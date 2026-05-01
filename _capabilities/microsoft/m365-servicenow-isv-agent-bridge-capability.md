---
categories: []
consumed_apis:
- microsoft
description: A capability that wraps a ServiceNow operation as both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Sébastien Levert
name: Microsoft M365 Servicenow Isv Agent Bridge Capability
operations: []
personas: []
provider_name: Microsoft
provider_slug: microsoft
search_terms:
- capability
- that
- wraps
- servicenow
- operation
slug: m365-servicenow-isv-agent-bridge-capability
source_filename: m365-servicenow-isv-agent-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microsoft M365 Servicenow Isv Agent Bridge Capability
    description: A capability that wraps a ServiceNow operation as both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path.
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
      namespace: m365-servicenow-isv-agent-bridge-capability-rest
      description: REST API for Microsoft M365 Servicenow Isv Agent Bridge Capability.
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
      namespace: m365-servicenow-isv-agent-bridge-capability-mcp
      description: MCP server exposing Microsoft M365 Servicenow Isv Agent Bridge Capability for AI agents.
      tools:
      - name: example
        description: A capability that wraps a ServiceNow operation as both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path.
        hints:
          readOnly: true
        call: microsoft.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: m365-servicenow-isv-agent-bridge-capability-skills
      description: Agent Skill bundle for Microsoft M365 Servicenow Isv Agent Bridge Capability.
      skills:
      - name: m365-servicenow-isv-agent-bridge-capability
        description: A capability that wraps a ServiceNow operation as both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path.
        location: file:///opt/naftiko/skills/m365-servicenow-isv-agent-bridge-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that wraps a ServiceNow operation as both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path.
          from:
            sourceNamespace: m365-servicenow-isv-agent-bridge-capability-mcp
            action: example
---

A capability that wraps a ServiceNow operation as both a native ISV agent installed inside M365 Copilot AND an MCP tool, demonstrating Sébastien's agent-to-agent ISV path. ServiceNow is the exact ISV example he gave for the agent-auto-installed-in-Copilot pattern; building it makes his ISV story concrete and reusable.

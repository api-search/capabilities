---
categories: []
consumed_apis:
- vanguard
description: A capability designed to be exercised in 30 minutes via the Naftiko VS Code extension + Backstage template by an architect at his desk.
layout: capability
naftiko_layer: proposed
naftiko_partner: Vanguard
name: Vanguard Vscode 30min Validation Capability
operations: []
personas: []
provider_name: Vanguard
provider_slug: vanguard
search_terms:
- capability
- designed
- exercised
- minutes
- naftiko
slug: vscode-30min-validation-capability
source_filename: vscode-30min-validation-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vanguard Vscode 30min Validation Capability
    description: A capability designed to be exercised in 30 minutes via the Naftiko VS Code extension + Backstage template by an architect at his desk.
    tags:
    - Vanguard
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: vanguard-env
    description: Vanguard credentials.
    keys:
      VANGUARD_API_KEY: VANGUARD_API_KEY
  capability:
    consumes:
    - namespace: vanguard
      type: http
      baseUri: https://api.vanguard.com
      authentication:
        type: bearer
        token: '{{VANGUARD_API_KEY}}'
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
      namespace: vscode-30min-validation-capability-rest
      description: REST API for Vanguard Vscode 30min Validation Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: vanguard.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: vscode-30min-validation-capability-mcp
      description: MCP server exposing Vanguard Vscode 30min Validation Capability for AI agents.
      tools:
      - name: example
        description: A capability designed to be exercised in 30 minutes via the Naftiko VS Code extension + Backstage template by an architect at his desk.
        hints:
          readOnly: true
        call: vanguard.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: vscode-30min-validation-capability-skills
      description: Agent Skill bundle for Vanguard Vscode 30min Validation Capability.
      skills:
      - name: vscode-30min-validation-capability
        description: A capability designed to be exercised in 30 minutes via the Naftiko VS Code extension + Backstage template by an architect at his desk.
        location: file:///opt/naftiko/skills/vscode-30min-validation-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability designed to be exercised in 30 minutes via the Naftiko VS Code extension + Backstage template by an architect at his desk.
          from:
            sourceNamespace: vscode-30min-validation-capability-mcp
            action: example
---

A capability designed to be exercised in 30 minutes via the Naftiko VS Code extension + Backstage template by an architect at his desk. **Paul Tihansky's** SA persona prefers to validate themselves before booking time; the fleet artifacts let him do that.

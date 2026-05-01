---
categories: []
consumed_apis:
- schneider-electric
description: A capability that drops an approved MCP server entry into the developer's VS Code Copilot extensions window, closing the loop registry → install.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Manu PK
name: Schneider Electric Schneider Github Copilot Mcp Extension Installer Capability
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- capability
- that
- drops
- approved
- server
slug: schneider-github-copilot-mcp-extension-installer-capability
source_filename: schneider-github-copilot-mcp-extension-installer-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider Github Copilot Mcp Extension Installer Capability
    description: A capability that drops an approved MCP server entry into the developer's VS Code Copilot extensions window, closing the loop registry → install.
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
      namespace: schneider-github-copilot-mcp-extension-installer-capability-rest
      description: REST API for Schneider Electric Schneider Github Copilot Mcp Extension Installer Capability.
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
      namespace: schneider-github-copilot-mcp-extension-installer-capability-mcp
      description: MCP server exposing Schneider Electric Schneider Github Copilot Mcp Extension Installer Capability for AI agents.
      tools:
      - name: example
        description: A capability that drops an approved MCP server entry into the developer's VS Code Copilot extensions window, closing the loop registry → install.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-github-copilot-mcp-extension-installer-capability-skills
      description: Agent Skill bundle for Schneider Electric Schneider Github Copilot Mcp Extension Installer Capability.
      skills:
      - name: schneider-github-copilot-mcp-extension-installer-capability
        description: A capability that drops an approved MCP server entry into the developer's VS Code Copilot extensions window, closing the loop registry → install.
        location: file:///opt/naftiko/skills/schneider-github-copilot-mcp-extension-installer-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that drops an approved MCP server entry into the developer's VS Code Copilot extensions window, closing the loop registry → install.
          from:
            sourceNamespace: schneider-github-copilot-mcp-extension-installer-capability-mcp
            action: example
---

A capability that drops an approved MCP server entry into the developer's VS Code Copilot extensions window, closing the loop registry → install. Distribution-into-IDE was the friction-removal he highlighted; making it Naftiko-driven is the natural next layer.

---
categories: []
consumed_apis:
- ford
description: A capability that consumes the GitHub MCP, Jira MCP, and Figma MCP servers and exposes a Ford-policy-tagged allow-list view that VS Code + Copilot can install from, with security-team-blessed risk attestations attached per server.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Third Party Mcp Ide Allow List Capability
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- consumes
- github
- jira
slug: third-party-mcp-ide-allow-list-capability
source_filename: third-party-mcp-ide-allow-list-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Third Party Mcp Ide Allow List Capability
    description: A capability that consumes the GitHub MCP, Jira MCP, and Figma MCP servers and exposes a Ford-policy-tagged allow-list view that VS Code + Copilot can install from, with security-team-blessed risk attestations attached per server.
    tags:
    - Ford
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: ford-env
    description: Ford credentials.
    keys:
      FORD_API_KEY: FORD_API_KEY
  capability:
    consumes:
    - namespace: ford
      type: http
      baseUri: https://api.ford.com
      authentication:
        type: bearer
        token: '{{FORD_API_KEY}}'
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
      namespace: third-party-mcp-ide-allow-list-capability-rest
      description: REST API for Ford Third Party Mcp Ide Allow List Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: ford.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: third-party-mcp-ide-allow-list-capability-mcp
      description: MCP server exposing Ford Third Party Mcp Ide Allow List Capability for AI agents.
      tools:
      - name: example
        description: A capability that consumes the GitHub MCP, Jira MCP, and Figma MCP servers and exposes a Ford-policy-tagged allow-list view that VS Code + Copilot can install from, with security-team-blessed risk attestations attached per server.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: third-party-mcp-ide-allow-list-capability-skills
      description: Agent Skill bundle for Ford Third Party Mcp Ide Allow List Capability.
      skills:
      - name: third-party-mcp-ide-allow-list-capability
        description: A capability that consumes the GitHub MCP, Jira MCP, and Figma MCP servers and exposes a Ford-policy-tagged allow-list view that VS Code + Copilot can install from, with security-team-blessed risk attestations attached per server.
        location: file:///opt/naftiko/skills/third-party-mcp-ide-allow-list-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes the GitHub MCP, Jira MCP, and Figma MCP servers and exposes a Ford-policy-tagged allow-list view that VS Code + Copilot can install from, with security-team-blessed risk attestations attached per server.
          from:
            sourceNamespace: third-party-mcp-ide-allow-list-capability-mcp
            action: example
---

A capability that consumes the GitHub MCP, Jira MCP, and Figma MCP servers and exposes a Ford-policy-tagged allow-list view that VS Code + Copilot can install from, with security-team-blessed risk attestations attached per server. This answers his ranked MCP priority #1 verbatim — "securely enabling third-party MCP servers" — with the exact three vendors he named.

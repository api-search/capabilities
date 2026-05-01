---
categories: []
consumed_apis:
- speakeasy
description: A capability that takes a Speakeasy-generated SDK + agent skill pair and surfaces the relevant slice into a VS Code Copilot-style coding agent on demand.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Daniel Kovac
name: Speakeasy Openapi To Vscode Coding Agent Bridge
operations: []
personas: []
provider_name: Speakeasy
provider_slug: speakeasy
search_terms:
- capability
- that
- takes
- speakeasy
- generated
slug: openapi-to-vscode-coding-agent-bridge
source_filename: openapi-to-vscode-coding-agent-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Speakeasy Openapi To Vscode Coding Agent Bridge
    description: A capability that takes a Speakeasy-generated SDK + agent skill pair and surfaces the relevant slice into a VS Code Copilot-style coding agent on demand.
    tags:
    - Speakeasy
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: speakeasy-env
    description: Speakeasy credentials.
    keys:
      SPEAKEASY_API_KEY: SPEAKEASY_API_KEY
  capability:
    consumes:
    - namespace: speakeasy
      type: http
      baseUri: https://api.speakeasy.com
      authentication:
        type: bearer
        token: '{{SPEAKEASY_API_KEY}}'
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
      namespace: openapi-to-vscode-coding-agent-bridge-rest
      description: REST API for Speakeasy Openapi To Vscode Coding Agent Bridge.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: speakeasy.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: openapi-to-vscode-coding-agent-bridge-mcp
      description: MCP server exposing Speakeasy Openapi To Vscode Coding Agent Bridge for AI agents.
      tools:
      - name: example
        description: A capability that takes a Speakeasy-generated SDK + agent skill pair and surfaces the relevant slice into a VS Code Copilot-style coding agent on demand.
        hints:
          readOnly: true
        call: speakeasy.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: openapi-to-vscode-coding-agent-bridge-skills
      description: Agent Skill bundle for Speakeasy Openapi To Vscode Coding Agent Bridge.
      skills:
      - name: openapi-to-vscode-coding-agent-bridge
        description: A capability that takes a Speakeasy-generated SDK + agent skill pair and surfaces the relevant slice into a VS Code Copilot-style coding agent on demand.
        location: file:///opt/naftiko/skills/openapi-to-vscode-coding-agent-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A capability that takes a Speakeasy-generated SDK + agent skill pair and surfaces the relevant slice into a VS Code Copilot-style coding agent on demand.
          from:
            sourceNamespace: openapi-to-vscode-coding-agent-bridge-mcp
            action: example
---

A capability that takes a Speakeasy-generated SDK + agent skill pair and surfaces the relevant slice into a VS Code Copilot-style coding agent on demand. His next-step is using Speakeasy as a reference model; running the bridge end-to-end into VS Code is the artifact that proves it.

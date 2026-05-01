---
categories: []
consumed_apis:
- vanguard
description: A capability that exposes Vanguard-internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Vanguard
name: Vanguard Github Copilot Mcp Developer Onboarding Capability
operations: []
personas: []
provider_name: Vanguard
provider_slug: vanguard
search_terms:
- capability
- that
- exposes
- vanguard
- internal
slug: github-copilot-mcp-developer-onboarding-capability
source_filename: github-copilot-mcp-developer-onboarding-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vanguard Github Copilot Mcp Developer Onboarding Capability
    description: A capability that exposes Vanguard-internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point.
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
      namespace: github-copilot-mcp-developer-onboarding-capability-rest
      description: REST API for Vanguard Github Copilot Mcp Developer Onboarding Capability.
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
      namespace: github-copilot-mcp-developer-onboarding-capability-mcp
      description: MCP server exposing Vanguard Github Copilot Mcp Developer Onboarding Capability for AI agents.
      tools:
      - name: example
        description: A capability that exposes Vanguard-internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point.
        hints:
          readOnly: true
        call: vanguard.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: github-copilot-mcp-developer-onboarding-capability-skills
      description: Agent Skill bundle for Vanguard Github Copilot Mcp Developer Onboarding Capability.
      skills:
      - name: github-copilot-mcp-developer-onboarding-capability
        description: A capability that exposes Vanguard-internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point.
        location: file:///opt/naftiko/skills/github-copilot-mcp-developer-onboarding-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that exposes Vanguard-internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point.
          from:
            sourceNamespace: github-copilot-mcp-developer-onboarding-capability-mcp
            action: example
---

A capability that exposes Vanguard-internal Naftiko capabilities as MCP servers inside GitHub Copilot's VS Code extension window — the developer-onboarding fleet entry-point. The api/eventDriven/dataPipelines gap shows up first as a developer-onboarding gap; making capabilities discoverable inside Copilot meets developers where they are.

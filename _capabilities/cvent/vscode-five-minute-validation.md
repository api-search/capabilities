---
categories: []
consumed_apis:
- cvent
description: A small, single-file capability designed to be dropped into VS Code with the Naftiko extension and validated end-to-end in 5 minutes (lint, run, MCP-test) — sent as the "summary message" attachment.
layout: capability
naftiko_layer: proposed
naftiko_partner: Jeff Seifert
name: Cvent Vscode Five Minute Validation
operations: []
personas: []
provider_name: Cvent
provider_slug: cvent
search_terms:
- small
- single
- file
- capability
- designed
slug: vscode-five-minute-validation
source_filename: vscode-five-minute-validation.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Cvent Vscode Five Minute Validation
    description: A small, single-file capability designed to be dropped into VS Code with the Naftiko extension and validated end-to-end in 5 minutes (lint, run, MCP-test) — sent as the "summary message" attachment.
    tags:
    - Cvent
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: cvent-env
    description: Cvent credentials.
    keys:
      CVENT_API_KEY: CVENT_API_KEY
  capability:
    consumes:
    - namespace: cvent
      type: http
      baseUri: https://api.cvent.com
      authentication:
        type: bearer
        token: '{{CVENT_API_KEY}}'
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
      namespace: vscode-five-minute-validation-rest
      description: REST API for Cvent Vscode Five Minute Validation.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: cvent.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: vscode-five-minute-validation-mcp
      description: MCP server exposing Cvent Vscode Five Minute Validation for AI agents.
      tools:
      - name: example
        description: A small, single-file capability designed to be dropped into VS Code with the Naftiko extension and validated end-to-end in 5 minutes (lint, run, MCP-test) — sent as the "summary message" attachment.
        hints:
          readOnly: true
        call: cvent.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: vscode-five-minute-validation-skills
      description: Agent Skill bundle for Cvent Vscode Five Minute Validation.
      skills:
      - name: vscode-five-minute-validation
        description: A small, single-file capability designed to be dropped into VS Code with the Naftiko extension and validated end-to-end in 5 minutes (lint, run, MCP-test) — sent as the "summary message" attachment.
        location: file:///opt/naftiko/skills/vscode-five-minute-validation
        allowed-tools: example
        tools:
        - name: example
          description: A small, single-file capability designed to be dropped into VS Code with the Naftiko extension and validated end-to-end in 5 minutes (lint, run, MCP-test) — sent as the "summary message" attachment.
          from:
            sourceNamespace: vscode-five-minute-validation-mcp
            action: example
---

A small, single-file capability designed to be dropped into VS Code with the Naftiko extension and validated end-to-end in 5 minutes (lint, run, MCP-test) — sent as the "summary message" attachment. His next-step is a summary message; the VSIX-validatable artifact is the highest-signal attachment.

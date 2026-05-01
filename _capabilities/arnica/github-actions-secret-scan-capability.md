---
categories: []
consumed_apis:
- arnica
description: A capability that consumes Arnica's GitHub-scan webhook + GitHub Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Anna Daugherty
name: Arnica Github Actions Secret Scan Capability
operations: []
personas: []
provider_name: Arnica
provider_slug: arnica
search_terms:
- capability
- that
- consumes
- arnica
- github
slug: github-actions-secret-scan-capability
source_filename: github-actions-secret-scan-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Arnica Github Actions Secret Scan Capability
    description: A capability that consumes Arnica's GitHub-scan webhook + GitHub Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant.
    tags:
    - Arnica
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: arnica-env
    description: Arnica credentials.
    keys:
      ARNICA_API_KEY: ARNICA_API_KEY
  capability:
    consumes:
    - namespace: arnica
      type: http
      baseUri: https://api.arnica.com
      authentication:
        type: bearer
        token: '{{ARNICA_API_KEY}}'
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
      namespace: github-actions-secret-scan-capability-rest
      description: REST API for Arnica Github Actions Secret Scan Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: arnica.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: github-actions-secret-scan-capability-mcp
      description: MCP server exposing Arnica Github Actions Secret Scan Capability for AI agents.
      tools:
      - name: example
        description: A capability that consumes Arnica's GitHub-scan webhook + GitHub Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant.
        hints:
          readOnly: true
        call: arnica.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: github-actions-secret-scan-capability-skills
      description: Agent Skill bundle for Arnica Github Actions Secret Scan Capability.
      skills:
      - name: github-actions-secret-scan-capability
        description: A capability that consumes Arnica's GitHub-scan webhook + GitHub Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant.
        location: file:///opt/naftiko/skills/github-actions-secret-scan-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes Arnica's GitHub-scan webhook + GitHub Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant.
          from:
            sourceNamespace: github-actions-secret-scan-capability-mcp
            action: example
---

A capability that consumes Arnica's GitHub-scan webhook + GitHub Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant. Arnica's flagship surface is GitHub; co-demoing Arnica scans + Naftiko governance on shared output is the partnership-with-teeth artifact.

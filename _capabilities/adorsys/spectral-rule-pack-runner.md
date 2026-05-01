---
categories: []
consumed_apis:
- adorsys
description: A capability that runs the Naftiko Spectral rule pack against a target OpenAPI doc and returns lint findings shaped for an agent.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Daniel Kocot
name: Adorsys Spectral Rule Pack Runner
operations: []
personas: []
provider_name: Adorsys
provider_slug: adorsys
search_terms:
- capability
- that
- runs
- naftiko
- spectral
slug: spectral-rule-pack-runner
source_filename: spectral-rule-pack-runner.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Adorsys Spectral Rule Pack Runner
    description: A capability that runs the Naftiko Spectral rule pack against a target OpenAPI doc and returns lint findings shaped for an agent.
    tags:
    - Adorsys
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: adorsys-env
    description: Adorsys credentials.
    keys:
      ADORSYS_API_KEY: ADORSYS_API_KEY
  capability:
    consumes:
    - namespace: adorsys
      type: http
      baseUri: https://api.adorsys.com
      authentication:
        type: bearer
        token: '{{ADORSYS_API_KEY}}'
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
      namespace: spectral-rule-pack-runner-rest
      description: REST API for Adorsys Spectral Rule Pack Runner.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: adorsys.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: spectral-rule-pack-runner-mcp
      description: MCP server exposing Adorsys Spectral Rule Pack Runner for AI agents.
      tools:
      - name: example
        description: A capability that runs the Naftiko Spectral rule pack against a target OpenAPI doc and returns lint findings shaped for an agent.
        hints:
          readOnly: true
        call: adorsys.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: spectral-rule-pack-runner-skills
      description: Agent Skill bundle for Adorsys Spectral Rule Pack Runner.
      skills:
      - name: spectral-rule-pack-runner
        description: A capability that runs the Naftiko Spectral rule pack against a target OpenAPI doc and returns lint findings shaped for an agent.
        location: file:///opt/naftiko/skills/spectral-rule-pack-runner
        allowed-tools: example
        tools:
        - name: example
          description: A capability that runs the Naftiko Spectral rule pack against a target OpenAPI doc and returns lint findings shaped for an agent.
          from:
            sourceNamespace: spectral-rule-pack-runner-mcp
            action: example
---

A capability that runs the Naftiko Spectral rule pack against a target OpenAPI doc and returns lint findings shaped for an agent. His thesis frames governance-as-spec-quality; Spectral is the tooling everyone in his audience already runs.

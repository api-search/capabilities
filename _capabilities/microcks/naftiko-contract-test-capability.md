---
categories: []
consumed_apis:
- microcks
description: A capability where the same YAML drives a Microcks mock + the Naftiko engine, so dev/test/prod share one artifact.
layout: capability
naftiko_layer: proposed
naftiko_partner: Laurent Broudoux
name: Microcks Naftiko Contract Test Capability
operations: []
personas: []
provider_name: Microcks
provider_slug: microcks
search_terms:
- capability
- where
- same
- yaml
- drives
slug: naftiko-contract-test-capability
source_filename: naftiko-contract-test-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microcks Naftiko Contract Test Capability
    description: A capability where the same YAML drives a Microcks mock + the Naftiko engine, so dev/test/prod share one artifact.
    tags:
    - Microcks
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: microcks-env
    description: Microcks credentials.
    keys:
      MICROCKS_API_KEY: MICROCKS_API_KEY
  capability:
    consumes:
    - namespace: microcks
      type: http
      baseUri: https://api.microcks.com
      authentication:
        type: bearer
        token: '{{MICROCKS_API_KEY}}'
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
      namespace: naftiko-contract-test-capability-rest
      description: REST API for Microcks Naftiko Contract Test Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: microcks.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: naftiko-contract-test-capability-mcp
      description: MCP server exposing Microcks Naftiko Contract Test Capability for AI agents.
      tools:
      - name: example
        description: A capability where the same YAML drives a Microcks mock + the Naftiko engine, so dev/test/prod share one artifact.
        hints:
          readOnly: true
        call: microcks.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: naftiko-contract-test-capability-skills
      description: Agent Skill bundle for Microcks Naftiko Contract Test Capability.
      skills:
      - name: naftiko-contract-test-capability
        description: A capability where the same YAML drives a Microcks mock + the Naftiko engine, so dev/test/prod share one artifact.
        location: file:///opt/naftiko/skills/naftiko-contract-test-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability where the same YAML drives a Microcks mock + the Naftiko engine, so dev/test/prod share one artifact.
          from:
            sourceNamespace: naftiko-contract-test-capability-mcp
            action: example
---

A capability where the same YAML drives a Microcks mock + the Naftiko engine, so dev/test/prod share one artifact. Microcks is already deployed in Naftiko's mocking stack; this formalizes that pattern as a published reference and answers his "future of partnership" question structurally.

---
categories: []
consumed_apis:
- palo-alto-networks
description: A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime.
layout: capability
naftiko_layer: proposed
naftiko_partner: James DeVore
name: Palo Alto Networks Palo Alto Cli Only Runnable Capability
operations: []
personas: []
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- capability
- designed
- exercised
- entirely
- naftiko
slug: palo-alto-cli-only-runnable-capability
source_filename: palo-alto-cli-only-runnable-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Palo Alto Networks Palo Alto Cli Only Runnable Capability
    description: A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime.
    tags:
    - Palo Alto Networks
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: palo-alto-networks-env
    description: Palo Alto Networks credentials.
    keys:
      PALO_ALTO_NETWORKS_API_KEY: PALO_ALTO_NETWORKS_API_KEY
  capability:
    consumes:
    - namespace: palo-alto-networks
      type: http
      baseUri: https://api.palo-alto-networks.com
      authentication:
        type: bearer
        token: '{{PALO_ALTO_NETWORKS_API_KEY}}'
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
      namespace: palo-alto-cli-only-runnable-capability-rest
      description: REST API for Palo Alto Networks Palo Alto Cli Only Runnable Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: palo-alto-networks.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: palo-alto-cli-only-runnable-capability-mcp
      description: MCP server exposing Palo Alto Networks Palo Alto Cli Only Runnable Capability for AI agents.
      tools:
      - name: example
        description: A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime.
        hints:
          readOnly: true
        call: palo-alto-networks.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: palo-alto-cli-only-runnable-capability-skills
      description: Agent Skill bundle for Palo Alto Networks Palo Alto Cli Only Runnable Capability.
      skills:
      - name: palo-alto-cli-only-runnable-capability
        description: A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime.
        location: file:///opt/naftiko/skills/palo-alto-cli-only-runnable-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime.
          from:
            sourceNamespace: palo-alto-cli-only-runnable-capability-mcp
            action: example
---

A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime. His next-step is blocked on container startup; a CLI-only path unblocks the partnership.

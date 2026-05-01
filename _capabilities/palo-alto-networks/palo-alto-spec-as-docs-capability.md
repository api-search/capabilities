---
categories: []
consumed_apis:
- palo-alto-networks
description: Wraps a Palo Alto API James already documents and treats the YAML + SKILL.md as the canonical documentation, repositioning his Lead Technical Writer role as the spec author.
layout: capability
naftiko_layer: proposed
naftiko_partner: James DeVore
name: Palo Alto Networks Palo Alto Spec As Docs Capability
operations: []
personas: []
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- wraps
- palo
- alto
- james
- already
slug: palo-alto-spec-as-docs-capability
source_filename: palo-alto-spec-as-docs-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Palo Alto Networks Palo Alto Spec As Docs Capability
    description: Wraps a Palo Alto API James already documents and treats the YAML + SKILL.md as the canonical documentation, repositioning his Lead Technical Writer role as the spec author.
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
      namespace: palo-alto-spec-as-docs-capability-rest
      description: REST API for Palo Alto Networks Palo Alto Spec As Docs Capability.
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
      namespace: palo-alto-spec-as-docs-capability-mcp
      description: MCP server exposing Palo Alto Networks Palo Alto Spec As Docs Capability for AI agents.
      tools:
      - name: example
        description: Wraps a Palo Alto API James already documents and treats the YAML + SKILL.md as the canonical documentation, repositioning his Lead Technical Writer role as the spec author.
        hints:
          readOnly: true
        call: palo-alto-networks.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: palo-alto-spec-as-docs-capability-skills
      description: Agent Skill bundle for Palo Alto Networks Palo Alto Spec As Docs Capability.
      skills:
      - name: palo-alto-spec-as-docs-capability
        description: Wraps a Palo Alto API James already documents and treats the YAML + SKILL.md as the canonical documentation, repositioning his Lead Technical Writer role as the spec author.
        location: file:///opt/naftiko/skills/palo-alto-spec-as-docs-capability
        allowed-tools: example
        tools:
        - name: example
          description: Wraps a Palo Alto API James already documents and treats the YAML + SKILL.md as the canonical documentation, repositioning his Lead Technical Writer role as the spec author.
          from:
            sourceNamespace: palo-alto-spec-as-docs-capability-mcp
            action: example
---

Wraps a Palo Alto API James already documents and treats the YAML + SKILL.md as the canonical documentation, repositioning his Lead Technical Writer role as the spec author. His role IS the persona SDI reframes — show that the spec is the docs.

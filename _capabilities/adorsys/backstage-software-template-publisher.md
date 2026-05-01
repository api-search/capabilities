---
categories: []
consumed_apis:
- adorsys
description: Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Daniel Kocot
name: Adorsys Backstage Software Template Publisher
operations: []
personas: []
provider_name: Adorsys
provider_slug: adorsys
search_terms:
- publishes
- naftiko
- spec
- driven
- integration
slug: backstage-software-template-publisher
source_filename: backstage-software-template-publisher.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Adorsys Backstage Software Template Publisher
    description: Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich.
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
      namespace: backstage-software-template-publisher-rest
      description: REST API for Adorsys Backstage Software Template Publisher.
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
      namespace: backstage-software-template-publisher-mcp
      description: MCP server exposing Adorsys Backstage Software Template Publisher for AI agents.
      tools:
      - name: example
        description: Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich.
        hints:
          readOnly: true
        call: adorsys.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: backstage-software-template-publisher-skills
      description: Agent Skill bundle for Adorsys Backstage Software Template Publisher.
      skills:
      - name: backstage-software-template-publisher
        description: Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich.
        location: file:///opt/naftiko/skills/backstage-software-template-publisher
        allowed-tools: example
        tools:
        - name: example
          description: Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich.
          from:
            sourceNamespace: backstage-software-template-publisher-mcp
            action: example
---

Publishes the Naftiko Spec-Driven Integration Backstage template into a Backstage catalog Daniel can demo at apidays Munich. His Spec-Driven Integration field-guide work names Backstage as the primary scaffolding surface; this turns the recommendation into a runnable artifact.

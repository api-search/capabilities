---
categories: []
consumed_apis:
- cvent
description: A Backstage software template that scaffolds a Cvent-shaped capability + K8s manifests + MCP exposure as a single, opinionated bundle.
layout: capability
naftiko_layer: proposed
naftiko_partner: Jeff Seifert
name: Cvent Platform Bundle Backstage Template
operations: []
personas: []
provider_name: Cvent
provider_slug: cvent
search_terms:
- backstage
- software
- template
- that
- scaffolds
slug: platform-bundle-backstage-template
source_filename: platform-bundle-backstage-template.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Cvent Platform Bundle Backstage Template
    description: A Backstage software template that scaffolds a Cvent-shaped capability + K8s manifests + MCP exposure as a single, opinionated bundle.
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
      namespace: platform-bundle-backstage-template-rest
      description: REST API for Cvent Platform Bundle Backstage Template.
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
      namespace: platform-bundle-backstage-template-mcp
      description: MCP server exposing Cvent Platform Bundle Backstage Template for AI agents.
      tools:
      - name: example
        description: A Backstage software template that scaffolds a Cvent-shaped capability + K8s manifests + MCP exposure as a single, opinionated bundle.
        hints:
          readOnly: true
        call: cvent.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: platform-bundle-backstage-template-skills
      description: Agent Skill bundle for Cvent Platform Bundle Backstage Template.
      skills:
      - name: platform-bundle-backstage-template
        description: A Backstage software template that scaffolds a Cvent-shaped capability + K8s manifests + MCP exposure as a single, opinionated bundle.
        location: file:///opt/naftiko/skills/platform-bundle-backstage-template
        allowed-tools: example
        tools:
        - name: example
          description: A Backstage software template that scaffolds a Cvent-shaped capability + K8s manifests + MCP exposure as a single, opinionated bundle.
          from:
            sourceNamespace: platform-bundle-backstage-template-mcp
            action: example
---

A Backstage software template that scaffolds a Cvent-shaped capability + K8s manifests + MCP exposure as a single, opinionated bundle. He asked for Backstage AND Kubernetes capabilities — this is one template that produces both.

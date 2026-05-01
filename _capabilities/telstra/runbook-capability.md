---
categories: []
consumed_apis:
- telstra
description: A Telstra-flavored capability scaffolded with K8s manifests + observability built in, sent as the un-sticker — "here's what running Naftiko in Telstra's platform looks like."
layout: capability
naftiko_layer: proposed
naftiko_partner: Ranjaka De Mel
name: Telstra Runbook Capability
operations: []
personas: []
provider_name: Telstra
provider_slug: telstra
search_terms:
- telstra
- flavored
- capability
- scaffolded
- with
slug: runbook-capability
source_filename: runbook-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Telstra Runbook Capability
    description: A Telstra-flavored capability scaffolded with K8s manifests + observability built in, sent as the un-sticker — "here's what running Naftiko in Telstra's platform looks like."
    tags:
    - Telstra
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: telstra-env
    description: Telstra credentials.
    keys:
      TELSTRA_API_KEY: TELSTRA_API_KEY
  capability:
    consumes:
    - namespace: telstra
      type: http
      baseUri: https://api.telstra.com
      authentication:
        type: bearer
        token: '{{TELSTRA_API_KEY}}'
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
      namespace: runbook-capability-rest
      description: REST API for Telstra Runbook Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: telstra.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: runbook-capability-mcp
      description: MCP server exposing Telstra Runbook Capability for AI agents.
      tools:
      - name: example
        description: A Telstra-flavored capability scaffolded with K8s manifests + observability built in, sent as the un-sticker — "here's what running Naftiko in Telstra's platform looks like."
        hints:
          readOnly: true
        call: telstra.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: runbook-capability-skills
      description: Agent Skill bundle for Telstra Runbook Capability.
      skills:
      - name: runbook-capability
        description: A Telstra-flavored capability scaffolded with K8s manifests + observability built in, sent as the un-sticker — "here's what running Naftiko in Telstra's platform looks like."
        location: file:///opt/naftiko/skills/runbook-capability
        allowed-tools: example
        tools:
        - name: example
          description: A Telstra-flavored capability scaffolded with K8s manifests + observability built in, sent as the un-sticker — "here's what running Naftiko in Telstra's platform looks like."
          from:
            sourceNamespace: runbook-capability-mcp
            action: example
---

A Telstra-flavored capability scaffolded with K8s manifests + observability built in, sent as the un-sticker — "here's what running Naftiko in Telstra's platform looks like." Twice expressed interest, never scheduled; tangible runbook is the un-sticker.

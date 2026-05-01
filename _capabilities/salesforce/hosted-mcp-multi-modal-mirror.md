---
categories: []
consumed_apis:
- salesforce
description: A capability that mirrors a Salesforce object across REST + GraphQL + Salesforce hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc — Kris's exact methodology argument.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Kris Harrison
name: Salesforce Hosted Mcp Multi Modal Mirror
operations: []
personas: []
provider_name: Salesforce
provider_slug: salesforce
search_terms:
- capability
- that
- mirrors
- salesforce
- object
slug: hosted-mcp-multi-modal-mirror
source_filename: hosted-mcp-multi-modal-mirror.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Salesforce Hosted Mcp Multi Modal Mirror
    description: A capability that mirrors a Salesforce object across REST + GraphQL + Salesforce hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc — Kris's exact methodology argument.
    tags:
    - Salesforce
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: salesforce-env
    description: Salesforce credentials.
    keys:
      SALESFORCE_API_KEY: SALESFORCE_API_KEY
  capability:
    consumes:
    - namespace: salesforce
      type: http
      baseUri: https://api.salesforce.com
      authentication:
        type: bearer
        token: '{{SALESFORCE_API_KEY}}'
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
      namespace: hosted-mcp-multi-modal-mirror-rest
      description: REST API for Salesforce Hosted Mcp Multi Modal Mirror.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: salesforce.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: hosted-mcp-multi-modal-mirror-mcp
      description: MCP server exposing Salesforce Hosted Mcp Multi Modal Mirror for AI agents.
      tools:
      - name: example
        description: A capability that mirrors a Salesforce object across REST + GraphQL + Salesforce hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc — Kris's exact methodology argument.
        hints:
          readOnly: true
        call: salesforce.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: hosted-mcp-multi-modal-mirror-skills
      description: Agent Skill bundle for Salesforce Hosted Mcp Multi Modal Mirror.
      skills:
      - name: hosted-mcp-multi-modal-mirror
        description: A capability that mirrors a Salesforce object across REST + GraphQL + Salesforce hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc — Kris's exact methodology argument.
        location: file:///opt/naftiko/skills/hosted-mcp-multi-modal-mirror
        allowed-tools: example
        tools:
        - name: example
          description: A capability that mirrors a Salesforce object across REST + GraphQL + Salesforce hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc — Kris's exact methodology argument.
          from:
            sourceNamespace: hosted-mcp-multi-modal-mirror-mcp
            action: example
---

A capability that mirrors a Salesforce object across REST + GraphQL + Salesforce hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc — Kris's exact methodology argument. He explicitly framed MCP as another integration mode beside REST/GraphQL/gRPC — this is the artifact that proves governance scales across modes.

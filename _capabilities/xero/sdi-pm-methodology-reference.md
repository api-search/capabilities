---
categories: []
consumed_apis:
- xero
description: A reference capability tied to SDI as the post-podcast methodology read for her PM team before apidays NYC.
layout: capability
naftiko_layer: proposed
naftiko_partner: Rose Missier
name: Xero Sdi Pm Methodology Reference
operations: []
personas: []
provider_name: Xero
provider_slug: xero
search_terms:
- reference
- capability
- tied
- post
- podcast
slug: sdi-pm-methodology-reference
source_filename: sdi-pm-methodology-reference.yaml
source_heading: Capability Spec
source_yaml: |
  naftiko: 1.0.0-alpha2
  info:
    title: Xero Sdi Pm Methodology Reference
    description: A reference capability tied to SDI as the post-podcast methodology read for her PM team before apidays NYC.
    tags:
    - Xero
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: xero-env
    description: Xero credentials.
    keys:
      XERO_API_KEY: XERO_API_KEY
  capability:
    consumes:
    - namespace: xero
      type: http
      baseUri: https://api.xero.com
      authentication:
        type: bearer
        token: '{{XERO_API_KEY}}'
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
      namespace: sdi-pm-methodology-reference-rest
      description: REST API for Xero Sdi Pm Methodology Reference.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: xero.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: sdi-pm-methodology-reference-mcp
      description: MCP server exposing Xero Sdi Pm Methodology Reference for AI agents.
      tools:
      - name: example
        description: A reference capability tied to SDI as the post-podcast methodology read for her PM team before apidays NYC.
        hints:
          readOnly: true
        call: xero.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: sdi-pm-methodology-reference-skills
      description: Agent Skill bundle for Xero Sdi Pm Methodology Reference.
      skills:
      - name: sdi-pm-methodology-reference
        description: A reference capability tied to SDI as the post-podcast methodology read for her PM team before apidays NYC.
        location: file:///opt/naftiko/skills/sdi-pm-methodology-reference
        allowed-tools: example
        tools:
        - name: example
          description: A reference capability tied to SDI as the post-podcast methodology read for her PM team before apidays NYC.
          from:
            sourceNamespace: sdi-pm-methodology-reference-mcp
            action: example
---

A reference capability tied to SDI as the post-podcast methodology read for her PM team before apidays NYC. Continues the podcast narrative thread and arms her with a reusable internal artifact.

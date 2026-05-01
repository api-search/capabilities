---
categories: []
consumed_apis:
- groupe-bpce
description: A reference capability paired with SDI as the banking-API methodology paper.
layout: capability
naftiko_layer: proposed
naftiko_partner: Groupe BPCE
name: Groupe BPCE Bpce Sdi Banking Methodology Reference
operations: []
personas: []
provider_name: Groupe BPCE
provider_slug: groupe-bpce
search_terms:
- reference
- capability
- paired
- with
- banking
slug: bpce-sdi-banking-methodology-reference
source_filename: bpce-sdi-banking-methodology-reference.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Groupe BPCE Bpce Sdi Banking Methodology Reference
    description: A reference capability paired with SDI as the banking-API methodology paper.
    tags:
    - Groupe BPCE
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: groupe-bpce-env
    description: Groupe BPCE credentials.
    keys:
      GROUPE_BPCE_API_KEY: GROUPE_BPCE_API_KEY
  capability:
    consumes:
    - namespace: groupe-bpce
      type: http
      baseUri: https://api.groupe-bpce.com
      authentication:
        type: bearer
        token: '{{GROUPE_BPCE_API_KEY}}'
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
      namespace: bpce-sdi-banking-methodology-reference-rest
      description: REST API for Groupe BPCE Bpce Sdi Banking Methodology Reference.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: groupe-bpce.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: bpce-sdi-banking-methodology-reference-mcp
      description: MCP server exposing Groupe BPCE Bpce Sdi Banking Methodology Reference for AI agents.
      tools:
      - name: example
        description: A reference capability paired with SDI as the banking-API methodology paper.
        hints:
          readOnly: true
        call: groupe-bpce.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bpce-sdi-banking-methodology-reference-skills
      description: Agent Skill bundle for Groupe BPCE Bpce Sdi Banking Methodology Reference.
      skills:
      - name: bpce-sdi-banking-methodology-reference
        description: A reference capability paired with SDI as the banking-API methodology paper.
        location: file:///opt/naftiko/skills/bpce-sdi-banking-methodology-reference
        allowed-tools: example
        tools:
        - name: example
          description: A reference capability paired with SDI as the banking-API methodology paper.
          from:
            sourceNamespace: bpce-sdi-banking-methodology-reference-mcp
            action: example
---

A reference capability paired with SDI as the banking-API methodology paper. SDI as a methodology is more "open-able" than a product page for a cold institutional contact.

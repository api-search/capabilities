---
categories: []
consumed_apis:
- groupe-bpce
description: A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer.
layout: capability
naftiko_layer: proposed
naftiko_partner: Groupe BPCE
name: Groupe BPCE Bpce French Banking Sdi Capability
operations: []
personas: []
provider_name: Groupe BPCE
provider_slug: groupe-bpce
search_terms:
- french
- banking
- capability
- with
- methodology
slug: bpce-french-banking-sdi-capability
source_filename: bpce-french-banking-sdi-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Groupe BPCE Bpce French Banking Sdi Capability
    description: A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer.
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
      namespace: bpce-french-banking-sdi-capability-rest
      description: REST API for Groupe BPCE Bpce French Banking Sdi Capability.
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
      namespace: bpce-french-banking-sdi-capability-mcp
      description: MCP server exposing Groupe BPCE Bpce French Banking Sdi Capability for AI agents.
      tools:
      - name: example
        description: A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer.
        hints:
          readOnly: true
        call: groupe-bpce.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bpce-french-banking-sdi-capability-skills
      description: Agent Skill bundle for Groupe BPCE Bpce French Banking Sdi Capability.
      skills:
      - name: bpce-french-banking-sdi-capability
        description: A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer.
        location: file:///opt/naftiko/skills/bpce-french-banking-sdi-capability
        allowed-tools: example
        tools:
        - name: example
          description: A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer.
          from:
            sourceNamespace: bpce-french-banking-sdi-capability-mcp
            action: example
---

A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer. Cohort messaging with BNP Paribas; the French-banking thread benefits from a shared artifact pattern.

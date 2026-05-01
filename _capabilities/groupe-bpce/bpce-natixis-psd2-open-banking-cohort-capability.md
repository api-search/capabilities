---
categories: []
consumed_apis:
- groupe-bpce
description: A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging as the shared French-Tier-1-bank artifact pattern.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Groupe BPCE
name: Groupe BPCE Bpce Natixis Psd2 Open Banking Cohort Capability
operations: []
personas: []
provider_name: Groupe BPCE
provider_slug: groupe-bpce
search_terms:
- capability
- over
- bpce
- psd2
- natixis
slug: bpce-natixis-psd2-open-banking-cohort-capability
source_filename: bpce-natixis-psd2-open-banking-cohort-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Groupe BPCE Bpce Natixis Psd2 Open Banking Cohort Capability
    description: A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging as the shared French-Tier-1-bank artifact pattern.
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
      namespace: bpce-natixis-psd2-open-banking-cohort-capability-rest
      description: REST API for Groupe BPCE Bpce Natixis Psd2 Open Banking Cohort Capability.
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
      namespace: bpce-natixis-psd2-open-banking-cohort-capability-mcp
      description: MCP server exposing Groupe BPCE Bpce Natixis Psd2 Open Banking Cohort Capability for AI agents.
      tools:
      - name: example
        description: A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging as the shared French-Tier-1-bank artifact pattern.
        hints:
          readOnly: true
        call: groupe-bpce.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bpce-natixis-psd2-open-banking-cohort-capability-skills
      description: Agent Skill bundle for Groupe BPCE Bpce Natixis Psd2 Open Banking Cohort Capability.
      skills:
      - name: bpce-natixis-psd2-open-banking-cohort-capability
        description: A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging as the shared French-Tier-1-bank artifact pattern.
        location: file:///opt/naftiko/skills/bpce-natixis-psd2-open-banking-cohort-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging as the shared French-Tier-1-bank artifact pattern.
          from:
            sourceNamespace: bpce-natixis-psd2-open-banking-cohort-capability-mcp
            action: example
---

A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging as the shared French-Tier-1-bank artifact pattern. Cohort messaging with BNP needs a French-banking shared artifact that's BPCE-specific; PSD2 is the public surface that exists.

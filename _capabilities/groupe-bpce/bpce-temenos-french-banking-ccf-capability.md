---
categories: []
consumed_apis:
- groupe-bpce
description: A capability over a Temenos-shaped core banking surface (the French Tier-1 default) with NaftikoCapability CRD + ArgoCD + CCF-style continuous compliance.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Groupe BPCE
name: Groupe BPCE Bpce Temenos French Banking Ccf Capability
operations: []
personas: []
provider_name: Groupe BPCE
provider_slug: groupe-bpce
search_terms:
- capability
- over
- temenos
- shaped
- core
slug: bpce-temenos-french-banking-ccf-capability
source_filename: bpce-temenos-french-banking-ccf-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Groupe BPCE Bpce Temenos French Banking Ccf Capability
    description: A capability over a Temenos-shaped core banking surface (the French Tier-1 default) with NaftikoCapability CRD + ArgoCD + CCF-style continuous compliance.
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
      namespace: bpce-temenos-french-banking-ccf-capability-rest
      description: REST API for Groupe BPCE Bpce Temenos French Banking Ccf Capability.
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
      namespace: bpce-temenos-french-banking-ccf-capability-mcp
      description: MCP server exposing Groupe BPCE Bpce Temenos French Banking Ccf Capability for AI agents.
      tools:
      - name: example
        description: A capability over a Temenos-shaped core banking surface (the French Tier-1 default) with NaftikoCapability CRD + ArgoCD + CCF-style continuous compliance.
        hints:
          readOnly: true
        call: groupe-bpce.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bpce-temenos-french-banking-ccf-capability-skills
      description: Agent Skill bundle for Groupe BPCE Bpce Temenos French Banking Ccf Capability.
      skills:
      - name: bpce-temenos-french-banking-ccf-capability
        description: A capability over a Temenos-shaped core banking surface (the French Tier-1 default) with NaftikoCapability CRD + ArgoCD + CCF-style continuous compliance.
        location: file:///opt/naftiko/skills/bpce-temenos-french-banking-ccf-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over a Temenos-shaped core banking surface (the French Tier-1 default) with NaftikoCapability CRD + ArgoCD + CCF-style continuous compliance.
          from:
            sourceNamespace: bpce-temenos-french-banking-ccf-capability-mcp
            action: example
---

A capability over a Temenos-shaped core banking surface (the French Tier-1 default) with NaftikoCapability CRD + ArgoCD + CCF-style continuous compliance. French Tier-1 banks operationalize compliance through GitOps + CCF; Temenos is the realistic substrate.

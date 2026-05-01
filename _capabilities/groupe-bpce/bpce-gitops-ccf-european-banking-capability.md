---
categories: []
consumed_apis:
- groupe-bpce
description: A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team.
layout: capability
naftiko_layer: proposed
naftiko_partner: Groupe BPCE
name: Groupe BPCE Bpce Gitops Ccf European Banking Capability
operations: []
personas: []
provider_name: Groupe BPCE
provider_slug: groupe-bpce
search_terms:
- capability
- using
- naftikocapability
- argocd
- gitops
slug: bpce-gitops-ccf-european-banking-capability
source_filename: bpce-gitops-ccf-european-banking-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Groupe BPCE Bpce Gitops Ccf European Banking Capability
    description: A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team.
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
      namespace: bpce-gitops-ccf-european-banking-capability-rest
      description: REST API for Groupe BPCE Bpce Gitops Ccf European Banking Capability.
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
      namespace: bpce-gitops-ccf-european-banking-capability-mcp
      description: MCP server exposing Groupe BPCE Bpce Gitops Ccf European Banking Capability for AI agents.
      tools:
      - name: example
        description: A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team.
        hints:
          readOnly: true
        call: groupe-bpce.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bpce-gitops-ccf-european-banking-capability-skills
      description: Agent Skill bundle for Groupe BPCE Bpce Gitops Ccf European Banking Capability.
      skills:
      - name: bpce-gitops-ccf-european-banking-capability
        description: A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team.
        location: file:///opt/naftiko/skills/bpce-gitops-ccf-european-banking-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team.
          from:
            sourceNamespace: bpce-gitops-ccf-european-banking-capability-mcp
            action: example
---

A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team. That stack maps directly to how French Tier-1 banks operationalize compliance.

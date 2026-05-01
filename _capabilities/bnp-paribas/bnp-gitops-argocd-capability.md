---
categories: []
consumed_apis:
- bnp-paribas
description: A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language.
layout: capability
naftiko_layer: proposed
naftiko_partner: Cedric MONIER
name: BNP Paribas Bnp Gitops Argocd Capability
operations: []
personas: []
provider_name: BNP Paribas
provider_slug: bnp-paribas
search_terms:
- capability
- deployed
- gitops
- argocd
- flux
slug: bnp-gitops-argocd-capability
source_filename: bnp-gitops-argocd-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: BNP Paribas Bnp Gitops Argocd Capability
    description: A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language.
    tags:
    - BNP Paribas
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: bnp-paribas-env
    description: BNP Paribas credentials.
    keys:
      BNP_PARIBAS_API_KEY: BNP_PARIBAS_API_KEY
  capability:
    consumes:
    - namespace: bnp-paribas
      type: http
      baseUri: https://api.bnp-paribas.com
      authentication:
        type: bearer
        token: '{{BNP_PARIBAS_API_KEY}}'
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
      namespace: bnp-gitops-argocd-capability-rest
      description: REST API for BNP Paribas Bnp Gitops Argocd Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: bnp-paribas.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: bnp-gitops-argocd-capability-mcp
      description: MCP server exposing BNP Paribas Bnp Gitops Argocd Capability for AI agents.
      tools:
      - name: example
        description: A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language.
        hints:
          readOnly: true
        call: bnp-paribas.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: bnp-gitops-argocd-capability-skills
      description: Agent Skill bundle for BNP Paribas Bnp Gitops Argocd Capability.
      skills:
      - name: bnp-gitops-argocd-capability
        description: A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language.
        location: file:///opt/naftiko/skills/bnp-gitops-argocd-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language.
          from:
            sourceNamespace: bnp-gitops-argocd-capability-mcp
            action: example
---

A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language. French banking + API-First = ArgoCD/GitOps + regulatory compliance is the door-opener.

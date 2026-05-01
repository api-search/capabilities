---
categories: []
consumed_apis:
- telstra
description: A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Ranjaka De Mel
name: Telstra Argocd Gitops Naftikocapability Runbook
operations: []
personas: []
provider_name: Telstra
provider_slug: telstra
search_terms:
- capability
- deployed
- naftikocapability
- argocd
- gitops
slug: argocd-gitops-naftikocapability-runbook
source_filename: argocd-gitops-naftikocapability-runbook.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Telstra Argocd Gitops Naftikocapability Runbook
    description: A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact.
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
      namespace: argocd-gitops-naftikocapability-runbook-rest
      description: REST API for Telstra Argocd Gitops Naftikocapability Runbook.
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
      namespace: argocd-gitops-naftikocapability-runbook-mcp
      description: MCP server exposing Telstra Argocd Gitops Naftikocapability Runbook for AI agents.
      tools:
      - name: example
        description: A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact.
        hints:
          readOnly: true
        call: telstra.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: argocd-gitops-naftikocapability-runbook-skills
      description: Agent Skill bundle for Telstra Argocd Gitops Naftikocapability Runbook.
      skills:
      - name: argocd-gitops-naftikocapability-runbook
        description: A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact.
        location: file:///opt/naftiko/skills/argocd-gitops-naftikocapability-runbook
        allowed-tools: example
        tools:
        - name: example
          description: A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact.
          from:
            sourceNamespace: argocd-gitops-naftikocapability-runbook-mcp
            action: example
---

A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact. His title is DevOps / Platform Engineer; ArgoCD + CRD is the native-language artifact.

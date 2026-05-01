---
categories: []
consumed_apis:
- telstra
description: A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language.
layout: capability
naftiko_layer: proposed
naftiko_partner: Ranjaka De Mel
name: Telstra K8s Gitops Capability
operations: []
personas: []
provider_name: Telstra
provider_slug: telstra
search_terms:
- capability
- deployed
- naftiko
- operator
- kubernetes
slug: k8s-gitops-capability
source_filename: k8s-gitops-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Telstra K8s Gitops Capability
    description: A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language.
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
      namespace: k8s-gitops-capability-rest
      description: REST API for Telstra K8s Gitops Capability.
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
      namespace: k8s-gitops-capability-mcp
      description: MCP server exposing Telstra K8s Gitops Capability for AI agents.
      tools:
      - name: example
        description: A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language.
        hints:
          readOnly: true
        call: telstra.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: k8s-gitops-capability-skills
      description: Agent Skill bundle for Telstra K8s Gitops Capability.
      skills:
      - name: k8s-gitops-capability
        description: A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language.
        location: file:///opt/naftiko/skills/k8s-gitops-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language.
          from:
            sourceNamespace: k8s-gitops-capability-mcp
            action: example
---

A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language. His title is DevOps / Platform Engineer; the K8s/GitOps surface is what his role evaluates first.

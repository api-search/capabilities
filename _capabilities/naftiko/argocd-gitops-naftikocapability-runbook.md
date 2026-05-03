---
categories: []
consumed_apis: []
description: A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact.
layout: capability
name: Argocd Gitops Naftikocapability Runbook
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- example
- mcp
- ai
- a capability deployed via naftikocapability crd + argocd gitops with a fully-loaded runbook — the un-sticker artifact.
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: argocd-gitops-naftikocapability-runbook
source_filename: argocd-gitops-naftikocapability-runbook.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Argocd Gitops Naftikocapability Runbook\n  description: A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: argocd-gitops-naftikocapability-runbook-rest\n    description: REST API for Argocd Gitops Naftikocapability Runbook.\n    resources:\n    - name: example\n      path: /example\n      operations:\n\
  \      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: argocd-gitops-naftikocapability-runbook-mcp\n    description: MCP server exposing Argocd Gitops Naftikocapability Runbook for AI agents.\n    tools:\n    - name: example\n      description: A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: argocd-gitops-naftikocapability-runbook-skills\n    description: Agent Skill bundle for Argocd Gitops Naftikocapability Runbook.\n    skills:\n    - name: argocd-gitops-naftikocapability-runbook\n      description: A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact.\n      location: file:///opt/naftiko/skills/argocd-gitops-naftikocapability-runbook\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact.\n        from:\n          sourceNamespace: argocd-gitops-naftikocapability-runbook-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/argocd-gitops-naftikocapability-runbook.yaml
tags:
- Naftiko
tools:
- description: A capability deployed via NaftikoCapability CRD + ArgoCD GitOps with a fully-loaded runbook — the un-sticker artifact.
  hints:
    readOnly: true
  name: example
---

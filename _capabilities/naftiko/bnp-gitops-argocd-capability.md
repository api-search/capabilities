---
categories: []
consumed_apis: []
description: A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language.
layout: capability
name: Bnp Gitops Argocd Capability
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
- a capability deployed via gitops (argocd/flux) with the naftikocapability crd, framed for bnp's argocd + regulatory-compliance language.
- ai
- mcp
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: bnp-gitops-argocd-capability
source_filename: bnp-gitops-argocd-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bnp Gitops Argocd Capability\n  description: A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bnp-gitops-argocd-capability-rest\n    description: REST API for Bnp Gitops Argocd Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method:\
  \ GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bnp-gitops-argocd-capability-mcp\n    description: MCP server exposing Bnp Gitops Argocd Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bnp-gitops-argocd-capability-skills\n    description: Agent Skill bundle for Bnp Gitops Argocd Capability.\n    skills:\n    - name: bnp-gitops-argocd-capability\n      description: A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language.\n      location: file:///opt/naftiko/skills/bnp-gitops-argocd-capability\n      allowed-tools: example\n\
  \      tools:\n      - name: example\n        description: A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language.\n        from:\n          sourceNamespace: bnp-gitops-argocd-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bnp-gitops-argocd-capability.yaml
tags:
- Naftiko
tools:
- description: A capability deployed via GitOps (ArgoCD/Flux) with the NaftikoCapability CRD, framed for BNP's ArgoCD + regulatory-compliance language.
  hints:
    readOnly: true
  name: example
---

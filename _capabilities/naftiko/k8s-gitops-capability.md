---
categories: []
consumed_apis: []
description: A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language.
layout: capability
name: K8S Gitops Capability
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
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- a capability deployed via naftiko operator for kubernetes + naftikocapability crd + gitops (argocd/flux) — devops/platform engineer's native language.
- governance
slug: k8s-gitops-capability
source_filename: k8s-gitops-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: K8s Gitops Capability\n  description: A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: k8s-gitops-capability-rest\n    description: REST API for K8s Gitops Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n\
  \        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: k8s-gitops-capability-mcp\n    description: MCP server exposing K8s Gitops Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: k8s-gitops-capability-skills\n    description: Agent Skill bundle for K8s Gitops Capability.\n    skills:\n    - name: k8s-gitops-capability\n      description: A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language.\n      location: file:///opt/naftiko/skills/k8s-gitops-capability\n      allowed-tools: example\n      tools:\n \
  \     - name: example\n        description: A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language.\n        from:\n          sourceNamespace: k8s-gitops-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/k8s-gitops-capability.yaml
tags:
- Naftiko
tools:
- description: A capability deployed via Naftiko Operator for Kubernetes + NaftikoCapability CRD + GitOps (ArgoCD/Flux) — DevOps/Platform Engineer's native language.
  hints:
    readOnly: true
  name: example
---

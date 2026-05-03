---
categories: []
consumed_apis: []
description: A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team.
layout: capability
name: Gitops Ccf European Banking Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- example op
- example
- api integration
- a capability using naftikocapability crd + argocd gitops + continuous compliance (ccf-style) for the european-banking platform team.
- naftiko
- governance
- mcp
- capabilities
- ai
slug: gitops-ccf-european-banking-capability
source_filename: gitops-ccf-european-banking-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Gitops Ccf European Banking Capability\n  description: A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: gitops-ccf-european-banking-capability-rest\n    description: REST API for Gitops Ccf European Banking Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n\
  \      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: gitops-ccf-european-banking-capability-mcp\n    description: MCP server exposing Gitops Ccf European Banking Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: gitops-ccf-european-banking-capability-skills\n    description: Agent Skill bundle for Gitops Ccf European Banking Capability.\n    skills:\n    - name: gitops-ccf-european-banking-capability\n      description: A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team.\n      location: file:///opt/naftiko/skills/gitops-ccf-european-banking-capability\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team.\n        from:\n          sourceNamespace: gitops-ccf-european-banking-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/gitops-ccf-european-banking-capability.yaml
tags:
- Naftiko
tools:
- description: A capability using NaftikoCapability CRD + ArgoCD GitOps + Continuous Compliance (CCF-style) for the European-banking platform team.
  hints:
    readOnly: true
  name: example
---

---
categories: []
consumed_apis: []
description: A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language.
layout: capability
name: Bnp Temenos Transact Core Banking Governance Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- a capability over temenos transact (the core banking system) with full governance ruleset + argocd gitops reconciliation, framed for bnp's regulatory-compliance language.
- spec-driven integration
- example op
- example
- api integration
- naftiko
- governance
- mcp
- capabilities
- ai
slug: bnp-temenos-transact-core-banking-governance-capability
source_filename: bnp-temenos-transact-core-banking-governance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bnp Temenos Transact Core Banking Governance Capability\n  description: A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bnp-temenos-transact-core-banking-governance-capability-rest\n    description: REST API for Bnp Temenos Transact Core Banking Governance\
  \ Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bnp-temenos-transact-core-banking-governance-capability-mcp\n    description: MCP server exposing Bnp Temenos Transact Core Banking Governance Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bnp-temenos-transact-core-banking-governance-capability-skills\n    description: Agent Skill bundle for Bnp Temenos Transact Core Banking Governance Capability.\n    skills:\n    - name: bnp-temenos-transact-core-banking-governance-capability\n\
  \      description: A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language.\n      location: file:///opt/naftiko/skills/bnp-temenos-transact-core-banking-governance-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language.\n        from:\n          sourceNamespace: bnp-temenos-transact-core-banking-governance-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bnp-temenos-transact-core-banking-governance-capability.yaml
tags:
- Naftiko
tools:
- description: A capability over Temenos Transact (the core banking system) with full governance ruleset + ArgoCD GitOps reconciliation, framed for BNP's regulatory-compliance language.
  hints:
    readOnly: true
  name: example
---

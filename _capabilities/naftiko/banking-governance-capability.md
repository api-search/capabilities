---
categories: []
consumed_apis: []
description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
layout: capability
name: Banking Governance Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- ai
- api integration
- spec-driven integration
- capabilities
- naftiko
- 'a capability built specifically to show banking-grade governance: labels on info, tags on consumes (data sensitivity, billing), kyverno admission control, nist/soc2/pci/gdpr continuous compliance.'
- mcp
- example op
- example
- governance
slug: banking-governance-capability
source_filename: banking-governance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Banking Governance Capability\n  description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: banking-governance-capability-rest\n    description: REST API for Banking Governance Capability.\n    resources:\n    - name:\
  \ example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: banking-governance-capability-mcp\n    description: MCP server exposing Banking Governance Capability for AI agents.\n    tools:\n    - name: example\n      description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: banking-governance-capability-skills\n    description: Agent Skill bundle for Banking Governance Capability.\n    skills:\n    - name: banking-governance-capability\n      description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data\
  \ sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'\n      location: file:///opt/naftiko/skills/banking-governance-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'\n        from:\n          sourceNamespace: banking-governance-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/banking-governance-capability.yaml
tags:
- Naftiko
tools:
- description: 'A capability built specifically to show banking-grade governance: labels on info, tags on Consumes (data sensitivity, billing), Kyverno admission control, NIST/SOC2/PCI/GDPR continuous compliance.'
  hints:
    readOnly: true
  name: example
---

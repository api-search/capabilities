---
categories: []
consumed_apis: []
description: A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for audit + advisory practice.
layout: capability
name: Ccf Continuous Compliance Capability
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
- mcp
- example op
- example
- a capability that activates compliance frameworks (nist/soc2/pci/gdpr) + continuous compliance (ccf-style), framed for audit + advisory practice.
- governance
slug: ccf-continuous-compliance-capability
source_filename: ccf-continuous-compliance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Ccf Continuous Compliance Capability\n  description: A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for audit + advisory practice.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: ccf-continuous-compliance-capability-rest\n    description: REST API for Ccf Continuous Compliance Capability.\n    resources:\n    - name: example\n      path: /example\n\
  \      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: ccf-continuous-compliance-capability-mcp\n    description: MCP server exposing Ccf Continuous Compliance Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for audit + advisory practice.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: ccf-continuous-compliance-capability-skills\n    description: Agent Skill bundle for Ccf Continuous Compliance Capability.\n    skills:\n    - name: ccf-continuous-compliance-capability\n      description: A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for audit + advisory practice.\n      location:\
  \ file:///opt/naftiko/skills/ccf-continuous-compliance-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for audit + advisory practice.\n        from:\n          sourceNamespace: ccf-continuous-compliance-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/ccf-continuous-compliance-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that activates Compliance Frameworks (NIST/SOC2/PCI/GDPR) + Continuous Compliance (CCF-style), framed for audit + advisory practice.
  hints:
    readOnly: true
  name: example
---

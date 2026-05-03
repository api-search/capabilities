---
categories: []
consumed_apis: []
description: A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance.
layout: capability
name: Compliance Payer Grade Capability
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
- governance
- a capability activating compliance frameworks (nist/soc2/gdpr, hipaa-adjacent) + rbac + audit trails + continuous compliance.
slug: compliance-payer-grade-capability
source_filename: compliance-payer-grade-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Compliance Payer Grade Capability\n  description: A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: compliance-payer-grade-capability-rest\n    description: REST API for Compliance Payer Grade Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method:\
  \ GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: compliance-payer-grade-capability-mcp\n    description: MCP server exposing Compliance Payer Grade Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: compliance-payer-grade-capability-skills\n    description: Agent Skill bundle for Compliance Payer Grade Capability.\n    skills:\n    - name: compliance-payer-grade-capability\n      description: A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance.\n      location: file:///opt/naftiko/skills/compliance-payer-grade-capability\n      allowed-tools:\
  \ example\n      tools:\n      - name: example\n        description: A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance.\n        from:\n          sourceNamespace: compliance-payer-grade-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/compliance-payer-grade-capability.yaml
tags:
- Naftiko
tools:
- description: A capability activating Compliance Frameworks (NIST/SOC2/GDPR, HIPAA-adjacent) + RBAC + audit trails + continuous compliance.
  hints:
    readOnly: true
  name: example
---

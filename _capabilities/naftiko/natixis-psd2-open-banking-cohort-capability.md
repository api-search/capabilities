---
categories: []
consumed_apis: []
description: A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging as the shared French-Tier-1-bank artifact pattern.
layout: capability
name: Natixis Psd2 Open Banking Cohort Capability
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
- naftiko
- governance
- mcp
- a capability over bpce's psd2 / natixis open api portal endpoints, paired with bnp-cohort messaging as the shared french-tier-1-bank artifact pattern.
- capabilities
- ai
slug: natixis-psd2-open-banking-cohort-capability
source_filename: natixis-psd2-open-banking-cohort-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Natixis Psd2 Open Banking Cohort Capability\n  description: A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging as the shared French-Tier-1-bank artifact pattern.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: natixis-psd2-open-banking-cohort-capability-rest\n    description: REST API for Natixis Psd2 Open Banking Cohort Capability.\n    resources:\n    - name: example\n\
  \      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: natixis-psd2-open-banking-cohort-capability-mcp\n    description: MCP server exposing Natixis Psd2 Open Banking Cohort Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging as the shared French-Tier-1-bank artifact pattern.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: natixis-psd2-open-banking-cohort-capability-skills\n    description: Agent Skill bundle for Natixis Psd2 Open Banking Cohort Capability.\n    skills:\n    - name: natixis-psd2-open-banking-cohort-capability\n      description: A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging\
  \ as the shared French-Tier-1-bank artifact pattern.\n      location: file:///opt/naftiko/skills/natixis-psd2-open-banking-cohort-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging as the shared French-Tier-1-bank artifact pattern.\n        from:\n          sourceNamespace: natixis-psd2-open-banking-cohort-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/natixis-psd2-open-banking-cohort-capability.yaml
tags:
- Naftiko
tools:
- description: A capability over BPCE's PSD2 / Natixis Open API portal endpoints, paired with BNP-cohort messaging as the shared French-Tier-1-bank artifact pattern.
  hints:
    readOnly: true
  name: example
---

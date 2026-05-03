---
categories: []
consumed_apis: []
description: A capability whose governance ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for automation-of-governance thesis.
layout: capability
name: Governance Automation Runtime Capability
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
- a capability whose governance ruleset (spectral rules, kyverno admission control, naftikogovernancefactretriever, naftikoscorecardcard) is wired in as the runtime for automation-of-governance thesis.
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: governance-automation-runtime-capability
source_filename: governance-automation-runtime-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Governance Automation Runtime Capability\n  description: A capability whose governance ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for automation-of-governance thesis.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: governance-automation-runtime-capability-rest\n    description: REST API for Governance Automation Runtime Capability.\n\
  \    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: governance-automation-runtime-capability-mcp\n    description: MCP server exposing Governance Automation Runtime Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability whose governance ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for automation-of-governance thesis.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: governance-automation-runtime-capability-skills\n    description: Agent Skill bundle for Governance Automation Runtime Capability.\n    skills:\n    - name: governance-automation-runtime-capability\n      description: A capability whose governance\
  \ ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for automation-of-governance thesis.\n      location: file:///opt/naftiko/skills/governance-automation-runtime-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability whose governance ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for automation-of-governance thesis.\n        from:\n          sourceNamespace: governance-automation-runtime-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/governance-automation-runtime-capability.yaml
tags:
- Naftiko
tools:
- description: A capability whose governance ruleset (Spectral rules, Kyverno admission control, NaftikoGovernanceFactRetriever, NaftikoScorecardCard) is wired in as the runtime for automation-of-governance thesis.
  hints:
    readOnly: true
  name: example
---

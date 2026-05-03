---
categories: []
consumed_apis: []
description: A capability where the Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story.
layout: capability
name: Devsecops Shift Left Governance Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- a capability where the naftiko spectral ruleset + blocking rules (auth required, https only, destructive-ops gate) + pii surface detection are wired in as the shift-left governance story.
- spec-driven integration
- example op
- example
- api integration
- naftiko
- governance
- mcp
- capabilities
- ai
slug: devsecops-shift-left-governance-capability
source_filename: devsecops-shift-left-governance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Devsecops Shift Left Governance Capability\n  description: A capability where the Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: devsecops-shift-left-governance-capability-rest\n    description: REST API for Devsecops Shift Left Governance Capability.\n\
  \    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: devsecops-shift-left-governance-capability-mcp\n    description: MCP server exposing Devsecops Shift Left Governance Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability where the Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: devsecops-shift-left-governance-capability-skills\n    description: Agent Skill bundle for Devsecops Shift Left Governance Capability.\n    skills:\n    - name: devsecops-shift-left-governance-capability\n      description: A capability where the\
  \ Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story.\n      location: file:///opt/naftiko/skills/devsecops-shift-left-governance-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability where the Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story.\n        from:\n          sourceNamespace: devsecops-shift-left-governance-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/devsecops-shift-left-governance-capability.yaml
tags:
- Naftiko
tools:
- description: A capability where the Naftiko Spectral ruleset + blocking rules (auth required, HTTPS only, destructive-ops gate) + PII surface detection are wired in as the shift-left governance story.
  hints:
    readOnly: true
  name: example
---

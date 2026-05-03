---
categories: []
consumed_apis: []
description: A capability that consumes GitHub-scan webhook + GitHub Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant.
layout: capability
name: Github Actions Secret Scan Capability
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
- a capability that consumes github-scan webhook + github actions api and exposes a single mcp tool returning shaped per-repo secret findings + remediation suggestions for an ai security assistant.
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: github-actions-secret-scan-capability
source_filename: github-actions-secret-scan-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Github Actions Secret Scan Capability\n  description: A capability that consumes GitHub-scan webhook + GitHub Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: github-actions-secret-scan-capability-rest\n    description: REST API for Github Actions Secret Scan Capability.\n    resources:\n\
  \    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: github-actions-secret-scan-capability-mcp\n    description: MCP server exposing Github Actions Secret Scan Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that consumes GitHub-scan webhook + GitHub Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: github-actions-secret-scan-capability-skills\n    description: Agent Skill bundle for Github Actions Secret Scan Capability.\n    skills:\n    - name: github-actions-secret-scan-capability\n      description: A capability that consumes GitHub-scan webhook + GitHub\
  \ Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant.\n      location: file:///opt/naftiko/skills/github-actions-secret-scan-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that consumes GitHub-scan webhook + GitHub Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant.\n        from:\n          sourceNamespace: github-actions-secret-scan-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/github-actions-secret-scan-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that consumes GitHub-scan webhook + GitHub Actions API and exposes a single MCP tool returning shaped per-repo secret findings + remediation suggestions for an AI security assistant.
  hints:
    readOnly: true
  name: example
---

---
categories: []
consumed_apis: []
description: A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime.
layout: capability
name: Cli Only Runnable Capability
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
- governance
- example op
- mcp
- example
- a capability designed to be exercised entirely via the naftiko cli (no docker daemon), demonstrating local validation, mcp test, and lint without any container runtime.
slug: cli-only-runnable-capability
source_filename: cli-only-runnable-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Cli Only Runnable Capability\n  description: A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: cli-only-runnable-capability-rest\n    description: REST API for Cli Only Runnable Capability.\n    resources:\n    - name: example\n      path: /example\n\
  \      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: cli-only-runnable-capability-mcp\n    description: MCP server exposing Cli Only Runnable Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: cli-only-runnable-capability-skills\n    description: Agent Skill bundle for Cli Only Runnable Capability.\n    skills:\n    - name: cli-only-runnable-capability\n      description: A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime.\n\
  \      location: file:///opt/naftiko/skills/cli-only-runnable-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime.\n        from:\n          sourceNamespace: cli-only-runnable-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/cli-only-runnable-capability.yaml
tags:
- Naftiko
tools:
- description: A capability designed to be exercised entirely via the Naftiko CLI (no Docker daemon), demonstrating local validation, MCP test, and lint without any container runtime.
  hints:
    readOnly: true
  name: example
---

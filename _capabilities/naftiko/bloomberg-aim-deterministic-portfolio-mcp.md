---
categories: []
consumed_apis: []
description: A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech opening artifact.
layout: capability
name: Bloomberg Aim Deterministic Portfolio Mcp
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
- a capability over bloomberg aim portfolio positions exposing typed, deterministic mcp reads for the ai-data-enterprise-tech opening artifact.
- example op
- governance
slug: bloomberg-aim-deterministic-portfolio-mcp
source_filename: bloomberg-aim-deterministic-portfolio-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bloomberg Aim Deterministic Portfolio Mcp\n  description: A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech opening artifact.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bloomberg-aim-deterministic-portfolio-mcp-rest\n    description: REST API for Bloomberg Aim Deterministic Portfolio Mcp.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bloomberg-aim-deterministic-portfolio-mcp-mcp\n    description: MCP server exposing Bloomberg Aim Deterministic Portfolio Mcp for AI agents.\n    tools:\n    - name: example\n      description: A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech opening artifact.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bloomberg-aim-deterministic-portfolio-mcp-skills\n    description: Agent Skill bundle for Bloomberg Aim Deterministic Portfolio Mcp.\n    skills:\n    - name: bloomberg-aim-deterministic-portfolio-mcp\n      description: A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech\
  \ opening artifact.\n      location: file:///opt/naftiko/skills/bloomberg-aim-deterministic-portfolio-mcp\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech opening artifact.\n        from:\n          sourceNamespace: bloomberg-aim-deterministic-portfolio-mcp-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bloomberg-aim-deterministic-portfolio-mcp.yaml
tags:
- Naftiko
tools:
- description: A capability over Bloomberg AIM portfolio positions exposing typed, deterministic MCP reads for the AI-Data-Enterprise-Tech opening artifact.
  hints:
    readOnly: true
  name: example
---

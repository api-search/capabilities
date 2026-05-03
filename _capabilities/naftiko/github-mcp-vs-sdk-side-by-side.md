---
categories: []
consumed_apis: []
description: A capability that wraps the GitHub REST API as both a generated SDK call path AND a Naftiko-exposed MCP tool over the same operation, used as the visual proof of "Capabilities Are the New Abstraction Layer."
layout: capability
name: Github Mcp Vs Sdk Side By Side
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
- capabilities
- governance
- mcp
- a capability that wraps the github rest api as both a generated sdk call path and a naftiko-exposed mcp tool over the same operation, used as the visual proof of "capabilities are the new abstraction layer."
- ai
slug: github-mcp-vs-sdk-side-by-side
source_filename: github-mcp-vs-sdk-side-by-side.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Github Mcp Vs Sdk Side By Side\n  description: A capability that wraps the GitHub REST API as both a generated SDK call path AND a Naftiko-exposed MCP tool over the same operation, used as the visual proof of \"Capabilities Are the New Abstraction Layer.\"\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: github-mcp-vs-sdk-side-by-side-rest\n    description: REST API for Github Mcp Vs Sdk Side By Side.\n    resources:\n\
  \    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: github-mcp-vs-sdk-side-by-side-mcp\n    description: MCP server exposing Github Mcp Vs Sdk Side By Side for AI agents.\n    tools:\n    - name: example\n      description: A capability that wraps the GitHub REST API as both a generated SDK call path AND a Naftiko-exposed MCP tool over the same operation, used as the visual proof of \"Capabilities Are the New Abstraction Layer.\"\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: github-mcp-vs-sdk-side-by-side-skills\n    description: Agent Skill bundle for Github Mcp Vs Sdk Side By Side.\n    skills:\n    - name: github-mcp-vs-sdk-side-by-side\n      description: A capability that wraps the GitHub REST API as both a generated SDK call path\
  \ AND a Naftiko-exposed MCP tool over the same operation, used as the visual proof of \"Capabilities Are the New Abstraction Layer.\"\n      location: file:///opt/naftiko/skills/github-mcp-vs-sdk-side-by-side\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that wraps the GitHub REST API as both a generated SDK call path AND a Naftiko-exposed MCP tool over the same operation, used as the visual proof of \"Capabilities Are the New Abstraction Layer.\"\n        from:\n          sourceNamespace: github-mcp-vs-sdk-side-by-side-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/github-mcp-vs-sdk-side-by-side.yaml
tags:
- Naftiko
tools:
- description: A capability that wraps the GitHub REST API as both a generated SDK call path AND a Naftiko-exposed MCP tool over the same operation, used as the visual proof of "Capabilities Are the New Abstraction Layer."
  hints:
    readOnly: true
  name: example
---

---
categories: []
consumed_apis: []
description: A capability that joins News headlines + Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant.
layout: capability
name: News Instant Message Context Mcp
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
- a capability that joins news headlines + instant messaging (ib) thread context into one mcp-callable agent tool for an internal trading-floor assistant.
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: news-instant-message-context-mcp
source_filename: news-instant-message-context-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: News Instant Message Context Mcp\n  description: A capability that joins News headlines + Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: news-instant-message-context-mcp-rest\n    description: REST API for News Instant Message Context Mcp.\n    resources:\n    - name: example\n      path: /example\n    \
  \  operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: news-instant-message-context-mcp-mcp\n    description: MCP server exposing News Instant Message Context Mcp for AI agents.\n    tools:\n    - name: example\n      description: A capability that joins News headlines + Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: news-instant-message-context-mcp-skills\n    description: Agent Skill bundle for News Instant Message Context Mcp.\n    skills:\n    - name: news-instant-message-context-mcp\n      description: A capability that joins News headlines + Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant.\n      location: file:///opt/naftiko/skills/news-instant-message-context-mcp\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that joins News headlines + Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant.\n        from:\n          sourceNamespace: news-instant-message-context-mcp-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/news-instant-message-context-mcp.yaml
tags:
- Naftiko
tools:
- description: A capability that joins News headlines + Instant Messaging (IB) thread context into one MCP-callable agent tool for an internal trading-floor assistant.
  hints:
    readOnly: true
  name: example
---

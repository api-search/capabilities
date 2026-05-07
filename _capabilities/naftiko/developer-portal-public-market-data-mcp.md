---
categories: []
consumed_apis: []
description: A capability over a public market-data API exposed through a developer portal as MCP, so external developers can pull quotes via agents.
layout: capability
name: Developer Portal Public Market Data Mcp
operations:
- description: ''
  method: GET
  name: get-quote
  path: /quote/{{symbol}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- market data
- get quote
- ai
- capabilities
- spec-driven integration
- api integration
- developer portal
- mcp
- naftiko
slug: developer-portal-public-market-data-mcp
source_filename: developer-portal-public-market-data-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Developer Portal Public Market Data Mcp\n  description: A capability over a public market-data API exposed through a developer portal as MCP, so external developers can pull quotes via agents.\n  tags: [Naftiko, Market Data, Developer Portal]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: alphavantage-env\n  keys: {ALPHAVANTAGE_API_KEY: ALPHAVANTAGE_API_KEY}\ncapability:\n  consumes:\n  - namespace: alphavantage\n    type: http\n    baseUri: https://www.alphavantage.co\n    resources:\n    - name: quote\n      path: /query\n      operations:\n      - {name: get-quote, method: GET, inputParameters: [{name: function, in: query}, {name: symbol, in: query}, {name: apikey, in: query}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: developer-portal-public-market-data-mcp-rest\n    description: REST surface for public market data.\n    resources:\n    - {name: quote, path: '/quote/{{symbol}}',\
  \ operations: [{method: GET, name: get-quote, inputParameters: [{name: symbol, in: path, type: string}], call: alphavantage.get-quote}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: developer-portal-public-market-data-mcp-mcp\n    description: MCP for public market data.\n    tools:\n    - name: get-quote\n      hints: {readOnly: true}\n      inputParameters: [{name: symbol, type: string, required: true}]\n      call: alphavantage.get-quote\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: developer-portal-public-market-data-mcp-skills\n    description: Skill for public market data.\n    skills:\n    - name: developer-portal-public-market-data-mcp\n      description: Public market-data MCP via developer portal.\n      location: file:///opt/naftiko/skills/developer-portal-public-market-data-mcp\n      allowed-tools: get-quote\n      tools:\n      - {name: get-quote, from: {sourceNamespace: developer-portal-public-market-data-mcp-mcp, action:\
  \ get-quote}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/developer-portal-public-market-data-mcp.yaml
tags:
- Naftiko
- Market Data
- Developer Portal
tools:
- description: ''
  hints:
    readOnly: true
  name: get-quote
---

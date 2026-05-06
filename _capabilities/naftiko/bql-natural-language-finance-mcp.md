---
categories: []
consumed_apis: []
description: A capability over Bloomberg Query Language (BQL) that lets agents issue natural-language finance queries; the capability translates to BQL and returns shaped results.
layout: capability
name: Bql Natural Language Finance Mcp
operations:
- description: Translate a natural-language finance question to BQL and return shaped results.
  method: POST
  name: ask-finance
  path: /ask
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- finance
- ask a finance question in plain english; returns shaped bql results.
- bloomberg
- api integration
- governance
- spec-driven integration
- ai
- mcp
- bql
- capabilities
- ask finance
- translate a natural-language finance question to bql and return shaped results.
slug: bql-natural-language-finance-mcp
source_filename: bql-natural-language-finance-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bql Natural Language Finance Mcp\n  description: A capability over Bloomberg Query Language (BQL) that lets agents issue natural-language finance queries; the capability translates to BQL and returns shaped results.\n  tags: [Naftiko, Bloomberg, BQL, Finance]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: bloomberg-env\n  keys: {BLOOMBERG_TOKEN: BLOOMBERG_TOKEN}\ncapability:\n  consumes:\n  - namespace: bql\n    type: http\n    baseUri: https://api.bloomberg.com\n    authentication: {type: bearer, token: '{{BLOOMBERG_TOKEN}}'}\n    resources:\n    - {name: bql, path: /eap/bql/v1/query, operations: [{name: run-bql-query, method: POST, description: Run a BQL expression.}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bql-natural-language-finance-mcp-rest\n    description: REST surface for natural-language finance queries.\n    resources:\n    - {name: ask, path: /ask, operations:\
  \ [{method: POST, name: ask-finance, description: Translate a natural-language finance question to BQL and return shaped results., call: bql.run-bql-query}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bql-natural-language-finance-mcp-mcp\n    description: MCP for NL→BQL queries.\n    tools:\n    - {name: ask-finance, description: Ask a finance question in plain English; returns shaped BQL results., call: bql.run-bql-query}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bql-natural-language-finance-mcp-skills\n    description: Skill for NL→BQL.\n    skills:\n    - name: bql-natural-language-finance-mcp\n      description: NL→BQL finance queries.\n      location: file:///opt/naftiko/skills/bql-natural-language-finance-mcp\n      allowed-tools: ask-finance\n      tools:\n      - {name: ask-finance, from: {sourceNamespace: bql-natural-language-finance-mcp-mcp, action: ask-finance}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bql-natural-language-finance-mcp.yaml
tags:
- Naftiko
- Bloomberg
- BQL
- Finance
tools:
- description: Ask a finance question in plain English; returns shaped BQL results.
  hints: {}
  name: ask-finance
---

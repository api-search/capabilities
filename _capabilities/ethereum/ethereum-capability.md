---
categories: []
consumed_apis: []
description: The Ethereum JSON-RPC API is the standard interface for interacting with Ethereum nodes. It provides methods for querying blockchain state, sending transactions, managing accounts, and interacting with smart contracts. All methods follow the JSON-RPC 2.0 specification over HTTP or WebSocket.
layout: capability
name: Ethereum JSON-RPC API
operations:
- description: Ethereum JSON-RPC endpoint
  method: POST
  name: jsonrpccall
  path: /
personas: []
provider_name: Ethereum
provider_slug: ethereum
search_terms:
- json-rpc
- defi
- ethereum
- web3
- ethereum json-rpc endpoint
- blockchain
- api
- jsonrpccall
- smart contracts
slug: ethereum-capability
source_filename: ethereum-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ethereum JSON-RPC API\n  description: The Ethereum JSON-RPC API is the standard interface for interacting with Ethereum nodes. It provides methods\n    for querying blockchain state, sending transactions, managing accounts, and interacting with smart contracts. All methods\n    follow the JSON-RPC 2.0 specification over HTTP or WebSocket.\n  tags:\n  - Ethereum\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ethereum\n    baseUri: http://localhost:8545\n    description: Ethereum JSON-RPC API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: jsonrpccall\n        method: POST\n        description: Ethereum JSON-RPC endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ethereum-rest\n\
  \    description: REST adapter for Ethereum JSON-RPC API.\n    resources:\n    - path: /\n      name: jsonrpccall\n      operations:\n      - method: POST\n        name: jsonrpccall\n        description: Ethereum JSON-RPC endpoint\n        call: ethereum.jsonrpccall\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ethereum-mcp\n    transport: http\n    description: MCP adapter for Ethereum JSON-RPC API for AI agent use.\n    tools:\n    - name: jsonrpccall\n      description: Ethereum JSON-RPC endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ethereum.jsonrpccall\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ethereum/refs/heads/main/capabilities/ethereum-capability.yaml
tags:
- Ethereum
- API
tools:
- description: Ethereum JSON-RPC endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: jsonrpccall
---

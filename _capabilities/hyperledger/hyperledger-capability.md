---
categories: []
consumed_apis: []
description: Hyperledger Besu is an Ethereum client written in Java that exposes a JSON-RPC 2.0 API over HTTP and WebSockets. The API provides namespaces including admin, debug, eth, net, web3, txpool, miner, and trace for interacting with Ethereum-compatible networks, smart contracts, and node operations.
layout: capability
name: Hyperledger Besu JSON-RPC API
operations:
- description: JSON-RPC endpoint
  method: POST
  name: jsonrpccall
  path: /
personas: []
provider_name: Hyperledger
provider_slug: hyperledger
search_terms:
- linux foundation
- distributed ledger
- enterprise
- blockchain
- api
- jsonrpccall
- json-rpc endpoint
- hyperledger
- smart contracts
slug: hyperledger-capability
source_filename: hyperledger-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hyperledger Besu JSON-RPC API\n  description: Hyperledger Besu is an Ethereum client written in Java that exposes a JSON-RPC 2.0 API over HTTP and WebSockets.\n    The API provides namespaces including admin, debug, eth, net, web3, txpool, miner, and trace for interacting with Ethereum-compatible\n    networks, smart contracts, and node operations.\n  tags:\n  - Hyperledger\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hyperledger\n    baseUri: https://besu.example.com\n    description: Hyperledger Besu JSON-RPC API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: jsonrpccall\n        method: POST\n        description: JSON-RPC endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ hyperledger-rest\n    description: REST adapter for Hyperledger Besu JSON-RPC API.\n    resources:\n    - path: /\n      name: jsonrpccall\n      operations:\n      - method: POST\n        name: jsonrpccall\n        description: JSON-RPC endpoint\n        call: hyperledger.jsonrpccall\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hyperledger-mcp\n    transport: http\n    description: MCP adapter for Hyperledger Besu JSON-RPC API for AI agent use.\n    tools:\n    - name: jsonrpccall\n      description: JSON-RPC endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hyperledger.jsonrpccall\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hyperledger/refs/heads/main/capabilities/hyperledger-capability.yaml
tags:
- Hyperledger
- API
tools:
- description: JSON-RPC endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: jsonrpccall
---

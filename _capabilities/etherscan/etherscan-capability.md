---
categories: []
consumed_apis: []
description: Etherscan API V2 provides unified access to blockchain data across Ethereum and 60+ EVM-compatible chains, including transactions, addresses, blocks, smart contracts, token transfers, and gas tracking. A single API key works across all supported networks.
layout: capability
name: Etherscan API
operations:
- description: Unified API endpoint
  method: GET
  name: callapi
  path: /
personas: []
provider_name: Etherscan
provider_slug: etherscan
search_terms:
- etherscan
- callapi
- unified api endpoint
- cryptocurrency
- ethereum
- web3
- blockchain
- api
- evm
slug: etherscan-capability
source_filename: etherscan-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Etherscan API\n  description: Etherscan API V2 provides unified access to blockchain data across Ethereum and 60+ EVM-compatible chains,\n    including transactions, addresses, blocks, smart contracts, token transfers, and gas tracking. A single API key works\n    across all supported networks.\n  tags:\n  - Etherscan\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: etherscan\n    baseUri: https://api.etherscan.io/v2/api\n    description: Etherscan API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: apikey\n      value: '{{ETHERSCAN_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: callapi\n        method: GET\n        description: Unified API endpoint\n        inputParameters:\n        - name: chainid\n          in: query\n          type: integer\n          required: true\n          description:\
  \ Numeric chain ID (e.g. 1 for Ethereum mainnet, 56 for BNB Smart Chain, 8453 for Base).\n        - name: module\n          in: query\n          type: string\n          required: true\n          description: API module (account, contract, transaction, block, stats, gastracker, token).\n        - name: action\n          in: query\n          type: string\n          required: true\n          description: Action within the module (e.g. balance, txlist, tokenbalance, getabi).\n        - name: address\n          in: query\n          type: string\n          description: Ethereum address for account or token operations.\n        - name: contractaddress\n          in: query\n          type: string\n          description: Smart contract address for token or contract operations.\n        - name: startblock\n          in: query\n          type: integer\n        - name: endblock\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n     \
  \   - name: offset\n          in: query\n          type: integer\n        - name: sort\n          in: query\n          type: string\n        - name: tag\n          in: query\n          type: string\n          description: Block tag (latest, earliest, pending) or block number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: etherscan-rest\n    description: REST adapter for Etherscan API.\n    resources:\n    - path: /\n      name: callapi\n      operations:\n      - method: GET\n        name: callapi\n        description: Unified API endpoint\n        call: etherscan.callapi\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: etherscan-mcp\n    transport: http\n    description: MCP adapter for Etherscan API for AI agent use.\n    tools:\n    - name: callapi\n      description: Unified\
  \ API endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: etherscan.callapi\n      with:\n        chainid: tools.chainid\n        module: tools.module\n        action: tools.action\n        address: tools.address\n        contractaddress: tools.contractaddress\n        startblock: tools.startblock\n        endblock: tools.endblock\n        page: tools.page\n        offset: tools.offset\n        sort: tools.sort\n        tag: tools.tag\n      inputParameters:\n      - name: chainid\n        type: integer\n        description: Numeric chain ID (e.g. 1 for Ethereum mainnet, 56 for BNB Smart Chain, 8453 for Base).\n        required: true\n      - name: module\n        type: string\n        description: API module (account, contract, transaction, block, stats, gastracker, token).\n        required: true\n      - name: action\n        type: string\n        description: Action within the module (e.g. balance, txlist, tokenbalance,\
  \ getabi).\n        required: true\n      - name: address\n        type: string\n        description: Ethereum address for account or token operations.\n      - name: contractaddress\n        type: string\n        description: Smart contract address for token or contract operations.\n      - name: startblock\n        type: integer\n        description: startblock\n      - name: endblock\n        type: integer\n        description: endblock\n      - name: page\n        type: integer\n        description: page\n      - name: offset\n        type: integer\n        description: offset\n      - name: sort\n        type: string\n        description: sort\n      - name: tag\n        type: string\n        description: Block tag (latest, earliest, pending) or block number.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ETHERSCAN_TOKEN: ETHERSCAN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/etherscan/refs/heads/main/capabilities/etherscan-capability.yaml
tags:
- Etherscan
- API
tools:
- description: Unified API endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: callapi
---

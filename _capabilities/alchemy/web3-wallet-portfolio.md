---
categories: []
consumed_apis: []
description: Unified capability for building Web3 wallet and portfolio applications. Combines the Token API for balance and metadata queries with the Transfers API for transaction history. Designed for wallet developers, DeFi app builders, and portfolio tracker teams who need comprehensive on-chain data for any EVM-compatible wallet address.
layout: capability
name: Alchemy Web3 Wallet Portfolio
operations:
- description: Get ERC-20 token balances for a wallet address.
  method: POST
  name: get-token-balances
  path: /v1/token-balances
- description: Get metadata for an ERC-20 token contract.
  method: POST
  name: get-token-metadata
  path: /v1/token-metadata
- description: Query historical asset transfers for a wallet address.
  method: POST
  name: get-asset-transfers
  path: /v1/transfers
personas:
- description: Builds EVM wallet applications needing token balances and transaction history.
  id: wallet-developer
  name: Wallet Developer
- description: Develops DeFi applications requiring portfolio tracking and token data.
  id: defi-builder
  name: DeFi Builder
provider_name: Alchemy
provider_slug: alchemy
search_terms:
- gas fee sponsorship and erc-4337 account abstraction.
- web3
- erc-20 token data and metadata.
- get metadata for an erc-20 token contract.
- web3 platform engineer
- blockchain
- wallet developer
- get token metadata
- get metadata (name, symbol, decimals, logo) for an erc-20 token contract.
- get erc-20 token balances for a wallet address.
- defi builder
- builds evm wallet applications needing token balances and transaction history.
- develops defi applications requiring portfolio tracking and token data.
- query historical on-chain asset transfers for a wallet by address, block range, and category.
- on-chain asset transfer history.
- get erc-20 token balances for a wallet address across evm networks.
- dapp developer
- alchemy
- ethereum
- tokens
- get token balances
- manages gas sponsorship infrastructure and erc-4337 policies.
- combines token api and transfers api for wallet portfolio applications.
- account abstraction
- erc-20 token metadata.
- creates decentralized applications with gasless ux for end users.
- get asset transfers
- query historical asset transfers for a wallet address.
- wallet balance and asset portfolio management.
- cryptocurrency
- transfers
- erc-20 token balances for a wallet.
- historical on-chain asset transfers.
- portfolio
- manages gasless transaction sponsorship using erc-4337 account abstraction via gas manager api.
slug: web3-wallet-portfolio
source_filename: web3-wallet-portfolio.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Alchemy Web3 Wallet Portfolio\n  description: Unified capability for building Web3 wallet and portfolio applications. Combines the Token API for balance\n    and metadata queries with the Transfers API for transaction history. Designed for wallet developers, DeFi app builders,\n    and portfolio tracker teams who need comprehensive on-chain data for any EVM-compatible wallet address.\n  tags:\n  - Alchemy\n  - Blockchain\n  - Portfolio\n  - Tokens\n  - Transfers\n  - Web3\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ALCHEMY_API_KEY: ALCHEMY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: token-api\n    baseUri: https://eth-mainnet.g.alchemy.com/v2/{apiKey}\n    description: Alchemy Token API for ERC-20 token data.\n    authentication:\n      type: apikey\n      key: X-Alchemy-Token\n      value: '{{ALCHEMY_API_KEY}}'\n      placement: header\n    resources:\n    - name: token-balances\n\
  \      path: /getTokenBalances\n      description: ERC-20 token balances by wallet address.\n      operations:\n      - name: get-token-balances\n        method: POST\n        description: Returns ERC-20 token balances for a specified wallet address.\n        body:\n          type: json\n          data:\n            id: 1\n            jsonrpc: '2.0'\n            method: alchemy_getTokenBalances\n            params: '{{tools.params}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: token-metadata\n      path: /getTokenMetadata\n      description: ERC-20 token metadata.\n      operations:\n      - name: get-token-metadata\n        method: POST\n        description: Returns metadata for a given ERC-20 token contract address.\n        body:\n          type: json\n          data:\n            id: 1\n            jsonrpc: '2.0'\n            method: alchemy_getTokenMetadata\n            params: '{{tools.params}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: transfers-api\n    baseUri: https://eth-mainnet.g.alchemy.com/v2/{apiKey}\n    description: Alchemy Transfers API for historical on-chain transfer data.\n    authentication:\n      type: apikey\n      key: X-Alchemy-Token\n      value: '{{ALCHEMY_API_KEY}}'\n      placement: header\n    resources:\n    - name: transfers\n      path: /\n      description: Historical asset transfer data.\n      operations:\n      - name: get-asset-transfers\n        method: POST\n        description: Returns asset transfers based on specified filters (ETH, ERC-20, ERC-721, ERC-1155).\n        body:\n          type: json\n          data:\n            id: 1\n            jsonrpc: '2.0'\n            method: alchemy_getAssetTransfers\n            params: '{{tools.params}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wallet-portfolio-api\n    description: Unified REST API for Web3 wallet portfolio data.\n    resources:\n    - path: /v1/token-balances\n      name: token-balances\n      description: ERC-20 token balances for a wallet.\n      operations:\n      - method: POST\n        name: get-token-balances\n        description: Get ERC-20 token balances for a wallet address.\n        call: token-api.get-token-balances\n        with:\n          params: rest.params\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/token-metadata\n      name: token-metadata\n      description: ERC-20 token metadata.\n      operations:\n      - method: POST\n        name: get-token-metadata\n        description: Get metadata for an ERC-20 token contract.\n        call: token-api.get-token-metadata\n        with:\n          params: rest.params\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /v1/transfers\n      name: transfers\n      description: Historical on-chain asset transfers.\n      operations:\n      - method: POST\n        name: get-asset-transfers\n        description: Query historical asset transfers for a wallet address.\n        call: transfers-api.get-asset-transfers\n        with:\n          params: rest.params\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wallet-portfolio-mcp\n    transport: http\n    description: MCP server for AI-assisted Web3 wallet portfolio analysis.\n    tools:\n    - name: get-token-balances\n      description: Get ERC-20 token balances for a wallet address across EVM networks.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: token-api.get-token-balances\n      with:\n        params: tools.params\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-token-metadata\n      description: Get metadata (name, symbol, decimals, logo) for an ERC-20 token contract.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: token-api.get-token-metadata\n      with:\n        params: tools.params\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset-transfers\n      description: Query historical on-chain asset transfers for a wallet by address, block range, and category.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: transfers-api.get-asset-transfers\n      with:\n        params: tools.params\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/alchemy/refs/heads/main/capabilities/web3-wallet-portfolio.yaml
tags:
- Alchemy
- Blockchain
- Portfolio
- Tokens
- Transfers
- Web3
tools:
- description: Get ERC-20 token balances for a wallet address across EVM networks.
  hints:
    idempotent: true
    readOnly: true
  name: get-token-balances
- description: Get metadata (name, symbol, decimals, logo) for an ERC-20 token contract.
  hints:
    idempotent: true
    readOnly: true
  name: get-token-metadata
- description: Query historical on-chain asset transfers for a wallet by address, block range, and category.
  hints:
    idempotent: true
    readOnly: true
  name: get-asset-transfers
---

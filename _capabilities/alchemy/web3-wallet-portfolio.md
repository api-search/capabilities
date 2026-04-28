---
categories: []
consumed_apis:
- token-api
- transfers-api
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
- query historical asset transfers for a wallet address.
- get erc-20 token balances for a wallet address.
- manages gasless transaction sponsorship using erc-4337 account abstraction via gas manager api.
- manages gas sponsorship infrastructure and erc-4337 policies.
- blockchain
- web3 platform engineer
- dapp developer
- account abstraction
- develops defi applications requiring portfolio tracking and token data.
- wallet developer
- portfolio
- ethereum
- get metadata (name, symbol, decimals, logo) for an erc-20 token contract.
- query historical on-chain asset transfers for a wallet by address, block range, and category.
- get erc-20 token balances for a wallet address across evm networks.
- gas fee sponsorship and erc-4337 account abstraction.
- get token balances
- historical on-chain asset transfers.
- erc-20 token metadata.
- erc-20 token data and metadata.
- creates decentralized applications with gasless ux for end users.
- erc-20 token balances for a wallet.
- get asset transfers
- alchemy
- get token metadata
- tokens
- transfers
- builds evm wallet applications needing token balances and transaction history.
- combines token api and transfers api for wallet portfolio applications.
- defi builder
- get metadata for an erc-20 token contract.
- cryptocurrency
- web3
- wallet balance and asset portfolio management.
- on-chain asset transfer history.
slug: web3-wallet-portfolio
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Alchemy Web3 Wallet Portfolio\"\n  description: >-\n    Unified capability for building Web3 wallet and portfolio applications.\n    Combines the Token API for balance and metadata queries with the Transfers\n    API for transaction history. Designed for wallet developers, DeFi app\n    builders, and portfolio tracker teams who need comprehensive on-chain\n    data for any EVM-compatible wallet address.\n  tags:\n    - Alchemy\n    - Blockchain\n    - Portfolio\n    - Tokens\n    - Transfers\n    - Web3\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ALCHEMY_API_KEY: ALCHEMY_API_KEY\n\ncapability:\n  consumes:\n    - import: token-api\n      location: ./shared/token-api.yaml\n    - import: transfers-api\n      location: ./shared/transfers-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wallet-portfolio-api\n      description: \"Unified REST API\
  \ for Web3 wallet portfolio data.\"\n      resources:\n        - path: /v1/token-balances\n          name: token-balances\n          description: \"ERC-20 token balances for a wallet.\"\n          operations:\n            - method: POST\n              name: get-token-balances\n              description: \"Get ERC-20 token balances for a wallet address.\"\n              call: \"token-api.get-token-balances\"\n              with:\n                params: \"rest.params\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/token-metadata\n          name: token-metadata\n          description: \"ERC-20 token metadata.\"\n          operations:\n            - method: POST\n              name: get-token-metadata\n              description: \"Get metadata for an ERC-20 token contract.\"\n              call: \"token-api.get-token-metadata\"\n              with:\n                params: \"rest.params\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transfers\n          name: transfers\n          description: \"Historical on-chain asset transfers.\"\n          operations:\n            - method: POST\n              name: get-asset-transfers\n              description: \"Query historical asset transfers for a wallet address.\"\n              call: \"transfers-api.get-asset-transfers\"\n              with:\n                params: \"rest.params\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wallet-portfolio-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Web3 wallet portfolio analysis.\"\n      tools:\n        - name: get-token-balances\n          description: \"Get ERC-20 token balances for a wallet address across EVM networks.\"\n          hints:\n            readOnly: true\n            idempotent: true\n    \
  \      call: \"token-api.get-token-balances\"\n          with:\n            params: \"tools.params\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-token-metadata\n          description: \"Get metadata (name, symbol, decimals, logo) for an ERC-20 token contract.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"token-api.get-token-metadata\"\n          with:\n            params: \"tools.params\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-asset-transfers\n          description: \"Query historical on-chain asset transfers for a wallet by address, block range, and category.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"transfers-api.get-asset-transfers\"\n          with:\n            params: \"tools.params\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n"
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

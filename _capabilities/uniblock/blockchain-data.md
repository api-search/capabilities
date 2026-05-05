---
api_specs:
- filename: uniblock-unified-api-openapi.yml
  format: yaml
  label: uniblock-unified
  slug: uniblock-unified
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/uniblock/refs/heads/main/openapi/uniblock-unified-api-openapi.yml
categories: []
consumed_apis:
- uniblock-unified
description: Unified capability for blockchain data access via Uniblock. Combines the Unified API and Direct API into a single workflow surface for Web3 developers, DeFi analysts, portfolio trackers, and NFT platforms needing multi-chain token, NFT, transaction, and market data.
layout: capability
name: Uniblock Blockchain Data
operations:
- description: Get token name, symbol, decimals, and contract details
  method: GET
  name: get-token-metadata
  path: /v1/tokens/metadata
- description: Get all token balances for a wallet address
  method: GET
  name: get-token-balances
  path: /v1/tokens/balances
- description: Get current market price for a token
  method: GET
  name: get-market-price
  path: /v1/tokens/price
- description: Get all NFTs held by a wallet address
  method: GET
  name: get-nft-balances
  path: /v1/nfts
- description: Get metadata for a specific NFT
  method: GET
  name: get-nft-metadata
  path: /v1/nfts/metadata
- description: Get transaction history for a wallet
  method: GET
  name: get-transactions
  path: /v1/transactions
personas: []
provider_name: Uniblock
provider_slug: uniblock
search_terms:
- get token price
- token metadata across blockchain networks
- market data
- transaction history
- look up token metadata (name, symbol, decimals, contract) on any supported blockchain
- get current market price for a token
- get metadata for a specific nft
- defi
- get all token balances for a wallet address
- get market price
- get transaction history for a wallet address
- get transaction history for a wallet
- nfts
- blockchain
- get current market price for a token by contract address
- get nft balances
- web3
- uniblock
- nft token metadata
- token market price
- get all nfts held by a wallet address
- get token balances
- get all nfts held by a wallet address on a blockchain network
- get nft metadata
- token balances for a wallet
- get token name, symbol, decimals, and contract details
- nft holdings for a wallet
- get metadata for a specific nft including image, attributes, and collection details
- tokens
- get all token balances for a wallet address across a blockchain network
- get transaction history
- get transactions
- get token metadata
- get nft holdings
slug: blockchain-data
source_filename: blockchain-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Uniblock Blockchain Data\"\n  description: >-\n    Unified capability for blockchain data access via Uniblock. Combines the\n    Unified API and Direct API into a single workflow surface for Web3\n    developers, DeFi analysts, portfolio trackers, and NFT platforms needing\n    multi-chain token, NFT, transaction, and market data.\n  tags:\n    - Uniblock\n    - Blockchain\n    - Web3\n    - Tokens\n    - NFTs\n    - Market Data\n    - DeFi\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNIBLOCK_API_KEY: UNIBLOCK_API_KEY\n\ncapability:\n  consumes:\n    - import: uniblock-unified\n      location: ./shared/uniblock-unified-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: blockchain-data-api\n      description: \"Unified REST API for multi-chain blockchain data via Uniblock.\"\n      resources:\n        - path: /v1/tokens/metadata\n          name:\
  \ token-metadata\n          description: \"Token metadata across blockchain networks\"\n          operations:\n            - method: GET\n              name: get-token-metadata\n              description: \"Get token name, symbol, decimals, and contract details\"\n              call: \"uniblock-unified.get-token-metadata\"\n              with:\n                chain: \"rest.chain\"\n                contractAddress: \"rest.contractAddress\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tokens/balances\n          name: token-balances\n          description: \"Token balances for a wallet\"\n          operations:\n            - method: GET\n              name: get-token-balances\n              description: \"Get all token balances for a wallet address\"\n              call: \"uniblock-unified.get-token-balances\"\n              with:\n                chain: \"rest.chain\"\n                address: \"rest.address\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tokens/price\n          name: token-price\n          description: \"Token market price\"\n          operations:\n            - method: GET\n              name: get-market-price\n              description: \"Get current market price for a token\"\n              call: \"uniblock-unified.get-market-price\"\n              with:\n                chain: \"rest.chain\"\n                contractAddress: \"rest.contractAddress\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/nfts\n          name: nft-balances\n          description: \"NFT holdings for a wallet\"\n          operations:\n            - method: GET\n              name: get-nft-balances\n              description: \"Get all NFTs held by a wallet address\"\n              call: \"uniblock-unified.get-nft-balances\"\n              with:\n     \
  \           chain: \"rest.chain\"\n                address: \"rest.address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/nfts/metadata\n          name: nft-metadata\n          description: \"NFT token metadata\"\n          operations:\n            - method: GET\n              name: get-nft-metadata\n              description: \"Get metadata for a specific NFT\"\n              call: \"uniblock-unified.get-nft-metadata\"\n              with:\n                chain: \"rest.chain\"\n                contractAddress: \"rest.contractAddress\"\n                tokenId: \"rest.tokenId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transactions\n          name: transactions\n          description: \"Transaction history\"\n          operations:\n            - method: GET\n              name: get-transactions\n              description: \"Get transaction\
  \ history for a wallet\"\n              call: \"uniblock-unified.get-transactions\"\n              with:\n                chain: \"rest.chain\"\n                address: \"rest.address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: blockchain-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted blockchain data analysis via Uniblock.\"\n      tools:\n        - name: get-token-metadata\n          description: \"Look up token metadata (name, symbol, decimals, contract) on any supported blockchain\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uniblock-unified.get-token-metadata\"\n          with:\n            chain: \"tools.chain\"\n            contractAddress: \"tools.contractAddress\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-token-balances\n\
  \          description: \"Get all token balances for a wallet address across a blockchain network\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uniblock-unified.get-token-balances\"\n          with:\n            chain: \"tools.chain\"\n            address: \"tools.address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-token-price\n          description: \"Get current market price for a token by contract address\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uniblock-unified.get-market-price\"\n          with:\n            chain: \"tools.chain\"\n            contractAddress: \"tools.contractAddress\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-nft-holdings\n          description: \"Get all NFTs held by a wallet address on a blockchain network\"\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"uniblock-unified.get-nft-balances\"\n          with:\n            chain: \"tools.chain\"\n            address: \"tools.address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-nft-metadata\n          description: \"Get metadata for a specific NFT including image, attributes, and collection details\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uniblock-unified.get-nft-metadata\"\n          with:\n            chain: \"tools.chain\"\n            contractAddress: \"tools.contractAddress\"\n            tokenId: \"tools.tokenId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-transaction-history\n          description: \"Get transaction history for a wallet address\"\n          hints:\n            readOnly: true\n            openWorld: false\n \
  \         call: \"uniblock-unified.get-transactions\"\n          with:\n            chain: \"tools.chain\"\n            address: \"tools.address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/uniblock/refs/heads/main/capabilities/blockchain-data.yaml
tags:
- Uniblock
- Blockchain
- Web3
- Tokens
- NFTs
- Market Data
- DeFi
tools:
- description: Look up token metadata (name, symbol, decimals, contract) on any supported blockchain
  hints:
    openWorld: true
    readOnly: true
  name: get-token-metadata
- description: Get all token balances for a wallet address across a blockchain network
  hints:
    openWorld: false
    readOnly: true
  name: get-token-balances
- description: Get current market price for a token by contract address
  hints:
    openWorld: true
    readOnly: true
  name: get-token-price
- description: Get all NFTs held by a wallet address on a blockchain network
  hints:
    openWorld: false
    readOnly: true
  name: get-nft-holdings
- description: Get metadata for a specific NFT including image, attributes, and collection details
  hints:
    openWorld: true
    readOnly: true
  name: get-nft-metadata
- description: Get transaction history for a wallet address
  hints:
    openWorld: false
    readOnly: true
  name: get-transaction-history
---

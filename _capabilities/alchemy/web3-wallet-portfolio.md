---
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
- cryptocurrency
- get token balances
- get erc-20 token balances for a wallet address across evm networks.
- creates decentralized applications with gasless ux for end users.
- ethereum
- web3
- get asset transfers
- transfers
- combines token api and transfers api for wallet portfolio applications.
- alchemy
- account abstraction
- erc-20 token data and metadata.
- historical on-chain asset transfers.
- on-chain asset transfer history.
- portfolio
- get metadata for an erc-20 token contract.
- erc-20 token metadata.
- web3 platform engineer
- get token metadata
- tokens
- manages gas sponsorship infrastructure and erc-4337 policies.
- builds evm wallet applications needing token balances and transaction history.
- develops defi applications requiring portfolio tracking and token data.
- blockchain
- erc-20 token balances for a wallet.
- get metadata (name, symbol, decimals, logo) for an erc-20 token contract.
- query historical asset transfers for a wallet address.
- defi builder
- dapp developer
- wallet developer
- manages gasless transaction sponsorship using erc-4337 account abstraction via gas manager api.
- gas fee sponsorship and erc-4337 account abstraction.
- query historical on-chain asset transfers for a wallet by address, block range, and category.
- get erc-20 token balances for a wallet address.
- wallet balance and asset portfolio management.
slug: web3-wallet-portfolio
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

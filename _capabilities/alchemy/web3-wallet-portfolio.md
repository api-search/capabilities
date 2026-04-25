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
- dapp developer
- blockchain
- get token balances
- on-chain asset transfer history.
- get asset transfers
- get token metadata
- get metadata for an erc-20 token contract.
- transfers
- web3 platform engineer
- historical on-chain asset transfers.
- cryptocurrency
- manages gasless transaction sponsorship using erc-4337 account abstraction via gas manager api.
- alchemy
- web3
- wallet balance and asset portfolio management.
- manages gas sponsorship infrastructure and erc-4337 policies.
- get metadata (name, symbol, decimals, logo) for an erc-20 token contract.
- erc-20 token metadata.
- wallet developer
- query historical asset transfers for a wallet address.
- gas fee sponsorship and erc-4337 account abstraction.
- erc-20 token data and metadata.
- ethereum
- creates decentralized applications with gasless ux for end users.
- erc-20 token balances for a wallet.
- combines token api and transfers api for wallet portfolio applications.
- tokens
- account abstraction
- portfolio
- builds evm wallet applications needing token balances and transaction history.
- defi builder
- query historical on-chain asset transfers for a wallet by address, block range, and category.
- get erc-20 token balances for a wallet address across evm networks.
- develops defi applications requiring portfolio tracking and token data.
- get erc-20 token balances for a wallet address.
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

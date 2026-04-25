---
consumed_apis:
- gas-manager
description: Capability for managing gasless transaction sponsorship using ERC-4337 Account Abstraction. Combines the Gas Manager API for policy creation and management with paymaster sponsorship. Designed for dApp developers and Web3 platform teams who want to abstract gas fees from end users.
layout: capability
name: Alchemy Gasless Transaction Management
operations:
- description: List all gas sponsorship policies.
  method: GET
  name: list-policies
  path: /v1/policies
- description: Create a new gas sponsorship policy.
  method: POST
  name: create-policy
  path: /v1/policies
- description: Get a specific gas sponsorship policy.
  method: GET
  name: get-policy
  path: /v1/policies/{policyId}
- description: Sponsor a user operation for gasless transactions.
  method: POST
  name: sponsor-user-operation
  path: /v1/sponsor
personas:
- description: Creates decentralized applications with gasless UX for end users.
  id: dapp-developer
  name: dApp Developer
- description: Manages gas sponsorship infrastructure and ERC-4337 policies.
  id: web3-platform-engineer
  name: Web3 Platform Engineer
provider_name: Alchemy
provider_slug: alchemy
search_terms:
- dapp developer
- create a new gas sponsorship policy with spend limits and network settings.
- gas sponsorship for user operations.
- blockchain
- get a specific gas sponsorship policy.
- on-chain asset transfer history.
- list all gas manager sponsorship policies for the alchemy application.
- sponsor a user operation for gasless transactions.
- web3 platform engineer
- get policy
- create policy
- cryptocurrency
- manages gasless transaction sponsorship using erc-4337 account abstraction via gas manager api.
- alchemy
- web3
- wallet balance and asset portfolio management.
- individual gas policy.
- manages gas sponsorship infrastructure and erc-4337 policies.
- wallet developer
- gas fee sponsorship and erc-4337 account abstraction.
- submit a user operation for erc-4337 gas sponsorship, enabling gasless transactions.
- list all gas sponsorship policies.
- erc-20 token data and metadata.
- ethereum
- create a new gas sponsorship policy.
- creates decentralized applications with gasless ux for end users.
- sponsor user operation
- list policies
- combines token api and transfers api for wallet portfolio applications.
- account abstraction
- gas manager
- get details for a specific gas sponsorship policy by id.
- builds evm wallet applications needing token balances and transaction history.
- defi builder
- gas sponsorship policies.
- develops defi applications requiring portfolio tracking and token data.
slug: gasless-transaction-management
tags:
- Alchemy
- Blockchain
- Gas Manager
- Account Abstraction
- Web3
tools:
- description: List all gas manager sponsorship policies for the Alchemy application.
  hints:
    idempotent: true
    readOnly: true
  name: list-policies
- description: Create a new gas sponsorship policy with spend limits and network settings.
  hints:
    idempotent: false
    readOnly: false
  name: create-policy
- description: Get details for a specific gas sponsorship policy by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-policy
- description: Submit a user operation for ERC-4337 gas sponsorship, enabling gasless transactions.
  hints:
    idempotent: false
    readOnly: false
  name: sponsor-user-operation
---

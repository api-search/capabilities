---
categories: []
consumed_apis:
- blockfrost
description: Workflow capability for Cardano blockchain exploration and dApp integration using the Blockfrost API. Enables developers, analysts, and dApp builders to query blocks, transactions, accounts, addresses, native assets, and epochs on the Cardano mainnet.
layout: capability
name: Blockfrost Cardano Explorer
operations:
- description: Get the latest Cardano block
  method: GET
  name: get-latest-block
  path: /v1/blocks/latest
- description: Get transaction by hash
  method: GET
  name: get-transaction
  path: /v1/transactions/{hash}
- description: Get stake account information
  method: GET
  name: get-account
  path: /v1/accounts/{stake_address}
- description: Get address information
  method: GET
  name: get-address
  path: /v1/addresses/{address}
- description: Get native asset information
  method: GET
  name: get-asset
  path: /v1/assets/{asset}
personas: []
provider_name: Blockfrost
provider_slug: blockfrost
search_terms:
- get information about a cardano address including ada balance, utxos, and native asset holdings.
- get stake account information
- submit a signed cardano transaction (cbor encoded) to the blockchain network.
- get address
- cryptocurrency
- get information about a cardano native asset including policy, name, supply, and on-chain metadata.
- dapps
- get transaction by hash
- Blockchain Analyst
- get asset
- interacts with cardano defi protocols and monitors address and account activity
- nft
- get account
- analyzes on-chain data including blocks, transactions, and account activity
- mints and manages cardano native assets and nft collections
- get latest epoch
- get transaction
- get latest block
- cardano
- get block
- builds decentralized applications on cardano using blockchain data and transaction submission
- decentralized identity, assets, and governance
- get the latest block on the cardano mainnet blockchain with slot, epoch, and transaction count information.
- get cardano stake account information including rewards, delegation, and pool information.
- get native asset information
- submit transaction
- get a specific cardano block by hash or block number.
- cardano blockchain exploration for developers, dapp builders, and analysts
- get the current cardano epoch information including start time, end time, and protocol parameters.
- blockchain
- DeFi User
- get details of a specific cardano transaction by its hash, including inputs, outputs, and metadata.
- web3
- core blockchain data and transaction management
- get the latest cardano block
- get address information
- NFT Creator
- dApp Developer
slug: blockfrost-cardano-explorer
tags:
- Blockchain
- Cardano
- Cryptocurrency
- DApps
- NFT
- Web3
tools:
- description: Get the latest block on the Cardano mainnet blockchain with slot, epoch, and transaction count information.
  hints:
    openWorld: true
    readOnly: true
  name: get-latest-block
- description: Get a specific Cardano block by hash or block number.
  hints:
    openWorld: true
    readOnly: true
  name: get-block
- description: Get details of a specific Cardano transaction by its hash, including inputs, outputs, and metadata.
  hints:
    openWorld: true
    readOnly: true
  name: get-transaction
- description: Get Cardano stake account information including rewards, delegation, and pool information.
  hints:
    openWorld: true
    readOnly: true
  name: get-account
- description: Get information about a Cardano address including ADA balance, UTXOs, and native asset holdings.
  hints:
    openWorld: true
    readOnly: true
  name: get-address
- description: Get information about a Cardano native asset including policy, name, supply, and on-chain metadata.
  hints:
    openWorld: true
    readOnly: true
  name: get-asset
- description: Get the current Cardano epoch information including start time, end time, and protocol parameters.
  hints:
    openWorld: true
    readOnly: true
  name: get-latest-epoch
- description: Submit a signed Cardano transaction (CBOR encoded) to the blockchain network.
  hints:
    openWorld: false
    readOnly: false
  name: submit-transaction
---

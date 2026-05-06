---
categories: []
consumed_apis: []
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
- cardano blockchain exploration for developers, dapp builders, and analysts
- web3
- dApp Developer
- nft
- get latest block
- blockchain
- get the latest cardano block
- get stake account information
- submit a signed cardano transaction (cbor encoded) to the blockchain network.
- Blockchain Analyst
- get address
- get asset
- cardano
- get native asset information
- interacts with cardano defi protocols and monitors address and account activity
- get latest epoch
- get details of a specific cardano transaction by its hash, including inputs, outputs, and metadata.
- analyzes on-chain data including blocks, transactions, and account activity
- NFT Creator
- dapps
- get information about a cardano native asset including policy, name, supply, and on-chain metadata.
- get transaction
- submit transaction
- get address information
- get block
- get cardano stake account information including rewards, delegation, and pool information.
- get information about a cardano address including ada balance, utxos, and native asset holdings.
- get the current cardano epoch information including start time, end time, and protocol parameters.
- mints and manages cardano native assets and nft collections
- get transaction by hash
- DeFi User
- cryptocurrency
- core blockchain data and transaction management
- builds decentralized applications on cardano using blockchain data and transaction submission
- get the latest block on the cardano mainnet blockchain with slot, epoch, and transaction count information.
- get account
- get a specific cardano block by hash or block number.
- decentralized identity, assets, and governance
slug: blockfrost-cardano-explorer
source_filename: blockfrost-cardano-explorer.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Blockfrost Cardano Explorer\n  description: Workflow capability for Cardano blockchain exploration and dApp integration using the Blockfrost API. Enables\n    developers, analysts, and dApp builders to query blocks, transactions, accounts, addresses, native assets, and epochs\n    on the Cardano mainnet.\n  tags:\n  - Blockchain\n  - Cardano\n  - Cryptocurrency\n  - DApps\n  - NFT\n  - Web3\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BLOCKFROST_PROJECT_ID: BLOCKFROST_PROJECT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: blockfrost\n    baseUri: https://cardano-mainnet.blockfrost.io/api/v0\n    description: Blockfrost Cardano mainnet API\n    authentication:\n      type: apikey\n      key: project_id\n      value: '{{BLOCKFROST_PROJECT_ID}}'\n      placement: header\n    resources:\n    - name: health\n      path: /health\n      description: API health check\n      operations:\n\
  \      - name: get-health\n        method: GET\n        description: Return backend status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blocks\n      path: /blocks\n      description: Cardano block data\n      operations:\n      - name: get-latest-block\n        method: GET\n        description: Get the latest block\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-block\n        method: GET\n        description: Get a specific block by hash or number\n        inputParameters:\n        - name: hash_or_number\n          in: path\n          type: string\n          required: true\n          description: Block hash or block number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /txs\n \
  \     description: Cardano transaction data\n      operations:\n      - name: get-transaction\n        method: GET\n        description: Get a specific transaction\n        inputParameters:\n        - name: hash\n          in: path\n          type: string\n          required: true\n          description: Transaction hash\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-transaction\n        method: POST\n        description: Submit a signed transaction to the network\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: application/cbor\n          data:\n            tx_data: '{{tools.tx_data}}'\n    - name: accounts\n      path: /accounts\n      description: Cardano stake account data\n      operations:\n      - name: get-account\n        method: GET\n        description: Get stake account\
  \ information\n        inputParameters:\n        - name: stake_address\n          in: path\n          type: string\n          required: true\n          description: Bech32 stake address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: addresses\n      path: /addresses\n      description: Cardano address data\n      operations:\n      - name: get-address\n        method: GET\n        description: Get address information\n        inputParameters:\n        - name: address\n          in: path\n          type: string\n          required: true\n          description: Bech32 address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /assets\n      description: Cardano native assets\n      operations:\n      - name: get-asset\n        method: GET\n        description: Get asset information\n     \
  \   inputParameters:\n        - name: asset\n          in: path\n          type: string\n          required: true\n          description: Asset ID (policy_id + asset_name in hex)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: epochs\n      path: /epochs\n      description: Cardano epoch data\n      operations:\n      - name: get-latest-epoch\n        method: GET\n        description: Get the latest epoch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: blockfrost-cardano-explorer-api\n    description: Unified REST API for Cardano blockchain exploration.\n    resources:\n    - path: /v1/blocks/latest\n      name: latest-block\n      operations:\n      - method: GET\n        name: get-latest-block\n        description: Get the latest Cardano block\n        call:\
  \ blockfrost.get-latest-block\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions/{hash}\n      name: transactions\n      operations:\n      - method: GET\n        name: get-transaction\n        description: Get transaction by hash\n        call: blockfrost.get-transaction\n        with:\n          hash: rest.hash\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{stake_address}\n      name: accounts\n      operations:\n      - method: GET\n        name: get-account\n        description: Get stake account information\n        call: blockfrost.get-account\n        with:\n          stake_address: rest.stake_address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/addresses/{address}\n      name: addresses\n      operations:\n      - method: GET\n        name: get-address\n        description: Get address information\n        call: blockfrost.get-address\n\
  \        with:\n          address: rest.address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets/{asset}\n      name: assets\n      operations:\n      - method: GET\n        name: get-asset\n        description: Get native asset information\n        call: blockfrost.get-asset\n        with:\n          asset: rest.asset\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: blockfrost-cardano-explorer-mcp\n    transport: http\n    description: MCP server for AI-assisted Cardano blockchain exploration and analysis.\n    tools:\n    - name: get-latest-block\n      description: Get the latest block on the Cardano mainnet blockchain with slot, epoch, and transaction count information.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: blockfrost.get-latest-block\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-block\n\
  \      description: Get a specific Cardano block by hash or block number.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: blockfrost.get-block\n      with:\n        hash_or_number: tools.hash_or_number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-transaction\n      description: Get details of a specific Cardano transaction by its hash, including inputs, outputs, and metadata.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: blockfrost.get-transaction\n      with:\n        hash: tools.hash\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Get Cardano stake account information including rewards, delegation, and pool information.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: blockfrost.get-account\n      with:\n        stake_address: tools.stake_address\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n    - name: get-address\n      description: Get information about a Cardano address including ADA balance, UTXOs, and native asset holdings.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: blockfrost.get-address\n      with:\n        address: tools.address\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset\n      description: Get information about a Cardano native asset including policy, name, supply, and on-chain metadata.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: blockfrost.get-asset\n      with:\n        asset: tools.asset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-latest-epoch\n      description: Get the current Cardano epoch information including start time, end time, and protocol parameters.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: blockfrost.get-latest-epoch\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: submit-transaction\n      description: Submit a signed Cardano transaction (CBOR encoded) to the blockchain network.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: blockfrost.submit-transaction\n      with:\n        tx_data: tools.tx_data\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/blockfrost/refs/heads/main/capabilities/blockfrost-cardano-explorer.yaml
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

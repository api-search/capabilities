---
categories: []
consumed_apis: []
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
- gas fee sponsorship and erc-4337 account abstraction.
- web3
- erc-20 token data and metadata.
- list policies
- web3 platform engineer
- blockchain
- create a new gas sponsorship policy.
- wallet developer
- get details for a specific gas sponsorship policy by id.
- defi builder
- builds evm wallet applications needing token balances and transaction history.
- develops defi applications requiring portfolio tracking and token data.
- gas sponsorship for user operations.
- submit a user operation for erc-4337 gas sponsorship, enabling gasless transactions.
- on-chain asset transfer history.
- list all gas sponsorship policies.
- sponsor user operation
- dapp developer
- alchemy
- gas sponsorship policies.
- ethereum
- get a specific gas sponsorship policy.
- create a new gas sponsorship policy with spend limits and network settings.
- sponsor a user operation for gasless transactions.
- create policy
- manages gas sponsorship infrastructure and erc-4337 policies.
- combines token api and transfers api for wallet portfolio applications.
- account abstraction
- individual gas policy.
- creates decentralized applications with gasless ux for end users.
- cryptocurrency
- wallet balance and asset portfolio management.
- list all gas manager sponsorship policies for the alchemy application.
- get policy
- gas manager
- manages gasless transaction sponsorship using erc-4337 account abstraction via gas manager api.
slug: gasless-transaction-management
source_filename: gasless-transaction-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Alchemy Gasless Transaction Management\n  description: Capability for managing gasless transaction sponsorship using ERC-4337 Account Abstraction. Combines the Gas\n    Manager API for policy creation and management with paymaster sponsorship. Designed for dApp developers and Web3 platform\n    teams who want to abstract gas fees from end users.\n  tags:\n  - Alchemy\n  - Blockchain\n  - Gas Manager\n  - Account Abstraction\n  - Web3\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ALCHEMY_BEARER_TOKEN: ALCHEMY_BEARER_TOKEN\n    ALCHEMY_API_KEY: ALCHEMY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: gas-manager\n    baseUri: https://manage.g.alchemy.com/api\n    description: Alchemy Gas Manager Management API for policy administration.\n    authentication:\n      type: bearer\n      token: '{{ALCHEMY_BEARER_TOKEN}}'\n    resources:\n    - name: policies\n      path: /gasManager/policy\n\
  \      description: Gas sponsorship policies.\n      operations:\n      - name: list-policies\n        method: GET\n        description: Returns all gas manager sponsorship policies.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-policy\n        method: POST\n        description: Creates a new gas sponsorship policy.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            network: '{{tools.network}}'\n            maxSpendPerUser: '{{tools.maxSpendPerUser}}'\n            maxSpendTotal: '{{tools.maxSpendTotal}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policy\n      path: /gasManager/policy/{policyId}\n      description: Individual gas sponsorship policy.\n      operations:\n      - name: get-policy\n        method: GET\n        description: Retrieves\
  \ details for a specific gas sponsorship policy.\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the gas manager policy.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sponsor\n      path: /sponsorUserOperation\n      description: Paymaster endpoint for sponsoring user operations.\n      operations:\n      - name: sponsor-user-operation\n        method: POST\n        description: Submits a user operation for gas sponsorship via ERC-4337 paymaster.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            jsonrpc: '2.0'\n            method: alchemy_requestGasAndPaymasterAndData\n            params: '{{tools.params}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: gasless-tx-api\n    description: Unified REST API for gasless transaction management.\n    resources:\n    - path: /v1/policies\n      name: policies\n      description: Gas sponsorship policies.\n      operations:\n      - method: GET\n        name: list-policies\n        description: List all gas sponsorship policies.\n        call: gas-manager.list-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-policy\n        description: Create a new gas sponsorship policy.\n        call: gas-manager.create-policy\n        with:\n          name: rest.name\n          network: rest.network\n          maxSpendPerUser: rest.maxSpendPerUser\n          maxSpendTotal: rest.maxSpendTotal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies/{policyId}\n      name: policy\n      description: Individual gas policy.\n  \
  \    operations:\n      - method: GET\n        name: get-policy\n        description: Get a specific gas sponsorship policy.\n        call: gas-manager.get-policy\n        with:\n          policyId: rest.policyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sponsor\n      name: sponsor\n      description: Gas sponsorship for user operations.\n      operations:\n      - method: POST\n        name: sponsor-user-operation\n        description: Sponsor a user operation for gasless transactions.\n        call: gas-manager.sponsor-user-operation\n        with:\n          id: rest.id\n          params: rest.params\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: gasless-tx-mcp\n    transport: http\n    description: MCP server for AI-assisted gasless transaction management.\n    tools:\n    - name: list-policies\n      description: List all gas manager sponsorship policies for\
  \ the Alchemy application.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: gas-manager.list-policies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-policy\n      description: Create a new gas sponsorship policy with spend limits and network settings.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: gas-manager.create-policy\n      with:\n        name: tools.name\n        network: tools.network\n        maxSpendPerUser: tools.maxSpendPerUser\n        maxSpendTotal: tools.maxSpendTotal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-policy\n      description: Get details for a specific gas sponsorship policy by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: gas-manager.get-policy\n      with:\n        policyId: tools.policyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sponsor-user-operation\n\
  \      description: Submit a user operation for ERC-4337 gas sponsorship, enabling gasless transactions.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: gas-manager.sponsor-user-operation\n      with:\n        id: tools.id\n        params: tools.params\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/alchemy/refs/heads/main/capabilities/gasless-transaction-management.yaml
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

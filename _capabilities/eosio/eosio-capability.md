---
categories: []
consumed_apis: []
description: HTTP/JSON RPC interface exposed by the chain_api_plugin in nodeos, the reference EOSIO (now Antelope) blockchain node implementation. The chain API allows clients to read blockchain state, fetch blocks and accounts, inspect ABI and contract data, and submit signed transactions to the network.
layout: capability
name: EOSIO / Antelope Nodeos Chain API
operations:
- description: Get chain information
  method: GET
  name: getinfo
  path: /get_info
- description: Get a block by ID or number
  method: POST
  name: getblock
  path: /get_block
- description: Get account information
  method: POST
  name: getaccount
  path: /get_account
- description: Get the ABI for a contract account
  method: POST
  name: getabi
  path: /get_abi
- description: Get contract code for an account
  method: POST
  name: getcode
  path: /get_code
- description: Get currency balance for an account
  method: POST
  name: getcurrencybalance
  path: /get_currency_balance
- description: Read rows from a contract table
  method: POST
  name: gettablerows
  path: /get_table_rows
- description: Push a signed transaction
  method: POST
  name: pushtransaction
  path: /push_transaction
- description: Send a signed transaction
  method: POST
  name: sendtransaction
  path: /send_transaction
- description: Get required keys for a transaction
  method: POST
  name: getrequiredkeys
  path: /get_required_keys
personas: []
provider_name: EOSIO
provider_slug: eosio
search_terms:
- eosio
- blockchain
- get currency balance for an account
- get required keys for a transaction
- getrequiredkeys
- getcode
- getinfo
- getcurrencybalance
- getblock
- sendtransaction
- get a block by id or number
- getabi
- gettablerows
- getaccount
- antelope
- get the abi for a contract account
- get account information
- api
- eos
- pushtransaction
- get contract code for an account
- push a signed transaction
- get chain information
- send a signed transaction
- read rows from a contract table
slug: eosio-capability
source_filename: eosio-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: EOSIO / Antelope Nodeos Chain API\n  description: HTTP/JSON RPC interface exposed by the chain_api_plugin in nodeos, the reference EOSIO (now Antelope) blockchain\n    node implementation. The chain API allows clients to read blockchain state, fetch blocks and accounts, inspect ABI and\n    contract data, and submit signed transactions to the network.\n  tags:\n  - Eosio\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: eosio\n    baseUri: https://eos.greymass.com/v1/chain\n    description: EOSIO / Antelope Nodeos Chain API HTTP API.\n    resources:\n    - name: get-info\n      path: /get_info\n      operations:\n      - name: getinfo\n        method: GET\n        description: Get chain information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-block\n      path: /get_block\n\
  \      operations:\n      - name: getblock\n        method: POST\n        description: Get a block by ID or number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-account\n      path: /get_account\n      operations:\n      - name: getaccount\n        method: POST\n        description: Get account information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-abi\n      path: /get_abi\n      operations:\n      - name: getabi\n        method: POST\n        description: Get the ABI for a contract account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-code\n      path: /get_code\n      operations:\n      - name: getcode\n        method: POST\n        description: Get contract code for an account\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-currency-balance\n      path: /get_currency_balance\n      operations:\n      - name: getcurrencybalance\n        method: POST\n        description: Get currency balance for an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-table-rows\n      path: /get_table_rows\n      operations:\n      - name: gettablerows\n        method: POST\n        description: Read rows from a contract table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: push-transaction\n      path: /push_transaction\n      operations:\n      - name: pushtransaction\n        method: POST\n        description: Push a signed transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: send-transaction\n      path: /send_transaction\n      operations:\n      - name: sendtransaction\n        method: POST\n        description: Send a signed transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-required-keys\n      path: /get_required_keys\n      operations:\n      - name: getrequiredkeys\n        method: POST\n        description: Get required keys for a transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: eosio-rest\n    description: REST adapter for EOSIO / Antelope Nodeos Chain API.\n    resources:\n    - path: /get_info\n      name: getinfo\n      operations:\n      - method: GET\n        name: getinfo\n        description: Get chain information\n        call: eosio.getinfo\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_block\n      name: getblock\n      operations:\n      - method: POST\n        name: getblock\n        description: Get a block by ID or number\n        call: eosio.getblock\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_account\n      name: getaccount\n      operations:\n      - method: POST\n        name: getaccount\n        description: Get account information\n        call: eosio.getaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_abi\n      name: getabi\n      operations:\n      - method: POST\n        name: getabi\n        description: Get the ABI for a contract account\n        call: eosio.getabi\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_code\n      name: getcode\n      operations:\n      - method: POST\n        name: getcode\n        description:\
  \ Get contract code for an account\n        call: eosio.getcode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_currency_balance\n      name: getcurrencybalance\n      operations:\n      - method: POST\n        name: getcurrencybalance\n        description: Get currency balance for an account\n        call: eosio.getcurrencybalance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_table_rows\n      name: gettablerows\n      operations:\n      - method: POST\n        name: gettablerows\n        description: Read rows from a contract table\n        call: eosio.gettablerows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /push_transaction\n      name: pushtransaction\n      operations:\n      - method: POST\n        name: pushtransaction\n        description: Push a signed transaction\n        call: eosio.pushtransaction\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /send_transaction\n      name: sendtransaction\n      operations:\n      - method: POST\n        name: sendtransaction\n        description: Send a signed transaction\n        call: eosio.sendtransaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_required_keys\n      name: getrequiredkeys\n      operations:\n      - method: POST\n        name: getrequiredkeys\n        description: Get required keys for a transaction\n        call: eosio.getrequiredkeys\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: eosio-mcp\n    transport: http\n    description: MCP adapter for EOSIO / Antelope Nodeos Chain API for AI agent use.\n    tools:\n    - name: getinfo\n      description: Get chain information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eosio.getinfo\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getblock\n      description: Get a block by ID or number\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eosio.getblock\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccount\n      description: Get account information\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eosio.getaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getabi\n      description: Get the ABI for a contract account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eosio.getabi\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcode\n      description: Get contract code for an account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n    \
  \  call: eosio.getcode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcurrencybalance\n      description: Get currency balance for an account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eosio.getcurrencybalance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettablerows\n      description: Read rows from a contract table\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eosio.gettablerows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pushtransaction\n      description: Push a signed transaction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eosio.pushtransaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendtransaction\n      description: Send a signed transaction\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eosio.sendtransaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrequiredkeys\n      description: Get required keys for a transaction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eosio.getrequiredkeys\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/eosio/refs/heads/main/capabilities/eosio-capability.yaml
tags:
- Eosio
- API
tools:
- description: Get chain information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinfo
- description: Get a block by ID or number
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getblock
- description: Get account information
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getaccount
- description: Get the ABI for a contract account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getabi
- description: Get contract code for an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getcode
- description: Get currency balance for an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getcurrencybalance
- description: Read rows from a contract table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: gettablerows
- description: Push a signed transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pushtransaction
- description: Send a signed transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendtransaction
- description: Get required keys for a transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getrequiredkeys
---

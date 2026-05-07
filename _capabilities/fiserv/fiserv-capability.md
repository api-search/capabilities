---
categories: []
consumed_apis: []
description: The Fiserv BankingHub API provides RESTful access to core banking operations including account management, transactions, transfers, payments, and party (customer) management. BankingHub enables financial institutions and fintech partners to integrate account opening, fund transfers, payment processing, and customer data management into their applications.
layout: capability
name: Fiserv BankingHub API
operations:
- description: Fiserv Create a new account
  method: POST
  name: addaccount
  path: /banking/accounts
- description: Fiserv Retrieve account details
  method: GET
  name: getaccount
  path: /banking/accounts/{accountId}
- description: Fiserv Update account details
  method: PATCH
  name: updateaccount
  path: /banking/accounts/{accountId}
- description: Fiserv List account transactions
  method: GET
  name: listtransactions
  path: /banking/accounts/{accountId}/transactions
- description: Fiserv Initiate a fund transfer
  method: POST
  name: createtransfer
  path: /banking/transfers
- description: Fiserv Retrieve transfer details
  method: GET
  name: gettransfer
  path: /banking/transfers/{transferId}
- description: Fiserv Process a payment
  method: POST
  name: createpayment
  path: /banking/payments
- description: Fiserv Reverse a payment
  method: POST
  name: reversepayment
  path: /banking/payments/{paymentId}/reverse
- description: Fiserv Create a customer party
  method: POST
  name: addparty
  path: /banking/parties
- description: Fiserv Retrieve party details
  method: GET
  name: getparty
  path: /banking/parties/{partyId}
- description: Fiserv Update party details
  method: PATCH
  name: updateparty
  path: /banking/parties/{partyId}
personas: []
provider_name: Fiserv
provider_slug: fiserv
search_terms:
- reversepayment
- fiserv initiate a fund transfer
- getaccount
- wealth management
- fiserv
- fiserv process a payment
- updateaccount
- api
- fiserv create a customer party
- fiserv update party details
- createpayment
- updateparty
- fiserv update account details
- createtransfer
- getparty
- fiserv list account transactions
- gettransfer
- listtransactions
- fiserv retrieve account details
- fiserv create a new account
- addaccount
- financial
- fiserv retrieve party details
- banking
- payments
- fiserv retrieve transfer details
- fiserv reverse a payment
- addparty
slug: fiserv-capability
source_filename: fiserv-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fiserv BankingHub API\n  description: The Fiserv BankingHub API provides RESTful access to core banking operations including account management,\n    transactions, transfers, payments, and party (customer) management. BankingHub enables financial institutions and fintech\n    partners to integrate account opening, fund transfers, payment processing, and customer data management into their applications.\n  tags:\n  - Fiserv\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fiserv\n    baseUri: https://cert.api.fiservapps.com\n    description: Fiserv BankingHub API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{FISERV_TOKEN}}'\n    resources:\n    - name: banking-accounts\n      path: /banking/accounts\n      operations:\n      - name: addaccount\n        method: POST\n        description: Fiserv Create a new account\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: banking-accounts-accountid\n      path: /banking/accounts/{accountId}\n      operations:\n      - name: getaccount\n        method: GET\n        description: Fiserv Retrieve account details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccount\n        method: PATCH\n        description: Fiserv Update account details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: banking-accounts-accountid-transactions\n      path: /banking/accounts/{accountId}/transactions\n      operations:\n      - name: listtransactions\n        method: GET\n        description: Fiserv List account transactions\n        inputParameters:\n        - name: fromDate\n          in: query\n          type: string\n        \
  \  description: Start date for the transaction search range.\n        - name: toDate\n          in: query\n          type: string\n          description: End date for the transaction search range.\n        - name: transactionType\n          in: query\n          type: string\n          description: Filter by transaction type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: banking-transfers\n      path: /banking/transfers\n      operations:\n      - name: createtransfer\n        method: POST\n        description: Fiserv Initiate a fund transfer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: banking-transfers-transferid\n      path: /banking/transfers/{transferId}\n      operations:\n      - name: gettransfer\n        method: GET\n        description: Fiserv Retrieve transfer details\n        inputParameters:\n\
  \        - name: transferId\n          in: path\n          type: string\n          required: true\n          description: The unique transfer identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: banking-payments\n      path: /banking/payments\n      operations:\n      - name: createpayment\n        method: POST\n        description: Fiserv Process a payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: banking-payments-paymentid-reverse\n      path: /banking/payments/{paymentId}/reverse\n      operations:\n      - name: reversepayment\n        method: POST\n        description: Fiserv Reverse a payment\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: The unique payment identifier.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: banking-parties\n      path: /banking/parties\n      operations:\n      - name: addparty\n        method: POST\n        description: Fiserv Create a customer party\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: banking-parties-partyid\n      path: /banking/parties/{partyId}\n      operations:\n      - name: getparty\n        method: GET\n        description: Fiserv Retrieve party details\n        inputParameters:\n        - name: partyId\n          in: path\n          type: string\n          required: true\n          description: The unique party identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateparty\n        method: PATCH\n        description: Fiserv Update party details\n\
  \        inputParameters:\n        - name: partyId\n          in: path\n          type: string\n          required: true\n          description: The unique party identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fiserv-rest\n    description: REST adapter for Fiserv BankingHub API.\n    resources:\n    - path: /banking/accounts\n      name: addaccount\n      operations:\n      - method: POST\n        name: addaccount\n        description: Fiserv Create a new account\n        call: fiserv.addaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /banking/accounts/{accountId}\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Fiserv Retrieve account details\n        call: fiserv.getaccount\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /banking/accounts/{accountId}\n      name: updateaccount\n      operations:\n      - method: PATCH\n        name: updateaccount\n        description: Fiserv Update account details\n        call: fiserv.updateaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /banking/accounts/{accountId}/transactions\n      name: listtransactions\n      operations:\n      - method: GET\n        name: listtransactions\n        description: Fiserv List account transactions\n        call: fiserv.listtransactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /banking/transfers\n      name: createtransfer\n      operations:\n      - method: POST\n        name: createtransfer\n        description: Fiserv Initiate a fund transfer\n        call: fiserv.createtransfer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /banking/transfers/{transferId}\n      name:\
  \ gettransfer\n      operations:\n      - method: GET\n        name: gettransfer\n        description: Fiserv Retrieve transfer details\n        call: fiserv.gettransfer\n        with:\n          transferId: rest.transferId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /banking/payments\n      name: createpayment\n      operations:\n      - method: POST\n        name: createpayment\n        description: Fiserv Process a payment\n        call: fiserv.createpayment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /banking/payments/{paymentId}/reverse\n      name: reversepayment\n      operations:\n      - method: POST\n        name: reversepayment\n        description: Fiserv Reverse a payment\n        call: fiserv.reversepayment\n        with:\n          paymentId: rest.paymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /banking/parties\n      name: addparty\n   \
  \   operations:\n      - method: POST\n        name: addparty\n        description: Fiserv Create a customer party\n        call: fiserv.addparty\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /banking/parties/{partyId}\n      name: getparty\n      operations:\n      - method: GET\n        name: getparty\n        description: Fiserv Retrieve party details\n        call: fiserv.getparty\n        with:\n          partyId: rest.partyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /banking/parties/{partyId}\n      name: updateparty\n      operations:\n      - method: PATCH\n        name: updateparty\n        description: Fiserv Update party details\n        call: fiserv.updateparty\n        with:\n          partyId: rest.partyId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fiserv-mcp\n    transport: http\n    description: MCP adapter\
  \ for Fiserv BankingHub API for AI agent use.\n    tools:\n    - name: addaccount\n      description: Fiserv Create a new account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiserv.addaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccount\n      description: Fiserv Retrieve account details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiserv.getaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateaccount\n      description: Fiserv Update account details\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiserv.updateaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtransactions\n      description: Fiserv List account transactions\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: fiserv.listtransactions\n      with:\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        transactionType: tools.transactionType\n      inputParameters:\n      - name: fromDate\n        type: string\n        description: Start date for the transaction search range.\n      - name: toDate\n        type: string\n        description: End date for the transaction search range.\n      - name: transactionType\n        type: string\n        description: Filter by transaction type.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtransfer\n      description: Fiserv Initiate a fund transfer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiserv.createtransfer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettransfer\n      description: Fiserv Retrieve transfer details\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: fiserv.gettransfer\n      with:\n        transferId: tools.transferId\n      inputParameters:\n      - name: transferId\n        type: string\n        description: The unique transfer identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpayment\n      description: Fiserv Process a payment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiserv.createpayment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reversepayment\n      description: Fiserv Reverse a payment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiserv.reversepayment\n      with:\n        paymentId: tools.paymentId\n      inputParameters:\n      - name: paymentId\n        type: string\n        description: The unique payment identifier.\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addparty\n      description: Fiserv Create a customer party\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiserv.addparty\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getparty\n      description: Fiserv Retrieve party details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiserv.getparty\n      with:\n        partyId: tools.partyId\n      inputParameters:\n      - name: partyId\n        type: string\n        description: The unique party identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateparty\n      description: Fiserv Update party details\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiserv.updateparty\n\
  \      with:\n        partyId: tools.partyId\n      inputParameters:\n      - name: partyId\n        type: string\n        description: The unique party identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FISERV_TOKEN: FISERV_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fiserv/refs/heads/main/capabilities/fiserv-capability.yaml
tags:
- Fiserv
- API
tools:
- description: Fiserv Create a new account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addaccount
- description: Fiserv Retrieve account details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Fiserv Update account details
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateaccount
- description: Fiserv List account transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransactions
- description: Fiserv Initiate a fund transfer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtransfer
- description: Fiserv Retrieve transfer details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransfer
- description: Fiserv Process a payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpayment
- description: Fiserv Reverse a payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reversepayment
- description: Fiserv Create a customer party
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addparty
- description: Fiserv Retrieve party details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getparty
- description: Fiserv Update party details
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateparty
---

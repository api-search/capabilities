---
categories: []
consumed_apis: []
description: The Braintree Payments API is the core server-side interface for accepting and processing payments through Braintree's gateway. It enables developers to create and manage transactions, handle authorizations and captures, and process refunds and voids. The API supports a wide range of payment methods including credit and debit cards, PayPal, Apple Pay, Google Pay, and Venmo. Authentication uses HTTP Basic auth with the merchant's public key as the username and private key as the password. All requests and responses use XML or JSON depending on the SDK and endpoint variant used.
layout: capability
name: Braintree Payments API
operations:
- description: Create a transaction
  method: POST
  name: createtransaction
  path: /transactions
- description: Get a transaction
  method: GET
  name: gettransaction
  path: /transactions/{transactionId}
- description: Submit transaction for settlement
  method: PUT
  name: submittransactionforsettlement
  path: /transactions/{transactionId}/submit_for_settlement
- description: Void a transaction
  method: PUT
  name: voidtransaction
  path: /transactions/{transactionId}/void
- description: Refund a transaction
  method: POST
  name: refundtransaction
  path: /transactions/{transactionId}/refund
- description: Generate a client token
  method: POST
  name: generateclienttoken
  path: /client_token
- description: Create a customer
  method: POST
  name: createcustomer
  path: /customers
- description: Get a customer
  method: GET
  name: getcustomer
  path: /customers/{customerId}
- description: Update a customer
  method: PUT
  name: updatecustomer
  path: /customers/{customerId}
- description: Delete a customer
  method: DELETE
  name: deletecustomer
  path: /customers/{customerId}
- description: Create a payment method
  method: POST
  name: createpaymentmethod
  path: /payment_methods
- description: Get a payment method
  method: GET
  name: getpaymentmethod
  path: /payment_methods/any/{paymentMethodToken}
- description: Update a payment method
  method: PUT
  name: updatepaymentmethod
  path: /payment_methods/any/{paymentMethodToken}
- description: Delete a payment method
  method: DELETE
  name: deletepaymentmethod
  path: /payment_methods/any/{paymentMethodToken}
- description: List disputes
  method: GET
  name: listdisputes
  path: /disputes
- description: Get a dispute
  method: GET
  name: getdispute
  path: /disputes/{disputeId}
- description: Accept a dispute
  method: PUT
  name: acceptdispute
  path: /disputes/{disputeId}/accept
personas: []
provider_name: braintree
provider_slug: braintree
search_terms:
- gettransaction
- refundtransaction
- get a transaction
- void a transaction
- get a customer
- delete a customer
- createpaymentmethod
- deletepaymentmethod
- create a payment method
- braintree
- updatepaymentmethod
- voidtransaction
- update a payment method
- refund a transaction
- generate a client token
- list disputes
- accept a dispute
- getdispute
- submit transaction for settlement
- getcustomer
- delete a payment method
- submittransactionforsettlement
- api
- acceptdispute
- listdisputes
- generateclienttoken
- createcustomer
- createtransaction
- create a customer
- updatecustomer
- update a customer
- deletecustomer
- get a dispute
- getpaymentmethod
- get a payment method
- create a transaction
slug: braintree-capability
source_filename: braintree-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Braintree Payments API\n  description: The Braintree Payments API is the core server-side interface for accepting and processing payments through\n    Braintree's gateway. It enables developers to create and manage transactions, handle authorizations and captures, and\n    process refunds and voids. The API supports a wide range of payment methods including credit and debit cards, PayPal,\n    Apple Pay, Google Pay, and Venmo. Authentication uses HTTP Basic auth with the merchant's public key as the username and\n    private key as the password. All requests and responses use XML or JSON depending on the SDK and endpoint variant used.\n  tags:\n  - Braintree\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: braintree\n    baseUri: https://api.braintreegateway.com/merchants/your_merchant_id\n    description: Braintree Payments API HTTP API.\n    authentication:\n      type:\
  \ basic\n      username: '{{BRAINTREE_USERNAME}}'\n      password: '{{BRAINTREE_PASSWORD}}'\n    resources:\n    - name: transactions\n      path: /transactions\n      operations:\n      - name: createtransaction\n        method: POST\n        description: Create a transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-transactionid\n      path: /transactions/{transactionId}\n      operations:\n      - name: gettransaction\n        method: GET\n        description: Get a transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-transactionid-submit-for-settlement\n      path: /transactions/{transactionId}/submit_for_settlement\n      operations:\n      - name: submittransactionforsettlement\n        method: PUT\n        description: Submit transaction for settlement\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-transactionid-void\n      path: /transactions/{transactionId}/void\n      operations:\n      - name: voidtransaction\n        method: PUT\n        description: Void a transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-transactionid-refund\n      path: /transactions/{transactionId}/refund\n      operations:\n      - name: refundtransaction\n        method: POST\n        description: Refund a transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: client-token\n      path: /client_token\n      operations:\n      - name: generateclienttoken\n        method: POST\n        description: Generate a client token\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /customers\n      operations:\n      - name: createcustomer\n        method: POST\n        description: Create a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-customerid\n      path: /customers/{customerId}\n      operations:\n      - name: getcustomer\n        method: GET\n        description: Get a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecustomer\n        method: PUT\n        description: Update a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecustomer\n        method: DELETE\n        description: Delete a customer\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-methods\n      path: /payment_methods\n      operations:\n      - name: createpaymentmethod\n        method: POST\n        description: Create a payment method\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-methods-any-paymentmethodtoken\n      path: /payment_methods/any/{paymentMethodToken}\n      operations:\n      - name: getpaymentmethod\n        method: GET\n        description: Get a payment method\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepaymentmethod\n        method: PUT\n        description: Update a payment method\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n      - name: deletepaymentmethod\n        method: DELETE\n        description: Delete a payment method\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: disputes\n      path: /disputes\n      operations:\n      - name: listdisputes\n        method: GET\n        description: List disputes\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter disputes by current status.\n        - name: received_date\n          in: query\n          type: string\n          description: Filter disputes received on or after this date in YYYY-MM-DD format.\n        - name: page\n          in: query\n          type: integer\n          description: Page number for paginated results, starting at 1.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: disputes-disputeid\n\
  \      path: /disputes/{disputeId}\n      operations:\n      - name: getdispute\n        method: GET\n        description: Get a dispute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: disputes-disputeid-accept\n      path: /disputes/{disputeId}/accept\n      operations:\n      - name: acceptdispute\n        method: PUT\n        description: Accept a dispute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: braintree-rest\n    description: REST adapter for Braintree Payments API.\n    resources:\n    - path: /transactions\n      name: createtransaction\n      operations:\n      - method: POST\n        name: createtransaction\n        description: Create a transaction\n        call: braintree.createtransaction\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /transactions/{transactionId}\n      name: gettransaction\n      operations:\n      - method: GET\n        name: gettransaction\n        description: Get a transaction\n        call: braintree.gettransaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions/{transactionId}/submit_for_settlement\n      name: submittransactionforsettlement\n      operations:\n      - method: PUT\n        name: submittransactionforsettlement\n        description: Submit transaction for settlement\n        call: braintree.submittransactionforsettlement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions/{transactionId}/void\n      name: voidtransaction\n      operations:\n      - method: PUT\n        name: voidtransaction\n        description: Void a transaction\n        call: braintree.voidtransaction\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /transactions/{transactionId}/refund\n      name: refundtransaction\n      operations:\n      - method: POST\n        name: refundtransaction\n        description: Refund a transaction\n        call: braintree.refundtransaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /client_token\n      name: generateclienttoken\n      operations:\n      - method: POST\n        name: generateclienttoken\n        description: Generate a client token\n        call: braintree.generateclienttoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers\n      name: createcustomer\n      operations:\n      - method: POST\n        name: createcustomer\n        description: Create a customer\n        call: braintree.createcustomer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customerId}\n      name: getcustomer\n      operations:\n      - method: GET\n\
  \        name: getcustomer\n        description: Get a customer\n        call: braintree.getcustomer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customerId}\n      name: updatecustomer\n      operations:\n      - method: PUT\n        name: updatecustomer\n        description: Update a customer\n        call: braintree.updatecustomer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customerId}\n      name: deletecustomer\n      operations:\n      - method: DELETE\n        name: deletecustomer\n        description: Delete a customer\n        call: braintree.deletecustomer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payment_methods\n      name: createpaymentmethod\n      operations:\n      - method: POST\n        name: createpaymentmethod\n        description: Create a payment method\n        call: braintree.createpaymentmethod\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /payment_methods/any/{paymentMethodToken}\n      name: getpaymentmethod\n      operations:\n      - method: GET\n        name: getpaymentmethod\n        description: Get a payment method\n        call: braintree.getpaymentmethod\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payment_methods/any/{paymentMethodToken}\n      name: updatepaymentmethod\n      operations:\n      - method: PUT\n        name: updatepaymentmethod\n        description: Update a payment method\n        call: braintree.updatepaymentmethod\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payment_methods/any/{paymentMethodToken}\n      name: deletepaymentmethod\n      operations:\n      - method: DELETE\n        name: deletepaymentmethod\n        description: Delete a payment method\n        call: braintree.deletepaymentmethod\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /disputes\n      name: listdisputes\n      operations:\n      - method: GET\n        name: listdisputes\n        description: List disputes\n        call: braintree.listdisputes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /disputes/{disputeId}\n      name: getdispute\n      operations:\n      - method: GET\n        name: getdispute\n        description: Get a dispute\n        call: braintree.getdispute\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /disputes/{disputeId}/accept\n      name: acceptdispute\n      operations:\n      - method: PUT\n        name: acceptdispute\n        description: Accept a dispute\n        call: braintree.acceptdispute\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: braintree-mcp\n    transport: http\n    description: MCP adapter for Braintree Payments API for AI agent\
  \ use.\n    tools:\n    - name: createtransaction\n      description: Create a transaction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: braintree.createtransaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettransaction\n      description: Get a transaction\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: braintree.gettransaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submittransactionforsettlement\n      description: Submit transaction for settlement\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: braintree.submittransactionforsettlement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: voidtransaction\n      description: Void a transaction\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: true\n      call: braintree.voidtransaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refundtransaction\n      description: Refund a transaction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: braintree.refundtransaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateclienttoken\n      description: Generate a client token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: braintree.generateclienttoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcustomer\n      description: Create a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: braintree.createcustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcustomer\n      description:\
  \ Get a customer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: braintree.getcustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecustomer\n      description: Update a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: braintree.updatecustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecustomer\n      description: Delete a customer\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: braintree.deletecustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpaymentmethod\n      description: Create a payment method\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: braintree.createpaymentmethod\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getpaymentmethod\n      description: Get a payment method\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: braintree.getpaymentmethod\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepaymentmethod\n      description: Update a payment method\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: braintree.updatepaymentmethod\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepaymentmethod\n      description: Delete a payment method\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: braintree.deletepaymentmethod\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdisputes\n      description: List disputes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: braintree.listdisputes\n      with:\n        status: tools.status\n        received_date: tools.received_date\n        page: tools.page\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter disputes by current status.\n      - name: received_date\n        type: string\n        description: Filter disputes received on or after this date in YYYY-MM-DD format.\n      - name: page\n        type: integer\n        description: Page number for paginated results, starting at 1.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdispute\n      description: Get a dispute\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: braintree.getdispute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acceptdispute\n      description: Accept a dispute\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ true\n      call: braintree.acceptdispute\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BRAINTREE_USERNAME: BRAINTREE_USERNAME\n    BRAINTREE_PASSWORD: BRAINTREE_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/braintree/refs/heads/main/capabilities/braintree-capability.yaml
tags:
- Braintree
- API
tools:
- description: Create a transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtransaction
- description: Get a transaction
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransaction
- description: Submit transaction for settlement
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: submittransactionforsettlement
- description: Void a transaction
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: voidtransaction
- description: Refund a transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: refundtransaction
- description: Generate a client token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateclienttoken
- description: Create a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustomer
- description: Get a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcustomer
- description: Update a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecustomer
- description: Delete a customer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecustomer
- description: Create a payment method
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpaymentmethod
- description: Get a payment method
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpaymentmethod
- description: Update a payment method
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepaymentmethod
- description: Delete a payment method
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepaymentmethod
- description: List disputes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdisputes
- description: Get a dispute
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdispute
- description: Accept a dispute
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: acceptdispute
---

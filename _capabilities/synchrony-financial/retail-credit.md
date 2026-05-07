---
categories: []
consumed_apis: []
description: Unified retail credit capability combining Synchrony's credit authorization and Quickscreen preapproval APIs. Enables merchants to offer instant credit decisions, process purchases on credit, handle payments, and manage refunds and reversals across web, mobile, and point-of-sale channels.
layout: capability
name: Synchrony Financial Retail Credit
operations:
- description: Run a Quickscreen preapproval to offer instant credit to a customer.
  method: POST
  name: submit-preapproval
  path: /v1/preapprovals
- description: Submit a full credit card application for instant decision.
  method: POST
  name: submit-application
  path: /v1/applications
- description: Retrieve the decision for a submitted credit application.
  method: GET
  name: get-application-decision
  path: /v1/applications/{applicationId}
- description: Authorize a purchase transaction on a Synchrony credit account.
  method: POST
  name: create-purchase
  path: /v1/purchases
- description: Place an authorization hold on a Synchrony credit account.
  method: POST
  name: create-preauthorization
  path: /v1/preauthorizations
- description: Process a payment to a customer's Synchrony credit account.
  method: POST
  name: create-payment
  path: /v1/payments
- description: Process a refund to a customer's Synchrony credit account.
  method: POST
  name: create-refund
  path: /v1/refunds
- description: Reverse or void a prior Synchrony credit transaction.
  method: POST
  name: create-reversal
  path: /v1/reversals
personas: []
provider_name: Synchrony Financial
provider_slug: synchrony-financial
search_terms:
- submit credit preapproval
- authorize a purchase transaction on a synchrony credit account.
- authorize a retail credit purchase transaction on a synchrony account.
- submit application
- place an authorization hold on a synchrony credit account for future capture.
- credit purchase authorizations.
- reverse or void a prior synchrony credit transaction.
- submit a full synchrony credit card application for an instant credit decision.
- process a payment to reduce a customer's synchrony credit balance.
- process refund
- consumer finance
- create preauthorization
- retrieve the decision for a submitted credit application.
- credit transaction refunds.
- soft-pull credit preapproval checks.
- synchrony financial
- retail finance
- place an authorization hold on a synchrony credit account.
- run a quickscreen preapproval to offer instant credit to a customer.
- submit preapproval
- transaction reversals and voids.
- create payment
- submit a full credit card application for instant decision.
- reverse transaction
- credit hold preauthorizations.
- credit authorization
- financial services
- credit
- create refund
- process payment
- create purchase
- credit account payments.
- credit application decisions.
- run a soft-pull quickscreen preapproval to instantly offer credit to a customer by name and address.
- authorize purchase
- process a refund to a customer's synchrony credit account.
- payments
- process a payment to a customer's synchrony credit account.
- retail credit
- retrieve the credit decision for a previously submitted application.
- get application decision
- void or reverse a prior synchrony credit transaction before settlement.
- full credit card application submissions.
- refund a prior synchrony credit transaction to the customer's account.
- create reversal
- submit credit application
slug: retail-credit
source_filename: retail-credit.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Synchrony Financial Retail Credit\n  description: Unified retail credit capability combining Synchrony's credit authorization and Quickscreen preapproval APIs.\n    Enables merchants to offer instant credit decisions, process purchases on credit, handle payments, and manage refunds\n    and reversals across web, mobile, and point-of-sale channels.\n  tags:\n  - Synchrony Financial\n  - Retail Credit\n  - Credit Authorization\n  - Consumer Finance\n  - Payments\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SYNCHRONY_API_TOKEN: SYNCHRONY_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: synchrony-credit-auth\n    baseUri: https://api.syf.com\n    description: Synchrony Financial Credit Authorization API for processing retail credit transactions.\n    authentication:\n      type: bearer\n      token: '{{SYNCHRONY_API_TOKEN}}'\n    resources:\n    - name: purchases\n      path:\
  \ /v1/authorizations/purchases\n      description: Purchase authorization transactions.\n      operations:\n      - name: create-purchase\n        method: POST\n        description: Initiates a purchase transaction against a Synchrony credit account.\n        inputParameters:\n        - name: merchantId\n          in: body\n          type: string\n          required: true\n          description: Merchant Synchrony identifier.\n        - name: accountNumber\n          in: body\n          type: string\n          required: true\n          description: Customer credit account number or payment token.\n        - name: amount\n          in: body\n          type: number\n          required: true\n          description: Transaction amount in dollars.\n        - name: channel\n          in: body\n          type: string\n          required: false\n          description: 'Transaction channel: web, mobile, or pos.'\n        - name: merchantOrderId\n          in: body\n          type: string\n    \
  \      required: false\n          description: Merchant internal order reference.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            accountNumber: '{{tools.accountNumber}}'\n            amount: '{{tools.amount}}'\n            channel: '{{tools.channel}}'\n            merchantOrderId: '{{tools.merchantOrderId}}'\n    - name: preauthorizations\n      path: /v1/authorizations/preauthorizations\n      description: Preauthorization hold operations.\n      operations:\n      - name: create-preauthorization\n        method: POST\n        description: Places an authorization hold on a customer's credit account.\n        inputParameters:\n        - name: merchantId\n          in: body\n          type: string\n          required: true\n          description: Merchant identifier.\n        - name: accountNumber\n\
  \          in: body\n          type: string\n          required: true\n          description: Credit account number or payment token.\n        - name: amount\n          in: body\n          type: number\n          required: true\n          description: Hold amount in dollars.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            accountNumber: '{{tools.accountNumber}}'\n            amount: '{{tools.amount}}'\n    - name: completions\n      path: /v1/authorizations/completions\n      description: Complete prior preauthorizations.\n      operations:\n      - name: create-completion\n        method: POST\n        description: Completes a prior preauthorization by capturing the final transaction amount.\n        inputParameters:\n        - name: merchantId\n          in: body\n          type: string\n    \
  \      required: true\n        - name: authorizationCode\n          in: body\n          type: string\n          required: true\n          description: Original preauthorization code.\n        - name: amount\n          in: body\n          type: number\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            authorizationCode: '{{tools.authorizationCode}}'\n            amount: '{{tools.amount}}'\n    - name: payments\n      path: /v1/authorizations/payments\n      description: Account payment operations.\n      operations:\n      - name: create-payment\n        method: POST\n        description: Processes a payment to a customer's Synchrony credit account.\n        inputParameters:\n        - name: merchantId\n          in: body\n          type: string\n          required: true\n\
  \        - name: accountNumber\n          in: body\n          type: string\n          required: true\n        - name: amount\n          in: body\n          type: number\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            accountNumber: '{{tools.accountNumber}}'\n            amount: '{{tools.amount}}'\n    - name: refunds\n      path: /v1/authorizations/refunds\n      description: Refund credit operations.\n      operations:\n      - name: create-refund\n        method: POST\n        description: Processes a refund to a customer's Synchrony credit account.\n        inputParameters:\n        - name: merchantId\n          in: body\n          type: string\n          required: true\n        - name: originalTransactionId\n          in: body\n          type: string\n          required:\
  \ true\n        - name: amount\n          in: body\n          type: number\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            originalTransactionId: '{{tools.originalTransactionId}}'\n            amount: '{{tools.amount}}'\n    - name: reversals\n      path: /v1/authorizations/reversals\n      description: Transaction reversal operations.\n      operations:\n      - name: create-reversal\n        method: POST\n        description: Voids or reverses a prior transaction.\n        inputParameters:\n        - name: merchantId\n          in: body\n          type: string\n          required: true\n        - name: originalTransactionId\n          in: body\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            originalTransactionId: '{{tools.originalTransactionId}}'\n  - type: http\n    namespace: synchrony-quickscreen\n    baseUri: https://api.syf.com\n    description: Synchrony Financial Quickscreen preapproval and credit application API.\n    authentication:\n      type: bearer\n      token: '{{SYNCHRONY_API_TOKEN}}'\n    resources:\n    - name: preapprovals\n      path: /v1/credit/preapproval\n      description: Soft-pull preapproval operations.\n      operations:\n      - name: submit-preapproval\n        method: POST\n        description: Submits a soft-pull preapproval check using customer name and address.\n        inputParameters:\n        - name: merchantId\n          in: body\n          type: string\n          required: true\n        - name: firstName\n          in: body\n          type: string\n          required: true\n \
  \       - name: lastName\n          in: body\n          type: string\n          required: true\n        - name: zipCode\n          in: body\n          type: string\n          required: true\n        - name: channel\n          in: body\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            address:\n              zipCode: '{{tools.zipCode}}'\n    - name: applications\n      path: /v1/credit/applications\n      description: Full credit card application submissions.\n      operations:\n      - name: submit-application\n        method: POST\n        description: Submits a full credit card application for instant decision.\n        inputParameters:\n        - name: merchantId\n\
  \          in: body\n          type: string\n          required: true\n        - name: offerId\n          in: body\n          type: string\n          required: false\n          description: Pre-filled offer ID from Quickscreen if available.\n        - name: firstName\n          in: body\n          type: string\n          required: true\n        - name: lastName\n          in: body\n          type: string\n          required: true\n        - name: channel\n          in: body\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            offerId: '{{tools.offerId}}'\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n    - name: decisions\n      path: /v1/credit/applications/{applicationId}\n      description: Application decision\
  \ retrieval.\n      operations:\n      - name: get-application-decision\n        method: GET\n        description: Retrieves the decision for a submitted credit application.\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: synchrony-retail-credit-api\n    description: Unified REST API for Synchrony retail credit operations.\n    resources:\n    - path: /v1/preapprovals\n      name: preapprovals\n      description: Soft-pull credit preapproval checks.\n      operations:\n      - method: POST\n        name: submit-preapproval\n        description: Run a Quickscreen preapproval to offer instant credit to a customer.\n        call: synchrony-quickscreen.submit-preapproval\n        with:\n          merchantId: rest.merchantId\n  \
  \        firstName: rest.firstName\n          lastName: rest.lastName\n          zipCode: rest.zipCode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications\n      name: applications\n      description: Full credit card application submissions.\n      operations:\n      - method: POST\n        name: submit-application\n        description: Submit a full credit card application for instant decision.\n        call: synchrony-quickscreen.submit-application\n        with:\n          merchantId: rest.merchantId\n          offerId: rest.offerId\n          firstName: rest.firstName\n          lastName: rest.lastName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{applicationId}\n      name: application-decision\n      description: Credit application decisions.\n      operations:\n      - method: GET\n        name: get-application-decision\n        description: Retrieve the decision for a\
  \ submitted credit application.\n        call: synchrony-quickscreen.get-application-decision\n        with:\n          applicationId: rest.applicationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/purchases\n      name: purchases\n      description: Credit purchase authorizations.\n      operations:\n      - method: POST\n        name: create-purchase\n        description: Authorize a purchase transaction on a Synchrony credit account.\n        call: synchrony-credit-auth.create-purchase\n        with:\n          merchantId: rest.merchantId\n          accountNumber: rest.accountNumber\n          amount: rest.amount\n          channel: rest.channel\n          merchantOrderId: rest.merchantOrderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/preauthorizations\n      name: preauthorizations\n      description: Credit hold preauthorizations.\n      operations:\n      - method: POST\n        name:\
  \ create-preauthorization\n        description: Place an authorization hold on a Synchrony credit account.\n        call: synchrony-credit-auth.create-preauthorization\n        with:\n          merchantId: rest.merchantId\n          accountNumber: rest.accountNumber\n          amount: rest.amount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments\n      name: payments\n      description: Credit account payments.\n      operations:\n      - method: POST\n        name: create-payment\n        description: Process a payment to a customer's Synchrony credit account.\n        call: synchrony-credit-auth.create-payment\n        with:\n          merchantId: rest.merchantId\n          accountNumber: rest.accountNumber\n          amount: rest.amount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/refunds\n      name: refunds\n      description: Credit transaction refunds.\n      operations:\n      - method:\
  \ POST\n        name: create-refund\n        description: Process a refund to a customer's Synchrony credit account.\n        call: synchrony-credit-auth.create-refund\n        with:\n          merchantId: rest.merchantId\n          originalTransactionId: rest.originalTransactionId\n          amount: rest.amount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reversals\n      name: reversals\n      description: Transaction reversals and voids.\n      operations:\n      - method: POST\n        name: create-reversal\n        description: Reverse or void a prior Synchrony credit transaction.\n        call: synchrony-credit-auth.create-reversal\n        with:\n          merchantId: rest.merchantId\n          originalTransactionId: rest.originalTransactionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: synchrony-retail-credit-mcp\n    transport: http\n    description: MCP server\
  \ for AI-assisted retail credit management using Synchrony Financial APIs.\n    tools:\n    - name: submit-credit-preapproval\n      description: Run a soft-pull Quickscreen preapproval to instantly offer credit to a customer by name and address.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: synchrony-quickscreen.submit-preapproval\n      with:\n        merchantId: tools.merchantId\n        firstName: tools.firstName\n        lastName: tools.lastName\n        zipCode: tools.zipCode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-credit-application\n      description: Submit a full Synchrony credit card application for an instant credit decision.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: synchrony-quickscreen.submit-application\n      with:\n        merchantId: tools.merchantId\n        offerId: tools.offerId\n        firstName:\
  \ tools.firstName\n        lastName: tools.lastName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application-decision\n      description: Retrieve the credit decision for a previously submitted application.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: synchrony-quickscreen.get-application-decision\n      with:\n        applicationId: tools.applicationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authorize-purchase\n      description: Authorize a retail credit purchase transaction on a Synchrony account.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: synchrony-credit-auth.create-purchase\n      with:\n        merchantId: tools.merchantId\n        accountNumber: tools.accountNumber\n        amount: tools.amount\n        channel: tools.channel\n        merchantOrderId: tools.merchantOrderId\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-preauthorization\n      description: Place an authorization hold on a Synchrony credit account for future capture.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: synchrony-credit-auth.create-preauthorization\n      with:\n        merchantId: tools.merchantId\n        accountNumber: tools.accountNumber\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-payment\n      description: Process a payment to reduce a customer's Synchrony credit balance.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: synchrony-credit-auth.create-payment\n      with:\n        merchantId: tools.merchantId\n        accountNumber: tools.accountNumber\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: process-refund\n      description: Refund a prior Synchrony credit transaction to the customer's account.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: synchrony-credit-auth.create-refund\n      with:\n        merchantId: tools.merchantId\n        originalTransactionId: tools.originalTransactionId\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reverse-transaction\n      description: Void or reverse a prior Synchrony credit transaction before settlement.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: synchrony-credit-auth.create-reversal\n      with:\n        merchantId: tools.merchantId\n        originalTransactionId: tools.originalTransactionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/synchrony-financial/refs/heads/main/capabilities/retail-credit.yaml
tags:
- Synchrony Financial
- Retail Credit
- Credit Authorization
- Consumer Finance
- Payments
tools:
- description: Run a soft-pull Quickscreen preapproval to instantly offer credit to a customer by name and address.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-credit-preapproval
- description: Submit a full Synchrony credit card application for an instant credit decision.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-credit-application
- description: Retrieve the credit decision for a previously submitted application.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-application-decision
- description: Authorize a retail credit purchase transaction on a Synchrony account.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authorize-purchase
- description: Place an authorization hold on a Synchrony credit account for future capture.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-preauthorization
- description: Process a payment to reduce a customer's Synchrony credit balance.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: process-payment
- description: Refund a prior Synchrony credit transaction to the customer's account.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: process-refund
- description: Void or reverse a prior Synchrony credit transaction before settlement.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: reverse-transaction
---

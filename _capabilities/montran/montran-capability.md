---
categories: []
consumed_apis: []
description: The Montran Corporate Payments Portal enables corporates to exercise complete control over accounts at their various bank relationships, with the ability to make secure payments over the Internet. It supports SWIFT payments and local clearing delivery through API integration and H2H (Host-to-Host) protocols. Corporates can connect their ERP systems and manually or automatically upload invoices for payments and collections management. The portal provides multi-bank visibility and supports secure payment initiation across multiple currencies and payment types.
layout: capability
name: Montran Corporate Payments Portal API
operations:
- description: Montran List corporate payments
  method: GET
  name: listcorporatepayments
  path: /payments
- description: Montran Create a corporate payment
  method: POST
  name: createcorporatepayment
  path: /payments
- description: Montran Get payment details
  method: GET
  name: getcorporatepayment
  path: /payments/{paymentId}
- description: Montran Approve a payment
  method: POST
  name: approvepayment
  path: /payments/{paymentId}/approve
- description: Montran Reject a payment
  method: POST
  name: rejectpayment
  path: /payments/{paymentId}/reject
- description: Montran List bank accounts
  method: GET
  name: listbankaccounts
  path: /accounts
- description: Montran Get bank account details
  method: GET
  name: getbankaccount
  path: /accounts/{accountId}
- description: Montran List account transactions
  method: GET
  name: listaccounttransactions
  path: /accounts/{accountId}/transactions
- description: Montran Upload a payment file
  method: POST
  name: uploadpaymentfile
  path: /files
- description: Montran Get file processing status
  method: GET
  name: getfilestatus
  path: /files/{fileId}
- description: Montran List beneficiaries
  method: GET
  name: listbeneficiaries
  path: /beneficiaries
- description: Montran Create a beneficiary
  method: POST
  name: createbeneficiary
  path: /beneficiaries
personas: []
provider_name: Montran
provider_slug: montran
search_terms:
- montran list beneficiaries
- listbeneficiaries
- uploadpaymentfile
- montran list corporate payments
- montran list bank accounts
- getcorporatepayment
- montran reject a payment
- montran list account transactions
- real-time payments
- market infrastructure
- api
- swift
- montran upload a payment file
- montran approve a payment
- rejectpayment
- listbankaccounts
- montran create a beneficiary
- financial services
- montran
- listaccounttransactions
- getfilestatus
- montran create a corporate payment
- getbankaccount
- createbeneficiary
- createcorporatepayment
- montran get bank account details
- banking
- approvepayment
- payments
- listcorporatepayments
- iso 20022
- montran get file processing status
- messaging
- central banking
- montran get payment details
slug: montran-capability
source_filename: montran-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Montran Corporate Payments Portal API\n  description: The Montran Corporate Payments Portal enables corporates to exercise complete control over accounts at their\n    various bank relationships, with the ability to make secure payments over the Internet. It supports SWIFT payments and\n    local clearing delivery through API integration and H2H (Host-to-Host) protocols. Corporates can connect their ERP systems\n    and manually or automatically upload invoices for payments and collections management. The portal provides multi-bank\n    visibility and supports secure payment initiation across multiple currencies and payment types.\n  tags:\n  - Montran\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: montran\n    baseUri: https://api.montran.com/corporate/v1\n    description: Montran Corporate Payments Portal API HTTP API.\n    authentication:\n      type: bearer\n  \
  \    token: '{{MONTRAN_TOKEN}}'\n    resources:\n    - name: payments\n      path: /payments\n      operations:\n      - name: listcorporatepayments\n        method: GET\n        description: Montran List corporate payments\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by payment status\n        - name: paymentType\n          in: query\n          type: string\n          description: Filter by payment type\n        - name: bankId\n          in: query\n          type: string\n          description: Filter by bank relationship\n        - name: currency\n          in: query\n          type: string\n        - name: fromDate\n          in: query\n          type: string\n        - name: toDate\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcorporatepayment\n        method: POST\n        description: Montran Create a corporate payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments-paymentid\n      path: /payments/{paymentId}\n      operations:\n      - name: getcorporatepayment\n        method: GET\n        description: Montran Get payment details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments-paymentid-approve\n      path: /payments/{paymentId}/approve\n      operations:\n      - name: approvepayment\n        method: POST\n        description: Montran Approve a payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments-paymentid-reject\n\
  \      path: /payments/{paymentId}/reject\n      operations:\n      - name: rejectpayment\n        method: POST\n        description: Montran Reject a payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /accounts\n      operations:\n      - name: listbankaccounts\n        method: GET\n        description: Montran List bank accounts\n        inputParameters:\n        - name: bankId\n          in: query\n          type: string\n          description: Filter by bank relationship\n        - name: currency\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid\n      path: /accounts/{accountId}\n      operations:\n      - name: getbankaccount\n        method: GET\n        description: Montran Get bank account details\n        inputParameters:\n\
  \        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-transactions\n      path: /accounts/{accountId}/transactions\n      operations:\n      - name: listaccounttransactions\n        method: GET\n        description: Montran List account transactions\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: fromDate\n          in: query\n          type: string\n        - name: toDate\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: files\n      path: /files\n      operations:\n      - name: uploadpaymentfile\n        method: POST\n        description: Montran Upload a payment file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-fileid\n      path: /files/{fileId}\n      operations:\n      - name: getfilestatus\n        method: GET\n        description: Montran Get file processing status\n        inputParameters:\n        - name: fileId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the uploaded file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: beneficiaries\n      path: /beneficiaries\n      operations:\n      - name: listbeneficiaries\n        method: GET\n        description: Montran List beneficiaries\n        inputParameters:\n\
  \        - name: page\n          in: query\n          type: integer\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbeneficiary\n        method: POST\n        description: Montran Create a beneficiary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: montran-rest\n    description: REST adapter for Montran Corporate Payments Portal API.\n    resources:\n    - path: /payments\n      name: listcorporatepayments\n      operations:\n      - method: GET\n        name: listcorporatepayments\n        description: Montran List corporate payments\n        call: montran.listcorporatepayments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payments\n    \
  \  name: createcorporatepayment\n      operations:\n      - method: POST\n        name: createcorporatepayment\n        description: Montran Create a corporate payment\n        call: montran.createcorporatepayment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payments/{paymentId}\n      name: getcorporatepayment\n      operations:\n      - method: GET\n        name: getcorporatepayment\n        description: Montran Get payment details\n        call: montran.getcorporatepayment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payments/{paymentId}/approve\n      name: approvepayment\n      operations:\n      - method: POST\n        name: approvepayment\n        description: Montran Approve a payment\n        call: montran.approvepayment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payments/{paymentId}/reject\n      name: rejectpayment\n      operations:\n      - method:\
  \ POST\n        name: rejectpayment\n        description: Montran Reject a payment\n        call: montran.rejectpayment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts\n      name: listbankaccounts\n      operations:\n      - method: GET\n        name: listbankaccounts\n        description: Montran List bank accounts\n        call: montran.listbankaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}\n      name: getbankaccount\n      operations:\n      - method: GET\n        name: getbankaccount\n        description: Montran Get bank account details\n        call: montran.getbankaccount\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/transactions\n      name: listaccounttransactions\n      operations:\n      - method: GET\n        name: listaccounttransactions\n\
  \        description: Montran List account transactions\n        call: montran.listaccounttransactions\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files\n      name: uploadpaymentfile\n      operations:\n      - method: POST\n        name: uploadpaymentfile\n        description: Montran Upload a payment file\n        call: montran.uploadpaymentfile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}\n      name: getfilestatus\n      operations:\n      - method: GET\n        name: getfilestatus\n        description: Montran Get file processing status\n        call: montran.getfilestatus\n        with:\n          fileId: rest.fileId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /beneficiaries\n      name: listbeneficiaries\n      operations:\n      - method: GET\n        name: listbeneficiaries\n      \
  \  description: Montran List beneficiaries\n        call: montran.listbeneficiaries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /beneficiaries\n      name: createbeneficiary\n      operations:\n      - method: POST\n        name: createbeneficiary\n        description: Montran Create a beneficiary\n        call: montran.createbeneficiary\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: montran-mcp\n    transport: http\n    description: MCP adapter for Montran Corporate Payments Portal API for AI agent use.\n    tools:\n    - name: listcorporatepayments\n      description: Montran List corporate payments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: montran.listcorporatepayments\n      with:\n        status: tools.status\n        paymentType: tools.paymentType\n        bankId: tools.bankId\n        currency: tools.currency\n\
  \        fromDate: tools.fromDate\n        toDate: tools.toDate\n        page: tools.page\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by payment status\n      - name: paymentType\n        type: string\n        description: Filter by payment type\n      - name: bankId\n        type: string\n        description: Filter by bank relationship\n      - name: currency\n        type: string\n        description: currency\n      - name: fromDate\n        type: string\n        description: fromDate\n      - name: toDate\n        type: string\n        description: toDate\n      - name: page\n        type: integer\n        description: page\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcorporatepayment\n      description: Montran Create a corporate payment\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: montran.createcorporatepayment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcorporatepayment\n      description: Montran Get payment details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: montran.getcorporatepayment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approvepayment\n      description: Montran Approve a payment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: montran.approvepayment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rejectpayment\n      description: Montran Reject a payment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: montran.rejectpayment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ listbankaccounts\n      description: Montran List bank accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: montran.listbankaccounts\n      with:\n        bankId: tools.bankId\n        currency: tools.currency\n      inputParameters:\n      - name: bankId\n        type: string\n        description: Filter by bank relationship\n      - name: currency\n        type: string\n        description: currency\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbankaccount\n      description: Montran Get bank account details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: montran.getbankaccount\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: Unique account identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listaccounttransactions\n      description: Montran List account transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: montran.listaccounttransactions\n      with:\n        accountId: tools.accountId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        page: tools.page\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: fromDate\n        type: string\n        description: fromDate\n      - name: toDate\n        type: string\n        description: toDate\n      - name: page\n        type: integer\n        description: page\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadpaymentfile\n      description: Montran Upload a payment file\n      hints:\n    \
  \    readOnly: false\n        destructive: false\n        idempotent: false\n      call: montran.uploadpaymentfile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfilestatus\n      description: Montran Get file processing status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: montran.getfilestatus\n      with:\n        fileId: tools.fileId\n      inputParameters:\n      - name: fileId\n        type: string\n        description: Unique identifier of the uploaded file\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbeneficiaries\n      description: Montran List beneficiaries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: montran.listbeneficiaries\n      with:\n        page: tools.page\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: page\n        type: integer\n\
  \        description: page\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbeneficiary\n      description: Montran Create a beneficiary\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: montran.createbeneficiary\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MONTRAN_TOKEN: MONTRAN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/montran/refs/heads/main/capabilities/montran-capability.yaml
tags:
- Montran
- API
tools:
- description: Montran List corporate payments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcorporatepayments
- description: Montran Create a corporate payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcorporatepayment
- description: Montran Get payment details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcorporatepayment
- description: Montran Approve a payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: approvepayment
- description: Montran Reject a payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rejectpayment
- description: Montran List bank accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbankaccounts
- description: Montran Get bank account details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbankaccount
- description: Montran List account transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounttransactions
- description: Montran Upload a payment file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadpaymentfile
- description: Montran Get file processing status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfilestatus
- description: Montran List beneficiaries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbeneficiaries
- description: Montran Create a beneficiary
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbeneficiary
---

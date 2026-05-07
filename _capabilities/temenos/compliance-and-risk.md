---
categories: []
consumed_apis: []
description: Compliance and financial crime management workflow combining Financial Crime Mitigation and core Transact APIs. Used by compliance officers, AML analysts, and risk teams to screen customers, monitor transactions, and manage regulatory risk.
layout: capability
name: Temenos Compliance And Risk
operations:
- description: Get customer AML risk score
  method: GET
  name: get-risk-score
  path: /v1/customers/{customerId}/risk-score
- description: Compute updated customer risk score
  method: POST
  name: compute-risk-score
  path: /v1/customers/{customerId}/risk-score
- description: Get sanctions alerts for a customer
  method: GET
  name: get-sanction-alerts
  path: /v1/customers/{customerId}/sanction-alerts
- description: List all sanctions alerts
  method: GET
  name: list-sanction-alerts
  path: /v1/sanction-alerts
- description: Screen a customer for onboarding compliance
  method: POST
  name: screen-customer
  path: /v1/screenings/onboarding
- description: Scan a transaction for AML indicators
  method: POST
  name: scan-transaction
  path: /v1/transactions/scan
- description: List transaction monitoring alerts
  method: GET
  name: list-alerts
  path: /v1/monitoring-alerts
- description: Get alert details
  method: GET
  name: get-alert
  path: /v1/monitoring-alerts/{alertId}
- description: Update alert status or resolution
  method: PUT
  name: update-alert
  path: /v1/monitoring-alerts/{alertId}
- description: Get customer details for compliance review
  method: GET
  name: get-customer
  path: /v1/customers
personas: []
provider_name: Temenos
provider_slug: temenos
search_terms:
- compute risk score
- get customer for review
- cloud banking
- wealth management
- kyc
- scan transaction
- resolve monitoring alert
- get customer risk score
- scan a transaction for aml indicators
- customer sanction screening alerts
- customer risk scoring
- list transaction monitoring alerts
- get customer aml risk score
- list all sanctions alerts
- financial crime
- onboarding kyc screening
- digital banking
- run full kyc and sanctions screening for a new customer
- screen onboarding customer
- compliance
- get aml risk score for a customer
- fintech
- transaction monitoring alerts
- scan a transaction message for aml indicators and suspicious patterns
- all sanction screening alerts
- transaction aml scanning
- list sanction alerts
- financial services
- customer lookups for compliance context
- get sanctions screening alerts for a specific customer
- get customer profile for compliance review context
- get customer
- get risk score
- list monitoring alerts
- aml
- get sanctions alerts for a customer
- list alerts
- get alert details
- update the status or resolution of a monitoring alert
- get alert
- update alert status or resolution
- single monitoring alert
- get sanction alerts
- sanctions screening
- screen a customer for onboarding compliance
- compute and refresh a customer risk score
- open banking
- get customer sanction alerts
- banking
- payments
- get customer details for compliance review
- list open aml transaction monitoring alerts
- screen customer
- scan transaction for aml
- list all sanctions alerts across all customers
- compute customer risk score
- compute updated customer risk score
- risk management
- core banking
- update alert
slug: compliance-and-risk
source_filename: compliance-and-risk.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Temenos Compliance And Risk\n  description: Compliance and financial crime management workflow combining Financial Crime Mitigation and core Transact APIs.\n    Used by compliance officers, AML analysts, and risk teams to screen customers, monitor transactions, and manage regulatory\n    risk.\n  tags:\n  - Compliance\n  - AML\n  - Risk Management\n  - KYC\n  - Sanctions Screening\n  - Financial Crime\n  - Banking\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TEMENOS_FCM_TOKEN: TEMENOS_FCM_TOKEN\n    TEMENOS_TRANSACT_TOKEN: TEMENOS_TRANSACT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: fcm\n    baseUri: https://api.temenos.com/fcm/v1\n    description: Temenos Financial Crime Mitigation API\n    authentication:\n      type: bearer\n      token: '{{TEMENOS_FCM_TOKEN}}'\n    resources:\n    - name: risk-scores\n      path: /customers/{customerId}/riskScore\n      description:\
  \ Customer risk scoring\n      operations:\n      - name: get-customer-risk-score\n        method: GET\n        description: Get customer risk score\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: compute-customer-risk-score\n        method: POST\n        description: Compute updated customer risk score\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        body:\n          type: json\n          data:\n            scoreType: '{{tools.scoreType}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sanction-alerts\n      path:\
  \ /customers/{customerId}/sanctionAlerts\n      description: Sanction screening alerts\n      operations:\n      - name: get-customer-sanction-alerts\n        method: GET\n        description: Get sanction alerts for a customer\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: all-sanction-alerts\n      path: /sanctionAlerts\n      description: All sanction alerts\n      operations:\n      - name: list-all-sanction-alerts\n        method: GET\n        description: List all sanctions alerts across customers\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n    - name: onboarding-screening\n      path: /screenings/onboarding\n      description: Onboarding KYC screening\n      operations:\n      - name: screen-onboarding-customer\n        method: POST\n        description: Screen a customer during onboarding\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n            checkTypes: '{{tools.checkTypes}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transaction-scanning\n      path: /transactions/scan\n      description: Transaction message scanning\n      operations:\n      - name: scan-transaction-message\n        method: POST\n        description: Scan a transaction message for AML indicators\n        body:\n          type: json\n          data:\n            transactionId: '{{tools.transactionId}}'\n            message: '{{tools.message}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring-alerts\n      path: /alerts\n      description: Transaction monitoring alerts\n      operations:\n      - name: list-monitoring-alerts\n        method: GET\n        description: List transaction monitoring alerts\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-alert\n        method: GET\n        description: Get monitoring alert details\n        inputParameters:\n        - name: alertId\n          in: path\n          type: string\n          required: true\n          description: Alert identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: update-alert\n        method: PUT\n        description: Update alert status or resolution\n        inputParameters:\n        - name: alertId\n          in: path\n          type: string\n          required: true\n          description: Alert identifier\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            resolution: '{{tools.resolution}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: transact\n    baseUri: https://api.temenos.com/transact/v1\n    description: Temenos Transact core banking API\n    authentication:\n      type: bearer\n      token: '{{TEMENOS_TRANSACT_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /holdings/accounts\n      description: Customer account arrangements\n      operations:\n      - name: list-accounts\n        method: GET\n \
  \       description: List customer accounts with optional filtering\n        inputParameters:\n        - name: customerId\n          in: query\n          type: string\n          required: false\n          description: Filter accounts by customer identifier\n        - name: accountType\n          in: query\n          type: string\n          required: false\n          description: Filter by account type (CURRENT, SAVINGS, DEPOSIT, LOAN)\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page\n        - name: page_start\n          in: query\n          type: integer\n          required: false\n          description: Starting record number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new account arrangement\n        body:\n          type:\
  \ json\n          data:\n            customerId: '{{tools.customerId}}'\n            accountType: '{{tools.accountType}}'\n            currency: '{{tools.currency}}'\n            productId: '{{tools.productId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-detail\n      path: /holdings/accounts/{accountId}\n      description: Single account operations\n      operations:\n      - name: get-account\n        method: GET\n        description: Get account details\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-account\n        method: PUT\n        description: Update account arrangement\n        inputParameters:\n      \
  \  - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-balances\n      path: /holdings/accounts/{accountId}/balances\n      description: Account balance information\n      operations:\n      - name: get-account-balances\n        method: GET\n        description: Get account balances\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-transactions\n      path: /holdings/accounts/{accountId}/transactions\n\
  \      description: Account transaction history\n      operations:\n      - name: list-account-transactions\n        method: GET\n        description: List account transactions\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /party/customers\n      description: Customer management\n      operations:\n      - name: list-customers\n        method: GET\n        description: List customers\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create new customer\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            customerType: '{{tools.customerType}}'\n            email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-detail\n      path: /party/customers/{customerId}\n      description: Single customer operations\n      operations:\n      - name: get-customer\n        method: GET\n        description: Get customer details\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique customer identifier\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-orders\n      path: /order/paymentOrders\n      description: Payment order management\n      operations:\n      - name: list-payment-orders\n        method: GET\n        description: List payment orders\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment-order\n        method: POST\n        description: Create payment order\n        body:\n          type: json\n          data:\n            debitAccountId: '{{tools.debitAccountId}}'\n            creditAccountId: '{{tools.creditAccountId}}'\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            paymentType: '{{tools.paymentType}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: compliance-risk-api\n    description: Unified REST API for Temenos compliance and risk management.\n    resources:\n    - path: /v1/customers/{customerId}/risk-score\n      name: risk-score\n      description: Customer risk scoring\n      operations:\n      - method: GET\n        name: get-risk-score\n        description: Get customer AML risk score\n        call: fcm.get-customer-risk-score\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: compute-risk-score\n        description: Compute updated customer risk score\n        call: fcm.compute-customer-risk-score\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/customers/{customerId}/sanction-alerts\n      name: sanction-alerts\n      description: Customer sanction screening alerts\n      operations:\n      - method: GET\n        name: get-sanction-alerts\n        description: Get sanctions alerts for a customer\n        call: fcm.get-customer-sanction-alerts\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sanction-alerts\n      name: all-sanction-alerts\n      description: All sanction screening alerts\n      operations:\n      - method: GET\n        name: list-sanction-alerts\n        description: List all sanctions alerts\n        call: fcm.list-all-sanction-alerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/screenings/onboarding\n      name: onboarding-screening\n      description: Onboarding KYC screening\n      operations:\n      - method: POST\n        name: screen-customer\n \
  \       description: Screen a customer for onboarding compliance\n        call: fcm.screen-onboarding-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions/scan\n      name: transaction-scanning\n      description: Transaction AML scanning\n      operations:\n      - method: POST\n        name: scan-transaction\n        description: Scan a transaction for AML indicators\n        call: fcm.scan-transaction-message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitoring-alerts\n      name: monitoring-alerts\n      description: Transaction monitoring alerts\n      operations:\n      - method: GET\n        name: list-alerts\n        description: List transaction monitoring alerts\n        call: fcm.list-monitoring-alerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitoring-alerts/{alertId}\n      name: alert-detail\n      description: Single\
  \ monitoring alert\n      operations:\n      - method: GET\n        name: get-alert\n        description: Get alert details\n        call: fcm.get-alert\n        with:\n          alertId: rest.alertId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-alert\n        description: Update alert status or resolution\n        call: fcm.update-alert\n        with:\n          alertId: rest.alertId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers\n      name: customers\n      description: Customer lookups for compliance context\n      operations:\n      - method: GET\n        name: get-customer\n        description: Get customer details for compliance review\n        call: transact.get-customer\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: compliance-risk-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted compliance and financial crime management.\n    tools:\n    - name: get-customer-risk-score\n      description: Get AML risk score for a customer\n      hints:\n        readOnly: true\n        openWorld: false\n      call: fcm.get-customer-risk-score\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: compute-customer-risk-score\n      description: Compute and refresh a customer risk score\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: fcm.compute-customer-risk-score\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: screen-onboarding-customer\n      description: Run full KYC and sanctions screening for a new customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: fcm.screen-onboarding-customer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer-sanction-alerts\n      description: Get sanctions screening alerts for a specific customer\n      hints:\n        readOnly: true\n        openWorld: false\n      call: fcm.get-customer-sanction-alerts\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sanction-alerts\n      description: List all sanctions alerts across all customers\n      hints:\n        readOnly: true\n        openWorld: false\n      call: fcm.list-all-sanction-alerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scan-transaction-for-aml\n      description: Scan a transaction message for AML indicators and suspicious patterns\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: fcm.scan-transaction-message\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-monitoring-alerts\n      description: List open AML transaction monitoring alerts\n      hints:\n        readOnly: true\n        openWorld: false\n      call: fcm.list-monitoring-alerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resolve-monitoring-alert\n      description: Update the status or resolution of a monitoring alert\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: fcm.update-alert\n      with:\n        alertId: tools.alertId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer-for-review\n      description: Get customer profile for compliance review context\n      hints:\n        readOnly: true\n        openWorld: false\n      call: transact.get-customer\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/temenos/refs/heads/main/capabilities/compliance-and-risk.yaml
tags:
- Compliance
- AML
- Risk Management
- KYC
- Sanctions Screening
- Financial Crime
- Banking
tools:
- description: Get AML risk score for a customer
  hints:
    openWorld: false
    readOnly: true
  name: get-customer-risk-score
- description: Compute and refresh a customer risk score
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: compute-customer-risk-score
- description: Run full KYC and sanctions screening for a new customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: screen-onboarding-customer
- description: Get sanctions screening alerts for a specific customer
  hints:
    openWorld: false
    readOnly: true
  name: get-customer-sanction-alerts
- description: List all sanctions alerts across all customers
  hints:
    openWorld: false
    readOnly: true
  name: list-sanction-alerts
- description: Scan a transaction message for AML indicators and suspicious patterns
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: scan-transaction-for-aml
- description: List open AML transaction monitoring alerts
  hints:
    openWorld: false
    readOnly: true
  name: list-monitoring-alerts
- description: Update the status or resolution of a monitoring alert
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resolve-monitoring-alert
- description: Get customer profile for compliance review context
  hints:
    openWorld: false
    readOnly: true
  name: get-customer-for-review
---

---
categories: []
consumed_apis:
- fcm
- transact
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
- scan a transaction for aml indicators
- get customer risk score
- list monitoring alerts
- core banking
- scan transaction
- get sanctions screening alerts for a specific customer
- transaction aml scanning
- get aml risk score for a customer
- compute and refresh a customer risk score
- get customer for review
- fintech
- compute customer risk score
- update the status or resolution of a monitoring alert
- open banking
- get alert
- screen a customer for onboarding compliance
- sanctions screening
- compute risk score
- risk management
- get customer aml risk score
- compute updated customer risk score
- update alert
- get risk score
- get alert details
- kyc
- run full kyc and sanctions screening for a new customer
- scan a transaction message for aml indicators and suspicious patterns
- aml
- customer lookups for compliance context
- wealth management
- get customer sanction alerts
- list sanction alerts
- all sanction screening alerts
- screen onboarding customer
- list transaction monitoring alerts
- update alert status or resolution
- screen customer
- get customer
- transaction monitoring alerts
- payments
- financial crime
- customer sanction screening alerts
- list alerts
- single monitoring alert
- banking
- get sanctions alerts for a customer
- onboarding kyc screening
- cloud banking
- get customer details for compliance review
- scan transaction for aml
- list all sanctions alerts across all customers
- list all sanctions alerts
- digital banking
- compliance
- get customer profile for compliance review context
- resolve monitoring alert
- financial services
- customer risk scoring
- list open aml transaction monitoring alerts
- get sanction alerts
slug: compliance-and-risk
source_filename: compliance-and-risk.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Temenos Compliance And Risk\"\n  description: \"Compliance and financial crime management workflow combining Financial Crime Mitigation and core Transact APIs. Used by compliance officers, AML analysts, and risk teams to screen customers, monitor transactions, and manage regulatory risk.\"\n  tags:\n    - Compliance\n    - AML\n    - Risk Management\n    - KYC\n    - Sanctions Screening\n    - Financial Crime\n    - Banking\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TEMENOS_FCM_TOKEN: TEMENOS_FCM_TOKEN\n      TEMENOS_TRANSACT_TOKEN: TEMENOS_TRANSACT_TOKEN\n\ncapability:\n  consumes:\n    - import: fcm\n      location: ./shared/financial-crime-mitigation.yaml\n    - import: transact\n      location: ./shared/transact.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: compliance-risk-api\n      description: \"Unified REST API for Temenos compliance\
  \ and risk management.\"\n      resources:\n        - path: /v1/customers/{customerId}/risk-score\n          name: risk-score\n          description: \"Customer risk scoring\"\n          operations:\n            - method: GET\n              name: get-risk-score\n              description: \"Get customer AML risk score\"\n              call: \"fcm.get-customer-risk-score\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: compute-risk-score\n              description: \"Compute updated customer risk score\"\n              call: \"fcm.compute-customer-risk-score\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customers/{customerId}/sanction-alerts\n          name: sanction-alerts\n\
  \          description: \"Customer sanction screening alerts\"\n          operations:\n            - method: GET\n              name: get-sanction-alerts\n              description: \"Get sanctions alerts for a customer\"\n              call: \"fcm.get-customer-sanction-alerts\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sanction-alerts\n          name: all-sanction-alerts\n          description: \"All sanction screening alerts\"\n          operations:\n            - method: GET\n              name: list-sanction-alerts\n              description: \"List all sanctions alerts\"\n              call: \"fcm.list-all-sanction-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/screenings/onboarding\n          name: onboarding-screening\n          description: \"Onboarding\
  \ KYC screening\"\n          operations:\n            - method: POST\n              name: screen-customer\n              description: \"Screen a customer for onboarding compliance\"\n              call: \"fcm.screen-onboarding-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/transactions/scan\n          name: transaction-scanning\n          description: \"Transaction AML scanning\"\n          operations:\n            - method: POST\n              name: scan-transaction\n              description: \"Scan a transaction for AML indicators\"\n              call: \"fcm.scan-transaction-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/monitoring-alerts\n          name: monitoring-alerts\n          description: \"Transaction monitoring alerts\"\n          operations:\n            - method: GET\n              name: list-alerts\n\
  \              description: \"List transaction monitoring alerts\"\n              call: \"fcm.list-monitoring-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/monitoring-alerts/{alertId}\n          name: alert-detail\n          description: \"Single monitoring alert\"\n          operations:\n            - method: GET\n              name: get-alert\n              description: \"Get alert details\"\n              call: \"fcm.get-alert\"\n              with:\n                alertId: \"rest.alertId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-alert\n              description: \"Update alert status or resolution\"\n              call: \"fcm.update-alert\"\n              with:\n                alertId: \"rest.alertId\"\n              outputParameters:\n                - type: object\n              \
  \    mapping: \"$.\"\n\n        - path: /v1/customers\n          name: customers\n          description: \"Customer lookups for compliance context\"\n          operations:\n            - method: GET\n              name: get-customer\n              description: \"Get customer details for compliance review\"\n              call: \"transact.get-customer\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: compliance-risk-mcp\n      transport: http\n      description: \"MCP server for AI-assisted compliance and financial crime management.\"\n      tools:\n        - name: get-customer-risk-score\n          description: \"Get AML risk score for a customer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"fcm.get-customer-risk-score\"\n          with:\n            customerId:\
  \ \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: compute-customer-risk-score\n          description: \"Compute and refresh a customer risk score\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"fcm.compute-customer-risk-score\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: screen-onboarding-customer\n          description: \"Run full KYC and sanctions screening for a new customer\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"fcm.screen-onboarding-customer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-customer-sanction-alerts\n          description: \"Get sanctions\
  \ screening alerts for a specific customer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"fcm.get-customer-sanction-alerts\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sanction-alerts\n          description: \"List all sanctions alerts across all customers\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"fcm.list-all-sanction-alerts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: scan-transaction-for-aml\n          description: \"Scan a transaction message for AML indicators and suspicious patterns\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"fcm.scan-transaction-message\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: list-monitoring-alerts\n          description: \"List open AML transaction monitoring alerts\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"fcm.list-monitoring-alerts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: resolve-monitoring-alert\n          description: \"Update the status or resolution of a monitoring alert\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"fcm.update-alert\"\n          with:\n            alertId: \"tools.alertId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-customer-for-review\n          description: \"Get customer profile for compliance review context\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"transact.get-customer\"\
  \n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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

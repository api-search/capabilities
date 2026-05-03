---
categories: []
consumed_apis:
- remitian-tax
description: Workflow capability for embedding automated tax payment processing into tax software and accounting platforms. Combines payment lifecycle management (initiation, validation, confirmation), jurisdiction lookup, account management, audit logging, and webhook configuration into a single integration. Used by tax software providers, accounting firms, and ERP integrators to replace manual government portal logins with automated payment infrastructure.
layout: capability
name: Remitian Tax Payment Automation
operations:
- description: List tax payments with filtering
  method: GET
  name: list-payments
  path: /v1/payments
- description: Initiate a new tax payment
  method: POST
  name: initiate-payment
  path: /v1/payments
- description: Get full payment details and status
  method: GET
  name: get-payment
  path: /v1/payments/{paymentId}
- description: Validate payment against jurisdiction rules
  method: POST
  name: validate-payment
  path: /v1/payments/{paymentId}/validate
- description: Confirm payment for processing
  method: POST
  name: confirm-payment
  path: /v1/payments/{paymentId}/confirm
- description: Browse supported tax jurisdictions
  method: GET
  name: list-jurisdictions
  path: /v1/jurisdictions
- description: List registered client accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Register a new client account
  method: POST
  name: create-account
  path: /v1/accounts
- description: List payment audit log entries
  method: GET
  name: list-audit-logs
  path: /v1/audit-logs
- description: List webhook subscriptions
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Create a webhook subscription
  method: POST
  name: create-webhook
  path: /v1/webhooks
personas: []
provider_name: Remitian
provider_slug: remitian
search_terms:
- automation
- list tax payments filtered by jurisdiction, status, and date range for reconciliation
- list tax payments with filtering
- list payments
- get payment requirements, accepted tax types, and routing for a jurisdiction
- initiate payment
- accounting
- validate payment
- register a webhook endpoint to receive real-time payment status events
- get jurisdiction
- remitian
- list client accounts registered for tax payment processing
- individual tax payment
- register a new client account with bank connection for tax payments
- confirm payment
- create webhook
- browse supported tax jurisdictions by country and type
- confirm a validated payment — irreversible, routes to tax authority
- list active webhook subscriptions for payment event notifications
- register a new client account
- list webhook subscriptions
- client tax payment accounts
- list audit logs
- browse supported tax jurisdictions
- payment validation
- retrieve bank-grade audit logs for payment compliance and reconciliation
- validate payment against jurisdiction rules
- list jurisdictions
- payments
- webhooks
- tax payment lifecycle management
- payment confirmation
- create account
- cancel a payment that has not yet been confirmed or processed
- list registered client accounts
- list payment audit log entries
- list accounts
- payment event webhook subscriptions
- list webhooks
- run jurisdiction-specific validation to check payment readiness
- create a webhook subscription
- supported tax jurisdictions
- cancel payment
- initiate a new tax payment
- confirm payment for processing
- embedded payments
- get complete payment details including validation results and status
- get payment
- fintech
- tax
- initiate a tax payment to a jurisdiction from a client account
- bank-grade payment audit logs
- get full payment details and status
slug: tax-payment-automation
source_filename: tax-payment-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Remitian Tax Payment Automation\n  description: >-\n    Workflow capability for embedding automated tax payment processing into\n    tax software and accounting platforms. Combines payment lifecycle management\n    (initiation, validation, confirmation), jurisdiction lookup, account\n    management, audit logging, and webhook configuration into a single\n    integration. Used by tax software providers, accounting firms, and ERP\n    integrators to replace manual government portal logins with automated\n    payment infrastructure.\n  tags:\n    - Remitian\n    - Tax\n    - Payments\n    - Fintech\n    - Accounting\n    - Embedded Payments\n    - Automation\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REMITIAN_API_KEY: REMITIAN_API_KEY\n\ncapability:\n  consumes:\n    - import: remitian-tax\n      location: ./shared/tax-payment.yaml\n\n  exposes:\n    - type: rest\n      port:\
  \ 8080\n      namespace: remitian-automation-api\n      description: \"Unified REST API for embedded tax payment automation.\"\n      resources:\n        - path: /v1/payments\n          name: payments\n          description: Tax payment lifecycle management\n          operations:\n            - method: GET\n              name: list-payments\n              description: List tax payments with filtering\n              call: \"remitian-tax.list-payments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: initiate-payment\n              description: Initiate a new tax payment\n              call: \"remitian-tax.initiate-payment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments/{paymentId}\n          name: payment\n          description: Individual tax payment\n          operations:\n            - method: GET\n  \
  \            name: get-payment\n              description: Get full payment details and status\n              call: \"remitian-tax.get-payment\"\n              with:\n                paymentId: \"rest.paymentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments/{paymentId}/validate\n          name: payment-validation\n          description: Payment validation\n          operations:\n            - method: POST\n              name: validate-payment\n              description: Validate payment against jurisdiction rules\n              call: \"remitian-tax.validate-payment\"\n              with:\n                paymentId: \"rest.paymentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments/{paymentId}/confirm\n          name: payment-confirmation\n          description: Payment confirmation\n          operations:\n            - method:\
  \ POST\n              name: confirm-payment\n              description: Confirm payment for processing\n              call: \"remitian-tax.confirm-payment\"\n              with:\n                paymentId: \"rest.paymentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jurisdictions\n          name: jurisdictions\n          description: Supported tax jurisdictions\n          operations:\n            - method: GET\n              name: list-jurisdictions\n              description: Browse supported tax jurisdictions\n              call: \"remitian-tax.list-jurisdictions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts\n          name: accounts\n          description: Client tax payment accounts\n          operations:\n            - method: GET\n              name: list-accounts\n              description: List registered client accounts\n\
  \              call: \"remitian-tax.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-account\n              description: Register a new client account\n              call: \"remitian-tax.create-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audit-logs\n          name: audit-logs\n          description: Bank-grade payment audit logs\n          operations:\n            - method: GET\n              name: list-audit-logs\n              description: List payment audit log entries\n              call: \"remitian-tax.list-audit-logs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks\n          name: webhooks\n          description: Payment event webhook subscriptions\n          operations:\n            - method:\
  \ GET\n              name: list-webhooks\n              description: List webhook subscriptions\n              call: \"remitian-tax.list-webhooks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: Create a webhook subscription\n              call: \"remitian-tax.create-webhook\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: remitian-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted tax payment automation and reconciliation.\"\n      tools:\n        - name: list-payments\n          description: List tax payments filtered by jurisdiction, status, and date range for reconciliation\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"remitian-tax.list-payments\"\n\
  \          with:\n            jurisdictionId: \"tools.jurisdictionId\"\n            status: \"tools.status\"\n            dateFrom: \"tools.dateFrom\"\n            dateTo: \"tools.dateTo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: initiate-payment\n          description: Initiate a tax payment to a jurisdiction from a client account\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"remitian-tax.initiate-payment\"\n          with:\n            amount: \"tools.amount\"\n            currency: \"tools.currency\"\n            taxType: \"tools.taxType\"\n            taxPeriod: \"tools.taxPeriod\"\n            jurisdictionId: \"tools.jurisdictionId\"\n            accountId: \"tools.accountId\"\n            taxIdentifier: \"tools.taxIdentifier\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-payment\n          description:\
  \ Get complete payment details including validation results and status\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"remitian-tax.get-payment\"\n          with:\n            paymentId: \"tools.paymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-payment\n          description: Run jurisdiction-specific validation to check payment readiness\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"remitian-tax.validate-payment\"\n          with:\n            paymentId: \"tools.paymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: confirm-payment\n          description: Confirm a validated payment — irreversible, routes to tax authority\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"remitian-tax.confirm-payment\"\
  \n          with:\n            paymentId: \"tools.paymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-payment\n          description: Cancel a payment that has not yet been confirmed or processed\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"remitian-tax.cancel-payment\"\n          with:\n            paymentId: \"tools.paymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-jurisdictions\n          description: Browse supported tax jurisdictions by country and type\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"remitian-tax.list-jurisdictions\"\n          with:\n            country: \"tools.country\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n  \
  \      - name: get-jurisdiction\n          description: Get payment requirements, accepted tax types, and routing for a jurisdiction\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"remitian-tax.get-jurisdiction\"\n          with:\n            jurisdictionId: \"tools.jurisdictionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-accounts\n          description: List client accounts registered for tax payment processing\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"remitian-tax.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-account\n          description: Register a new client account with bank connection for tax payments\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"remitian-tax.create-account\"\n  \
  \        with:\n            name: \"tools.name\"\n            email: \"tools.email\"\n            taxIdentifier: \"tools.taxIdentifier\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-audit-logs\n          description: Retrieve bank-grade audit logs for payment compliance and reconciliation\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"remitian-tax.list-audit-logs\"\n          with:\n            paymentId: \"tools.paymentId\"\n            accountId: \"tools.accountId\"\n            eventType: \"tools.eventType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhooks\n          description: List active webhook subscriptions for payment event notifications\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"remitian-tax.list-webhooks\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n        - name: create-webhook\n          description: Register a webhook endpoint to receive real-time payment status events\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"remitian-tax.create-webhook\"\n          with:\n            url: \"tools.url\"\n            events: \"tools.events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/remitian/refs/heads/main/capabilities/tax-payment-automation.yaml
tags:
- Remitian
- Tax
- Payments
- Fintech
- Accounting
- Embedded Payments
- Automation
tools:
- description: List tax payments filtered by jurisdiction, status, and date range for reconciliation
  hints:
    openWorld: false
    readOnly: true
  name: list-payments
- description: Initiate a tax payment to a jurisdiction from a client account
  hints:
    destructive: false
    readOnly: false
  name: initiate-payment
- description: Get complete payment details including validation results and status
  hints:
    openWorld: false
    readOnly: true
  name: get-payment
- description: Run jurisdiction-specific validation to check payment readiness
  hints:
    openWorld: false
    readOnly: true
  name: validate-payment
- description: Confirm a validated payment — irreversible, routes to tax authority
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: confirm-payment
- description: Cancel a payment that has not yet been confirmed or processed
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-payment
- description: Browse supported tax jurisdictions by country and type
  hints:
    openWorld: true
    readOnly: true
  name: list-jurisdictions
- description: Get payment requirements, accepted tax types, and routing for a jurisdiction
  hints:
    openWorld: true
    readOnly: true
  name: get-jurisdiction
- description: List client accounts registered for tax payment processing
  hints:
    openWorld: false
    readOnly: true
  name: list-accounts
- description: Register a new client account with bank connection for tax payments
  hints:
    destructive: false
    readOnly: false
  name: create-account
- description: Retrieve bank-grade audit logs for payment compliance and reconciliation
  hints:
    openWorld: false
    readOnly: true
  name: list-audit-logs
- description: List active webhook subscriptions for payment event notifications
  hints:
    openWorld: false
    readOnly: true
  name: list-webhooks
- description: Register a webhook endpoint to receive real-time payment status events
  hints:
    destructive: false
    readOnly: false
  name: create-webhook
---

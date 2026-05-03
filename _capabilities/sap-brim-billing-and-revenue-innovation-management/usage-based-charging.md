---
categories: []
consumed_apis:
- sap-brim-convergent-charging
description: Workflow capability for real-time usage rating, charging, and balance management in SAP BRIM Convergent Charging. Enables usage event submission, real-time rating against pricing plans, prepaid balance management, and pricing plan governance. Used by telecom engineers, IoT billing teams, and revenue managers.
layout: capability
name: SAP BRIM Usage-Based Charging
operations:
- description: Get current account balance.
  method: GET
  name: get-balance
  path: /v1/balances/{accountId}
- description: List available pricing plans.
  method: GET
  name: list-pricing-plans
  path: /v1/pricing-plans
personas: []
provider_name: SAP BRIM (Billing and Revenue Innovation Management)
provider_slug: sap-brim-billing-and-revenue-innovation-management
search_terms:
- account balance inquiries.
- get balance
- usage-based pricing
- get detailed configuration of a specific pricing plan.
- sap
- get account balance
- list pricing plans
- list available pricing plans.
- pricing plan catalog.
- enterprise
- revenue management
- rate usage batch
- rate a single usage event against the applicable sap brim pricing plan.
- list available pricing plans and rate cards in the charging engine.
- order to cash
- apply a credit or debit adjustment to a customer account balance.
- rate usage event
- charging
- billing
- adjust balance
- get pricing plan
- get the current prepaid or postpaid balance for a customer account.
- rate a batch of usage events in a single request for high-throughput scenarios.
- subscription management
- get current account balance.
slug: usage-based-charging
source_filename: usage-based-charging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP BRIM Usage-Based Charging\"\n  description: \"Workflow capability for real-time usage rating, charging, and balance management in SAP BRIM Convergent Charging. Enables usage event submission, real-time rating against pricing plans, prepaid balance management, and pricing plan governance. Used by telecom engineers, IoT billing teams, and revenue managers.\"\n  tags:\n    - Billing\n    - Charging\n    - Revenue Management\n    - SAP\n    - Usage-Based Pricing\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_BRIM_OAUTH_TOKEN: SAP_BRIM_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: sap-brim-convergent-charging\n      location: ./shared/convergent-charging.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: sap-brim-usage-charging-api\n      description: \"Unified REST API for SAP BRIM usage-based charging and balance management.\"\n      resources:\n\
  \        - path: /v1/balances/{accountId}\n          name: account-balance\n          description: \"Account balance inquiries.\"\n          operations:\n            - method: GET\n              name: get-balance\n              description: \"Get current account balance.\"\n              call: \"sap-brim-convergent-charging.get-balance\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pricing-plans\n          name: pricing-plans\n          description: \"Pricing plan catalog.\"\n          operations:\n            - method: GET\n              name: list-pricing-plans\n              description: \"List available pricing plans.\"\n              call: \"sap-brim-convergent-charging.list-pricing-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace:\
  \ sap-brim-usage-charging-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP BRIM usage-based charging operations.\"\n      tools:\n        - name: rate-usage-event\n          description: \"Rate a single usage event against the applicable SAP BRIM pricing plan.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"sap-brim-convergent-charging.rate-usage-event\"\n          with:\n            accountId: \"tools.accountId\"\n            serviceType: \"tools.serviceType\"\n            quantity: \"tools.quantity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: rate-usage-batch\n          description: \"Rate a batch of usage events in a single request for high-throughput scenarios.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"sap-brim-convergent-charging.rate-usage-batch\"\n          with:\n            events:\
  \ \"tools.events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-balance\n          description: \"Get the current prepaid or postpaid balance for a customer account.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sap-brim-convergent-charging.get-account-balance\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: adjust-balance\n          description: \"Apply a credit or debit adjustment to a customer account balance.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"sap-brim-convergent-charging.adjust-balance\"\n          with:\n            accountId: \"tools.accountId\"\n            amount: \"tools.amount\"\n            adjustmentType: \"tools.adjustmentType\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n        - name: list-pricing-plans\n          description: \"List available pricing plans and rate cards in the charging engine.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-brim-convergent-charging.list-pricing-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pricing-plan\n          description: \"Get detailed configuration of a specific pricing plan.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sap-brim-convergent-charging.get-pricing-plan\"\n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-brim-billing-and-revenue-innovation-management/refs/heads/main/capabilities/usage-based-charging.yaml
tags:
- Billing
- Charging
- Revenue Management
- SAP
- Usage-Based Pricing
tools:
- description: Rate a single usage event against the applicable SAP BRIM pricing plan.
  hints:
    idempotent: false
    readOnly: false
  name: rate-usage-event
- description: Rate a batch of usage events in a single request for high-throughput scenarios.
  hints:
    idempotent: false
    readOnly: false
  name: rate-usage-batch
- description: Get the current prepaid or postpaid balance for a customer account.
  hints:
    openWorld: false
    readOnly: true
  name: get-account-balance
- description: Apply a credit or debit adjustment to a customer account balance.
  hints:
    idempotent: false
    readOnly: false
  name: adjust-balance
- description: List available pricing plans and rate cards in the charging engine.
  hints:
    openWorld: true
    readOnly: true
  name: list-pricing-plans
- description: Get detailed configuration of a specific pricing plan.
  hints:
    openWorld: false
    readOnly: true
  name: get-pricing-plan
---

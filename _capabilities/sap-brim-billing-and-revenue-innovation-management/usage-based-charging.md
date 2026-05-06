---
categories: []
consumed_apis: []
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
- get balance
- rate a single usage event against the applicable sap brim pricing plan.
- get account balance
- charging
- get the current prepaid or postpaid balance for a customer account.
- list available pricing plans.
- rate usage event
- list pricing plans
- revenue management
- billing
- enterprise
- rate usage batch
- order to cash
- get detailed configuration of a specific pricing plan.
- get current account balance.
- apply a credit or debit adjustment to a customer account balance.
- get pricing plan
- subscription management
- sap
- rate a batch of usage events in a single request for high-throughput scenarios.
- usage-based pricing
- adjust balance
- list available pricing plans and rate cards in the charging engine.
- account balance inquiries.
- pricing plan catalog.
slug: usage-based-charging
source_filename: usage-based-charging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP BRIM Usage-Based Charging\n  description: Workflow capability for real-time usage rating, charging, and balance management in SAP BRIM Convergent Charging.\n    Enables usage event submission, real-time rating against pricing plans, prepaid balance management, and pricing plan governance.\n    Used by telecom engineers, IoT billing teams, and revenue managers.\n  tags:\n  - Billing\n  - Charging\n  - Revenue Management\n  - SAP\n  - Usage-Based Pricing\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_BRIM_OAUTH_TOKEN: SAP_BRIM_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sap-brim-convergent-charging\n    baseUri: https://api.sap.com/convergent-charging/v1\n    description: SAP BRIM Convergent Charging API for real-time usage rating and balance management.\n    authentication:\n      type: bearer\n      token: '{{SAP_BRIM_OAUTH_TOKEN}}'\n    resources:\n    - name:\
  \ rating\n      path: /rating/rate\n      description: Rate usage events against pricing plans.\n      operations:\n      - name: rate-usage-event\n        method: POST\n        description: Rate a single usage event against the applicable pricing plan.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            accountId: '{{tools.accountId}}'\n            serviceType: '{{tools.serviceType}}'\n            quantity: '{{tools.quantity}}'\n      - name: rate-usage-batch\n        method: POST\n        description: Rate a batch of usage events in a single request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            events: '{{tools.events}}'\n    - name: balances\n      path: /balances\n      description: Account balance\
  \ inquiries and adjustments.\n      operations:\n      - name: get-balance\n        method: GET\n        description: Get the current balance for an account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: The account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: adjust-balance\n        method: POST\n        description: Adjust the balance for an account (credit or debit).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            accountId: '{{tools.accountId}}'\n            amount: '{{tools.amount}}'\n            adjustmentType: '{{tools.adjustmentType}}'\n    - name: pricing-plans\n      path: /pricing-plans\n      description: Manage pricing plans\
  \ and rate cards.\n      operations:\n      - name: list-pricing-plans\n        method: GET\n        description: List available pricing plans.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pricing-plan\n        method: GET\n        description: Get details of a specific pricing plan.\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: The pricing plan identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: sap-brim-usage-charging-api\n    description: Unified REST API for SAP BRIM usage-based charging and balance management.\n    resources:\n    - path: /v1/balances/{accountId}\n      name: account-balance\n      description: Account balance inquiries.\n  \
  \    operations:\n      - method: GET\n        name: get-balance\n        description: Get current account balance.\n        call: sap-brim-convergent-charging.get-balance\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pricing-plans\n      name: pricing-plans\n      description: Pricing plan catalog.\n      operations:\n      - method: GET\n        name: list-pricing-plans\n        description: List available pricing plans.\n        call: sap-brim-convergent-charging.list-pricing-plans\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: sap-brim-usage-charging-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP BRIM usage-based charging operations.\n    tools:\n    - name: rate-usage-event\n      description: Rate a single usage event against the applicable SAP BRIM pricing plan.\n      hints:\n      \
  \  readOnly: false\n        idempotent: false\n      call: sap-brim-convergent-charging.rate-usage-event\n      with:\n        accountId: tools.accountId\n        serviceType: tools.serviceType\n        quantity: tools.quantity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rate-usage-batch\n      description: Rate a batch of usage events in a single request for high-throughput scenarios.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: sap-brim-convergent-charging.rate-usage-batch\n      with:\n        events: tools.events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-balance\n      description: Get the current prepaid or postpaid balance for a customer account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sap-brim-convergent-charging.get-account-balance\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: adjust-balance\n      description: Apply a credit or debit adjustment to a customer account balance.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: sap-brim-convergent-charging.adjust-balance\n      with:\n        accountId: tools.accountId\n        amount: tools.amount\n        adjustmentType: tools.adjustmentType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pricing-plans\n      description: List available pricing plans and rate cards in the charging engine.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-brim-convergent-charging.list-pricing-plans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pricing-plan\n      description: Get detailed configuration of a specific pricing plan.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sap-brim-convergent-charging.get-pricing-plan\n      with:\n\
  \        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

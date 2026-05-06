---
categories: []
consumed_apis: []
description: Recurring billing operations on Shift4. Combines plans, subscriptions, and customer/card management to support SaaS and membership-style billing.
layout: capability
name: Shift4 Subscription Billing
operations: []
personas: []
provider_name: Shift4 Payments
provider_slug: shift4-payments
search_terms:
- update or cancel a shift4 subscription.
- create subscription
- billing
- commerce
- create a shift4 subscription for a customer on a plan.
- create a shift4 plan.
- shift4
- plans
- update subscription
- create customer
- checkout
- payments
- subscriptions
- create plan
- customers
- list shift4 plans.
- create a shift4 customer.
- fintech
- list plans
slug: subscription-billing
source_filename: subscription-billing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Shift4 Subscription Billing\n  description: Recurring billing operations on Shift4. Combines plans, subscriptions, and customer/card management to support\n    SaaS and membership-style billing.\n  tags:\n  - Shift4\n  - Subscriptions\n  - Plans\n  - Billing\n  - Customers\n  created: '2026-05-05'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHIFT4_API_KEY: SHIFT4_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: shift4-customers\n    baseUri: https://api.shift4.com\n    authentication:\n      type: basic\n      username: '{{SHIFT4_API_KEY}}'\n      password: ''\n    resources:\n    - name: customers\n      path: /customers\n      operations:\n      - name: list-customers\n        method: GET\n        description: List customers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method:\
  \ POST\n        description: Create a customer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            description: '{{tools.description}}'\n    - name: customer\n      path: /customers/{customer}\n      operations:\n      - name: get-customer\n        method: GET\n        description: Retrieve a customer by ID.\n        inputParameters:\n        - name: customer\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-customer\n        method: POST\n        description: Update a customer.\n        inputParameters:\n        - name: customer\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: delete-customer\n        method: DELETE\n        description: Delete a customer.\n        inputParameters:\n        - name: customer\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: shift4-subscriptions\n    baseUri: https://api.shift4.com\n    authentication:\n      type: basic\n      username: '{{SHIFT4_API_KEY}}'\n      password: ''\n    resources:\n    - name: plans\n      path: /plans\n      operations:\n      - name: list-plans\n        method: GET\n        description: List plans.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-plan\n        method: POST\n        description: Create a plan.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plan\n      path: /plans/{plan}\n      operations:\n      - name: get-plan\n        method: GET\n        description: Retrieve a plan by ID.\n        inputParameters:\n        - name: plan\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-plan\n        method: POST\n        description: Update a plan.\n        inputParameters:\n        - name: plan\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /subscriptions\n      operations:\n      - name: create-subscription\n        method: POST\n        description: Create a subscription.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscription\n      path: /subscriptions/{subscription}\n      operations:\n      - name: get-subscription\n        method: GET\n        description: Retrieve a subscription by ID.\n        inputParameters:\n        - name: subscription\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-subscription\n        method: POST\n        description: Update or cancel a subscription.\n        inputParameters:\n        - name: subscription\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9081\n    namespace: shift4-subscription-billing-mcp\n\
  \    transport: http\n    description: MCP surface for managing Shift4 subscription billing.\n    tools:\n    - name: create-customer\n      description: Create a Shift4 customer.\n      hints:\n        readOnly: false\n        destructive: false\n      call: shift4-customers.create-customer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-plan\n      description: Create a Shift4 plan.\n      hints:\n        readOnly: false\n        destructive: false\n      call: shift4-subscriptions.create-plan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-subscription\n      description: Create a Shift4 subscription for a customer on a plan.\n      hints:\n        readOnly: false\n        destructive: false\n      call: shift4-subscriptions.create-subscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-subscription\n      description: Update or cancel a Shift4 subscription.\n\
  \      hints:\n        readOnly: false\n        destructive: false\n      call: shift4-subscriptions.update-subscription\n      with:\n        subscription: tools.subscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-plans\n      description: List Shift4 plans.\n      hints:\n        readOnly: true\n      call: shift4-subscriptions.list-plans\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shift4-payments/refs/heads/main/capabilities/subscription-billing.yaml
tags:
- Shift4
- Subscriptions
- Plans
- Billing
- Customers
tools:
- description: Create a Shift4 customer.
  hints:
    destructive: false
    readOnly: false
  name: create-customer
- description: Create a Shift4 plan.
  hints:
    destructive: false
    readOnly: false
  name: create-plan
- description: Create a Shift4 subscription for a customer on a plan.
  hints:
    destructive: false
    readOnly: false
  name: create-subscription
- description: Update or cancel a Shift4 subscription.
  hints:
    destructive: false
    readOnly: false
  name: update-subscription
- description: List Shift4 plans.
  hints:
    readOnly: true
  name: list-plans
---

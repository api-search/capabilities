---
categories: []
consumed_apis: []
description: You can use billing plans and subscriptions to create subscriptions that process recurring PayPal payments for physical or digital goods, or services. A plan includes pricing and billing cycle information that defines the amount and frequency of charge for a subscription. You can also define a fixed plan, such as a $5 basic plan or a volume- or graduated-based plan with pricing tiers based on the quantity purchased. For more information, see <a href="/docs/subscriptions/">Subscriptions Overview</a>.
layout: capability
name: Paypal Subscriptions
operations:
- description: Paypal Create plan
  method: POST
  name: plans-create
  path: /v1/billing/plans
- description: Paypal List plans
  method: GET
  name: plans-list
  path: /v1/billing/plans
- description: Paypal Show plan details
  method: GET
  name: plans-get
  path: /v1/billing/plans/{id}
- description: Paypal Update plan
  method: PATCH
  name: plans-patch
  path: /v1/billing/plans/{id}
- description: Paypal Activate plan
  method: POST
  name: plans-activate
  path: /v1/billing/plans/{id}/activate
- description: Paypal Deactivate plan
  method: POST
  name: plans-deactivate
  path: /v1/billing/plans/{id}/deactivate
- description: Paypal Update pricing
  method: POST
  name: plans-update-pricing-schemes
  path: /v1/billing/plans/{id}/update-pricing-schemes
- description: Paypal Create subscription
  method: POST
  name: subscriptions-create
  path: /v1/billing/subscriptions
- description: Paypal Show subscription details
  method: GET
  name: subscriptions-get
  path: /v1/billing/subscriptions/{id}
- description: Paypal Update subscription
  method: PATCH
  name: subscriptions-patch
  path: /v1/billing/subscriptions/{id}
- description: Paypal Revise plan or quantity of subscription
  method: POST
  name: subscriptions-revise
  path: /v1/billing/subscriptions/{id}/revise
- description: Paypal Suspend subscription
  method: POST
  name: subscriptions-suspend
  path: /v1/billing/subscriptions/{id}/suspend
- description: Paypal Cancel subscription
  method: POST
  name: subscriptions-cancel
  path: /v1/billing/subscriptions/{id}/cancel
- description: Paypal Activate subscription
  method: POST
  name: subscriptions-activate
  path: /v1/billing/subscriptions/{id}/activate
- description: Paypal Capture authorized payment on subscription
  method: POST
  name: subscriptions-capture
  path: /v1/billing/subscriptions/{id}/capture
- description: Paypal List transactions for subscription
  method: GET
  name: subscriptions-transactions
  path: /v1/billing/subscriptions/{id}/transactions
personas: []
provider_name: PayPal
provider_slug: paypal
search_terms:
- paypal update pricing
- disputes
- paypal create plan
- paypal cancel subscription
- subscriptions create
- invoices
- subscriptions get
- api
- subscriptions capture
- billing
- plans activate
- orders
- subscriptions
- paypal list plans
- paypal capture authorized payment on subscription
- paypal create subscription
- paypal show plan details
- paypal revise plan or quantity of subscription
- subscriptions patch
- paypal update subscription
- plans list
- paypal suspend subscription
- plans deactivate
- plans update pricing schemes
- paypal activate subscription
- tokens
- subscriptions revise
- paypal list transactions for subscription
- webhooks
- plans patch
- subscriptions cancel
- subscriptions transactions
- paypal update plan
- subscriptions activate
- paypal activate plan
- plans get
- paypal show subscription details
- payouts
- payments
- plans create
- subscriptions suspend
- paypal deactivate plan
- paypal
- commerce
slug: paypal-capability
source_filename: paypal-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Paypal Subscriptions\n  description: You can use billing plans and subscriptions to create subscriptions that process recurring PayPal payments\n    for physical or digital goods, or services. A plan includes pricing and billing cycle information that defines the amount\n    and frequency of charge for a subscription. You can also define a fixed plan, such as a $5 basic plan or a volume- or\n    graduated-based plan with pricing tiers based on the quantity purchased. For more information, see <a href=\"/docs/subscriptions/\">Subscriptions\n    Overview</a>.\n  tags:\n  - Paypal\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: paypal\n    baseUri: https://api-m.sandbox.paypal.com\n    description: Paypal Subscriptions HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PAYPAL_TOKEN}}'\n    resources:\n    - name: v1-billing-plans\n      path: /v1/billing/plans\n\
  \      operations:\n      - name: plans-create\n        method: POST\n        description: Paypal Create plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: plans-list\n        method: GET\n        description: Paypal List plans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-billing-plans-id\n      path: /v1/billing/plans/{id}\n      operations:\n      - name: plans-get\n        method: GET\n        description: Paypal Show plan details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: plans-patch\n        method: PATCH\n        description: Paypal Update plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-billing-plans-id-activate\n\
  \      path: /v1/billing/plans/{id}/activate\n      operations:\n      - name: plans-activate\n        method: POST\n        description: Paypal Activate plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-billing-plans-id-deactivate\n      path: /v1/billing/plans/{id}/deactivate\n      operations:\n      - name: plans-deactivate\n        method: POST\n        description: Paypal Deactivate plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-billing-plans-id-update-pricing-schemes\n      path: /v1/billing/plans/{id}/update-pricing-schemes\n      operations:\n      - name: plans-update-pricing-schemes\n        method: POST\n        description: Paypal Update pricing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: v1-billing-subscriptions\n      path: /v1/billing/subscriptions\n      operations:\n      - name: subscriptions-create\n        method: POST\n        description: Paypal Create subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-billing-subscriptions-id\n      path: /v1/billing/subscriptions/{id}\n      operations:\n      - name: subscriptions-get\n        method: GET\n        description: Paypal Show subscription details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: subscriptions-patch\n        method: PATCH\n        description: Paypal Update subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-billing-subscriptions-id-revise\n      path: /v1/billing/subscriptions/{id}/revise\n\
  \      operations:\n      - name: subscriptions-revise\n        method: POST\n        description: Paypal Revise plan or quantity of subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-billing-subscriptions-id-suspend\n      path: /v1/billing/subscriptions/{id}/suspend\n      operations:\n      - name: subscriptions-suspend\n        method: POST\n        description: Paypal Suspend subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-billing-subscriptions-id-cancel\n      path: /v1/billing/subscriptions/{id}/cancel\n      operations:\n      - name: subscriptions-cancel\n        method: POST\n        description: Paypal Cancel subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-billing-subscriptions-id-activate\n\
  \      path: /v1/billing/subscriptions/{id}/activate\n      operations:\n      - name: subscriptions-activate\n        method: POST\n        description: Paypal Activate subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-billing-subscriptions-id-capture\n      path: /v1/billing/subscriptions/{id}/capture\n      operations:\n      - name: subscriptions-capture\n        method: POST\n        description: Paypal Capture authorized payment on subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-billing-subscriptions-id-transactions\n      path: /v1/billing/subscriptions/{id}/transactions\n      operations:\n      - name: subscriptions-transactions\n        method: GET\n        description: Paypal List transactions for subscription\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: paypal-rest\n    description: REST adapter for Paypal Subscriptions.\n    resources:\n    - path: /v1/billing/plans\n      name: plans-create\n      operations:\n      - method: POST\n        name: plans-create\n        description: Paypal Create plan\n        call: paypal.plans-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/plans\n      name: plans-list\n      operations:\n      - method: GET\n        name: plans-list\n        description: Paypal List plans\n        call: paypal.plans-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/plans/{id}\n      name: plans-get\n      operations:\n      - method: GET\n        name: plans-get\n        description: Paypal Show plan details\n        call: paypal.plans-get\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/billing/plans/{id}\n      name: plans-patch\n      operations:\n      - method: PATCH\n        name: plans-patch\n        description: Paypal Update plan\n        call: paypal.plans-patch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/plans/{id}/activate\n      name: plans-activate\n      operations:\n      - method: POST\n        name: plans-activate\n        description: Paypal Activate plan\n        call: paypal.plans-activate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/plans/{id}/deactivate\n      name: plans-deactivate\n      operations:\n      - method: POST\n        name: plans-deactivate\n        description: Paypal Deactivate plan\n        call: paypal.plans-deactivate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/plans/{id}/update-pricing-schemes\n      name: plans-update-pricing-schemes\n\
  \      operations:\n      - method: POST\n        name: plans-update-pricing-schemes\n        description: Paypal Update pricing\n        call: paypal.plans-update-pricing-schemes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/subscriptions\n      name: subscriptions-create\n      operations:\n      - method: POST\n        name: subscriptions-create\n        description: Paypal Create subscription\n        call: paypal.subscriptions-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/subscriptions/{id}\n      name: subscriptions-get\n      operations:\n      - method: GET\n        name: subscriptions-get\n        description: Paypal Show subscription details\n        call: paypal.subscriptions-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/subscriptions/{id}\n      name: subscriptions-patch\n      operations:\n      - method:\
  \ PATCH\n        name: subscriptions-patch\n        description: Paypal Update subscription\n        call: paypal.subscriptions-patch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/subscriptions/{id}/revise\n      name: subscriptions-revise\n      operations:\n      - method: POST\n        name: subscriptions-revise\n        description: Paypal Revise plan or quantity of subscription\n        call: paypal.subscriptions-revise\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/subscriptions/{id}/suspend\n      name: subscriptions-suspend\n      operations:\n      - method: POST\n        name: subscriptions-suspend\n        description: Paypal Suspend subscription\n        call: paypal.subscriptions-suspend\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/subscriptions/{id}/cancel\n      name: subscriptions-cancel\n      operations:\n     \
  \ - method: POST\n        name: subscriptions-cancel\n        description: Paypal Cancel subscription\n        call: paypal.subscriptions-cancel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/subscriptions/{id}/activate\n      name: subscriptions-activate\n      operations:\n      - method: POST\n        name: subscriptions-activate\n        description: Paypal Activate subscription\n        call: paypal.subscriptions-activate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/subscriptions/{id}/capture\n      name: subscriptions-capture\n      operations:\n      - method: POST\n        name: subscriptions-capture\n        description: Paypal Capture authorized payment on subscription\n        call: paypal.subscriptions-capture\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing/subscriptions/{id}/transactions\n      name: subscriptions-transactions\n\
  \      operations:\n      - method: GET\n        name: subscriptions-transactions\n        description: Paypal List transactions for subscription\n        call: paypal.subscriptions-transactions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: paypal-mcp\n    transport: http\n    description: MCP adapter for Paypal Subscriptions for AI agent use.\n    tools:\n    - name: plans-create\n      description: Paypal Create plan\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paypal.plans-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: plans-list\n      description: Paypal List plans\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: paypal.plans-list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: plans-get\n      description: Paypal Show\
  \ plan details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: paypal.plans-get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: plans-patch\n      description: Paypal Update plan\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paypal.plans-patch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: plans-activate\n      description: Paypal Activate plan\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paypal.plans-activate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: plans-deactivate\n      description: Paypal Deactivate plan\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paypal.plans-deactivate\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: plans-update-pricing-schemes\n      description: Paypal Update pricing\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paypal.plans-update-pricing-schemes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscriptions-create\n      description: Paypal Create subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paypal.subscriptions-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscriptions-get\n      description: Paypal Show subscription details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: paypal.subscriptions-get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscriptions-patch\n      description: Paypal Update subscription\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: paypal.subscriptions-patch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscriptions-revise\n      description: Paypal Revise plan or quantity of subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paypal.subscriptions-revise\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscriptions-suspend\n      description: Paypal Suspend subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paypal.subscriptions-suspend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscriptions-cancel\n      description: Paypal Cancel subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paypal.subscriptions-cancel\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: subscriptions-activate\n      description: Paypal Activate subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paypal.subscriptions-activate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscriptions-capture\n      description: Paypal Capture authorized payment on subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paypal.subscriptions-capture\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscriptions-transactions\n      description: Paypal List transactions for subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: paypal.subscriptions-transactions\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PAYPAL_TOKEN: PAYPAL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/paypal/refs/heads/main/capabilities/paypal-capability.yaml
tags:
- Paypal
- API
tools:
- description: Paypal Create plan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: plans-create
- description: Paypal List plans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: plans-list
- description: Paypal Show plan details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: plans-get
- description: Paypal Update plan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: plans-patch
- description: Paypal Activate plan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: plans-activate
- description: Paypal Deactivate plan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: plans-deactivate
- description: Paypal Update pricing
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: plans-update-pricing-schemes
- description: Paypal Create subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: subscriptions-create
- description: Paypal Show subscription details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: subscriptions-get
- description: Paypal Update subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: subscriptions-patch
- description: Paypal Revise plan or quantity of subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: subscriptions-revise
- description: Paypal Suspend subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: subscriptions-suspend
- description: Paypal Cancel subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: subscriptions-cancel
- description: Paypal Activate subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: subscriptions-activate
- description: Paypal Capture authorized payment on subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: subscriptions-capture
- description: Paypal List transactions for subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: subscriptions-transactions
---

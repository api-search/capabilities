---
categories: []
consumed_apis:
- sap-brim-subscription-billing
description: Workflow capability for end-to-end subscription management within the SAP BRIM suite. Covers subscriber onboarding, plan management, lifecycle transitions (activate, suspend, renew, cancel), and billing cycle orchestration. Used by subscription management teams and customer service representatives.
layout: capability
name: SAP BRIM Subscription Lifecycle Management
operations:
- description: List all subscriptions with filtering.
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: Get subscription details.
  method: GET
  name: get-subscription
  path: /v1/subscriptions/{subscriptionId}
- description: List available subscription plans.
  method: GET
  name: list-plans
  path: /v1/plans
- description: List customers.
  method: GET
  name: list-customers
  path: /v1/customers
- description: Get customer account details.
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
personas: []
provider_name: SAP BRIM (Billing and Revenue Innovation Management)
provider_slug: sap-brim-billing-and-revenue-innovation-management
search_terms:
- list customer subscriptions with filtering by status, plan, or customer.
- list subscriptions
- list customers.
- customer accounts.
- list available subscription plans.
- get customer account details.
- cancel and terminate a customer subscription.
- subscription management
- order to cash
- subscription management.
- get full lifecycle details of a specific subscription.
- get subscription details.
- get subscription
- list all subscriptions with filtering.
- revenue management
- list plans
- get customer account details and subscription history.
- sap
- create subscription
- enterprise
- list customers
- suspend an active subscription (e.g., for non-payment).
- single customer account.
- get customer
- usage-based pricing
- suspend subscription
- list all available subscription plans in the brim catalog.
- billing
- single subscription.
- create a new subscription for a customer on a selected plan.
- subscription plan catalog.
- cancel subscription
slug: subscription-lifecycle-management
source_filename: subscription-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP BRIM Subscription Lifecycle Management\"\n  description: \"Workflow capability for end-to-end subscription management within the SAP BRIM suite. Covers subscriber onboarding, plan management, lifecycle transitions (activate, suspend, renew, cancel), and billing cycle orchestration. Used by subscription management teams and customer service representatives.\"\n  tags:\n    - Billing\n    - Revenue Management\n    - SAP\n    - Subscription Management\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_BRIM_OAUTH_TOKEN: SAP_BRIM_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: sap-brim-subscription-billing\n      location: ./shared/subscription-billing.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sap-brim-subscription-lifecycle-api\n      description: \"Unified REST API for SAP BRIM subscription lifecycle management.\"\n      resources:\n\
  \        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"Subscription management.\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List all subscriptions with filtering.\"\n              call: \"sap-brim-subscription-billing.list-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions/{subscriptionId}\n          name: subscription\n          description: \"Single subscription.\"\n          operations:\n            - method: GET\n              name: get-subscription\n              description: \"Get subscription details.\"\n              call: \"sap-brim-subscription-billing.get-subscription\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/plans\n\
  \          name: plans\n          description: \"Subscription plan catalog.\"\n          operations:\n            - method: GET\n              name: list-plans\n              description: \"List available subscription plans.\"\n              call: \"sap-brim-subscription-billing.list-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers\n          name: customers\n          description: \"Customer accounts.\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List customers.\"\n              call: \"sap-brim-subscription-billing.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{customerId}\n          name: customer\n          description: \"Single customer account.\"\n          operations:\n            - method: GET\n              name: get-customer\n\
  \              description: \"Get customer account details.\"\n              call: \"sap-brim-subscription-billing.get-customer\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: sap-brim-subscription-lifecycle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP BRIM subscription lifecycle management.\"\n      tools:\n        - name: list-subscriptions\n          description: \"List customer subscriptions with filtering by status, plan, or customer.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-brim-subscription-billing.list-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-subscription\n          description: \"Get full lifecycle details of a specific subscription.\"\
  \n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sap-brim-subscription-billing.get-subscription\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-subscription\n          description: \"Create a new subscription for a customer on a selected plan.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"sap-brim-subscription-billing.create-subscription\"\n          with:\n            customerId: \"tools.customerId\"\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: suspend-subscription\n          description: \"Suspend an active subscription (e.g., for non-payment).\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n\
  \          call: \"sap-brim-subscription-billing.suspend-subscription\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-subscription\n          description: \"Cancel and terminate a customer subscription.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"sap-brim-subscription-billing.cancel-subscription\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-plans\n          description: \"List all available subscription plans in the BRIM catalog.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-brim-subscription-billing.list-plans\"\n          outputParameters:\n            - type: object\n         \
  \     mapping: \"$.\"\n        - name: get-customer\n          description: \"Get customer account details and subscription history.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sap-brim-subscription-billing.get-customer\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-brim-billing-and-revenue-innovation-management/refs/heads/main/capabilities/subscription-lifecycle-management.yaml
tags:
- Billing
- Revenue Management
- SAP
- Subscription Management
tools:
- description: List customer subscriptions with filtering by status, plan, or customer.
  hints:
    openWorld: true
    readOnly: true
  name: list-subscriptions
- description: Get full lifecycle details of a specific subscription.
  hints:
    openWorld: false
    readOnly: true
  name: get-subscription
- description: Create a new subscription for a customer on a selected plan.
  hints:
    idempotent: false
    readOnly: false
  name: create-subscription
- description: Suspend an active subscription (e.g., for non-payment).
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: suspend-subscription
- description: Cancel and terminate a customer subscription.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-subscription
- description: List all available subscription plans in the BRIM catalog.
  hints:
    openWorld: true
    readOnly: true
  name: list-plans
- description: Get customer account details and subscription history.
  hints:
    openWorld: false
    readOnly: true
  name: get-customer
---

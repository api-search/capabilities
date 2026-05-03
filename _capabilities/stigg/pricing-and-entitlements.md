---
api_specs:
- filename: stigg-openapi.yml
  format: yaml
  label: stigg
  slug: stigg
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/stigg/refs/heads/main/openapi/stigg-openapi.yml
categories: []
consumed_apis:
- stigg
description: Unified pricing, subscription, and entitlement management workflow for SaaS products. Enables engineering teams to provision customers, manage subscription lifecycles, enforce feature access gates, and track usage for metered billing — all through a single integration that allows product managers to iterate on pricing without additional engineering effort.
layout: capability
name: Stigg Pricing and Entitlements
operations:
- description: Provision a new customer in Stigg.
  method: POST
  name: provision-customer
  path: /v1/customers
- description: Retrieve customer details and active subscriptions.
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
- description: Create a new subscription for a customer.
  method: POST
  name: create-subscription
  path: /v1/subscriptions
- description: Cancel an active subscription.
  method: POST
  name: cancel-subscription
  path: /v1/subscriptions/{subscriptionId}/cancel
- description: Check if a customer can access a specific feature.
  method: GET
  name: check-entitlement
  path: /v1/entitlements
- description: Get all feature entitlements for a customer.
  method: GET
  name: get-entitlements
  path: /v1/customers/{customerId}/entitlements
- description: Report feature usage for metered billing.
  method: POST
  name: report-usage
  path: /v1/usage
personas: []
provider_name: Stigg
provider_slug: stigg
search_terms:
- get all feature entitlements for a customer to understand their full access profile across all plan features.
- finops
- usage-based billing
- retrieve customer details and active subscriptions.
- get customer details including active subscriptions and plan information.
- provision a new customer in stigg. use when onboarding a new tenant or user to the saas product.
- report usage
- saas
- entitlements
- all entitlements for a customer.
- customer provisioning and retrieval.
- report feature usage for metered billing.
- report measured feature usage for a customer for metered billing calculations. use after each metered api call or event.
- subscription management
- pricing
- provision a new customer in stigg.
- get entitlements
- provision customer
- enroll a customer in a pricing plan by creating a subscription.
- check entitlement
- subscription lifecycle management.
- create subscription
- feature entitlement checks.
- feature usage reporting.
- check if a customer can access a specific feature.
- check whether a customer has access to a specific feature and what their usage limits are. use as a feature gate before executing protected functionality.
- cancel an active customer subscription. use for churn, downgrades, or account closures.
- individual customer operations.
- get customer
- cancel an active subscription.
- billing
- create a new subscription for a customer.
- get all feature entitlements for a customer.
- cancel subscription
slug: pricing-and-entitlements
source_filename: pricing-and-entitlements.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Stigg Pricing and Entitlements\n  description: >-\n    Unified pricing, subscription, and entitlement management workflow for SaaS\n    products. Enables engineering teams to provision customers, manage subscription\n    lifecycles, enforce feature access gates, and track usage for metered billing —\n    all through a single integration that allows product managers to iterate on\n    pricing without additional engineering effort.\n  tags:\n    - FinOps\n    - Pricing\n    - Billing\n    - Entitlements\n    - Usage-Based Billing\n    - SaaS\n    - Subscription Management\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STIGG_API_KEY: STIGG_API_KEY\n\ncapability:\n  consumes:\n    - import: stigg\n      location: ./shared/stigg.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: pricing-entitlements-api\n      description: >-\n        Unified REST API for customer\
  \ provisioning, subscription management,\n        and feature entitlement enforcement.\n      resources:\n        - path: /v1/customers\n          name: customers\n          description: Customer provisioning and retrieval.\n          operations:\n            - method: POST\n              name: provision-customer\n              description: Provision a new customer in Stigg.\n              call: \"stigg.provision-customer\"\n              with:\n                customerId: \"rest.customerId\"\n                name: \"rest.name\"\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customers/{customerId}\n          name: customer\n          description: Individual customer operations.\n          operations:\n            - method: GET\n              name: get-customer\n              description: Retrieve customer details and active subscriptions.\n              call: \"stigg.get-customer\"\
  \n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: Subscription lifecycle management.\n          operations:\n            - method: POST\n              name: create-subscription\n              description: Create a new subscription for a customer.\n              call: \"stigg.create-subscription\"\n              with:\n                customerId: \"rest.customerId\"\n                planId: \"rest.planId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/subscriptions/{subscriptionId}/cancel\n          name: cancel-subscription\n          description: Cancel an active subscription.\n          operations:\n            - method: POST\n              name: cancel-subscription\n              description: Cancel\
  \ an active subscription.\n              call: \"stigg.cancel-subscription\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/entitlements\n          name: entitlements\n          description: Feature entitlement checks.\n          operations:\n            - method: GET\n              name: check-entitlement\n              description: Check if a customer can access a specific feature.\n              call: \"stigg.check-entitlement\"\n              with:\n                customerId: \"rest.customerId\"\n                featureId: \"rest.featureId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customers/{customerId}/entitlements\n          name: customer-entitlements\n          description: All entitlements for a customer.\n          operations:\n            -\
  \ method: GET\n              name: get-entitlements\n              description: Get all feature entitlements for a customer.\n              call: \"stigg.get-entitlements\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/usage\n          name: usage\n          description: Feature usage reporting.\n          operations:\n            - method: POST\n              name: report-usage\n              description: Report feature usage for metered billing.\n              call: \"stigg.report-usage\"\n              with:\n                customerId: \"rest.customerId\"\n                featureId: \"rest.featureId\"\n                value: \"rest.value\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: pricing-entitlements-mcp\n      transport: http\n\
  \      description: >-\n        MCP server for AI-assisted pricing management, entitlement enforcement,\n        and subscription lifecycle operations.\n      tools:\n        - name: provision-customer\n          description: >-\n            Provision a new customer in Stigg. Use when onboarding a new tenant\n            or user to the SaaS product.\n          hints:\n            readOnly: false\n          call: \"stigg.provision-customer\"\n          with:\n            customerId: \"tools.customerId\"\n            name: \"tools.name\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-customer\n          description: >-\n            Get customer details including active subscriptions and plan information.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stigg.get-customer\"\n          with:\n            customerId: \"tools.customerId\"\n       \
  \   outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-subscription\n          description: >-\n            Enroll a customer in a pricing plan by creating a subscription.\n          hints:\n            readOnly: false\n          call: \"stigg.create-subscription\"\n          with:\n            customerId: \"tools.customerId\"\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-subscription\n          description: >-\n            Cancel an active customer subscription. Use for churn, downgrades,\n            or account closures.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"stigg.cancel-subscription\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n\n        - name: check-entitlement\n          description: >-\n            Check whether a customer has access to a specific feature and what\n            their usage limits are. Use as a feature gate before executing\n            protected functionality.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stigg.check-entitlement\"\n          with:\n            customerId: \"tools.customerId\"\n            featureId: \"tools.featureId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-entitlements\n          description: >-\n            Get all feature entitlements for a customer to understand their\n            full access profile across all plan features.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stigg.get-entitlements\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n\n        - name: report-usage\n          description: >-\n            Report measured feature usage for a customer for metered billing\n            calculations. Use after each metered API call or event.\n          hints:\n            readOnly: false\n          call: \"stigg.report-usage\"\n          with:\n            customerId: \"tools.customerId\"\n            featureId: \"tools.featureId\"\n            value: \"tools.value\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stigg/refs/heads/main/capabilities/pricing-and-entitlements.yaml
tags:
- FinOps
- Pricing
- Billing
- Entitlements
- Usage-Based Billing
- SaaS
- Subscription Management
tools:
- description: Provision a new customer in Stigg. Use when onboarding a new tenant or user to the SaaS product.
  hints:
    readOnly: false
  name: provision-customer
- description: Get customer details including active subscriptions and plan information.
  hints:
    idempotent: true
    readOnly: true
  name: get-customer
- description: Enroll a customer in a pricing plan by creating a subscription.
  hints:
    readOnly: false
  name: create-subscription
- description: Cancel an active customer subscription. Use for churn, downgrades, or account closures.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-subscription
- description: Check whether a customer has access to a specific feature and what their usage limits are. Use as a feature gate before executing protected functionality.
  hints:
    idempotent: true
    readOnly: true
  name: check-entitlement
- description: Get all feature entitlements for a customer to understand their full access profile across all plan features.
  hints:
    idempotent: true
    readOnly: true
  name: get-entitlements
- description: Report measured feature usage for a customer for metered billing calculations. Use after each metered API call or event.
  hints:
    readOnly: false
  name: report-usage
---

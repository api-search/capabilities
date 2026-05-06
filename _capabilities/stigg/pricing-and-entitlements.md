---
categories: []
consumed_apis: []
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
- provision a new customer in stigg. use when onboarding a new tenant or user to the saas product.
- customer provisioning and retrieval.
- subscription lifecycle management.
- provision a new customer in stigg.
- retrieve customer details and active subscriptions.
- usage-based billing
- get customer
- finops
- individual customer operations.
- get entitlements
- check whether a customer has access to a specific feature and what their usage limits are. use as a feature gate before executing protected functionality.
- check entitlement
- all entitlements for a customer.
- create subscription
- get all feature entitlements for a customer.
- billing
- get customer details including active subscriptions and plan information.
- cancel an active customer subscription. use for churn, downgrades, or account closures.
- get all feature entitlements for a customer to understand their full access profile across all plan features.
- report feature usage for metered billing.
- entitlements
- saas
- subscription management
- feature usage reporting.
- report measured feature usage for a customer for metered billing calculations. use after each metered api call or event.
- cancel subscription
- cancel an active subscription.
- create a new subscription for a customer.
- provision customer
- enroll a customer in a pricing plan by creating a subscription.
- feature entitlement checks.
- pricing
- report usage
- check if a customer can access a specific feature.
slug: pricing-and-entitlements
source_filename: pricing-and-entitlements.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stigg Pricing and Entitlements\n  description: Unified pricing, subscription, and entitlement management workflow for SaaS products. Enables engineering teams\n    to provision customers, manage subscription lifecycles, enforce feature access gates, and track usage for metered billing\n    — all through a single integration that allows product managers to iterate on pricing without additional engineering effort.\n  tags:\n  - FinOps\n  - Pricing\n  - Billing\n  - Entitlements\n  - Usage-Based Billing\n  - SaaS\n  - Subscription Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STIGG_API_KEY: STIGG_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stigg\n    baseUri: https://api.stigg.io\n    description: Stigg GraphQL API for entitlement and subscription management.\n    authentication:\n      type: apikey\n      key: X-API-KEY\n      value: '{{STIGG_API_KEY}}'\n     \
  \ placement: header\n    resources:\n    - name: graphql\n      path: /graphql\n      description: Stigg GraphQL endpoint for all operations.\n      operations:\n      - name: provision-customer\n        method: POST\n        description: Provision a new customer with optional billing info and initial subscription.\n        body:\n          type: json\n          data:\n            query: 'mutation ProvisionCustomer($input: ProvisionCustomerInput!) { provisionCustomer(input: $input) { customer\n              { id name email } } }'\n            variables:\n              input:\n                customerId: '{{tools.customerId}}'\n                name: '{{tools.name}}'\n                email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.provisionCustomer\n      - name: get-customer\n        method: POST\n        description: Retrieve customer details, active subscriptions, and entitlements.\n\
  \        body:\n          type: json\n          data:\n            query: 'query GetCustomer($customerId: String!) { customer(id: $customerId) { id name email subscriptions { id\n              status plan { id name } } } }'\n            variables:\n              customerId: '{{tools.customerId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.customer\n      - name: create-subscription\n        method: POST\n        description: Create a subscription linking a customer to a pricing plan.\n        body:\n          type: json\n          data:\n            query: 'mutation CreateSubscription($input: CreateSubscriptionInput!) { createSubscription(input: $input) { id\n              status plan { id name } } }'\n            variables:\n              input:\n                customerId: '{{tools.customerId}}'\n                planId: '{{tools.planId}}'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.data.createSubscription\n      - name: cancel-subscription\n        method: POST\n        description: Cancel an active subscription.\n        body:\n          type: json\n          data:\n            query: 'mutation CancelSubscription($input: CancelSubscriptionInput!) { cancelSubscription(input: $input) { id\n              status } }'\n            variables:\n              input:\n                subscriptionId: '{{tools.subscriptionId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.cancelSubscription\n      - name: check-entitlement\n        method: POST\n        description: Check if a customer has access to a specific feature.\n        body:\n          type: json\n          data:\n            query: 'query CheckEntitlement($customerId: String!, $featureId: String!) { customerEntitlement(customerId: $customerId,\n              featureId:\
  \ $featureId) { isGranted usageLimit currentUsage resetPeriod } }'\n            variables:\n              customerId: '{{tools.customerId}}'\n              featureId: '{{tools.featureId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.customerEntitlement\n      - name: get-entitlements\n        method: POST\n        description: Get all feature entitlements for a customer.\n        body:\n          type: json\n          data:\n            query: 'query GetEntitlements($customerId: String!) { customerEntitlements(customerId: $customerId) { featureId\n              isGranted usageLimit currentUsage } }'\n            variables:\n              customerId: '{{tools.customerId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.customerEntitlements\n      - name: report-usage\n        method: POST\n        description: Report calculated\
  \ usage measurements for metered features.\n        body:\n          type: json\n          data:\n            query: 'mutation ReportUsage($input: ReportUsageInput!) { reportUsage(input: $input) { id } }'\n            variables:\n              input:\n                customerId: '{{tools.customerId}}'\n                featureId: '{{tools.featureId}}'\n                value: '{{tools.value}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.reportUsage\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pricing-entitlements-api\n    description: Unified REST API for customer provisioning, subscription management, and feature entitlement enforcement.\n    resources:\n    - path: /v1/customers\n      name: customers\n      description: Customer provisioning and retrieval.\n      operations:\n      - method: POST\n        name: provision-customer\n        description: Provision a new customer in Stigg.\n\
  \        call: stigg.provision-customer\n        with:\n          customerId: rest.customerId\n          name: rest.name\n          email: rest.email\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{customerId}\n      name: customer\n      description: Individual customer operations.\n      operations:\n      - method: GET\n        name: get-customer\n        description: Retrieve customer details and active subscriptions.\n        call: stigg.get-customer\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions\n      name: subscriptions\n      description: Subscription lifecycle management.\n      operations:\n      - method: POST\n        name: create-subscription\n        description: Create a new subscription for a customer.\n        call: stigg.create-subscription\n        with:\n          customerId: rest.customerId\n        \
  \  planId: rest.planId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions/{subscriptionId}/cancel\n      name: cancel-subscription\n      description: Cancel an active subscription.\n      operations:\n      - method: POST\n        name: cancel-subscription\n        description: Cancel an active subscription.\n        call: stigg.cancel-subscription\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entitlements\n      name: entitlements\n      description: Feature entitlement checks.\n      operations:\n      - method: GET\n        name: check-entitlement\n        description: Check if a customer can access a specific feature.\n        call: stigg.check-entitlement\n        with:\n          customerId: rest.customerId\n          featureId: rest.featureId\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /v1/customers/{customerId}/entitlements\n      name: customer-entitlements\n      description: All entitlements for a customer.\n      operations:\n      - method: GET\n        name: get-entitlements\n        description: Get all feature entitlements for a customer.\n        call: stigg.get-entitlements\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/usage\n      name: usage\n      description: Feature usage reporting.\n      operations:\n      - method: POST\n        name: report-usage\n        description: Report feature usage for metered billing.\n        call: stigg.report-usage\n        with:\n          customerId: rest.customerId\n          featureId: rest.featureId\n          value: rest.value\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pricing-entitlements-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted pricing management, entitlement enforcement, and subscription lifecycle operations.\n    tools:\n    - name: provision-customer\n      description: Provision a new customer in Stigg. Use when onboarding a new tenant or user to the SaaS product.\n      hints:\n        readOnly: false\n      call: stigg.provision-customer\n      with:\n        customerId: tools.customerId\n        name: tools.name\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description: Get customer details including active subscriptions and plan information.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stigg.get-customer\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-subscription\n      description: Enroll a customer in a pricing plan by creating a subscription.\n      hints:\n        readOnly:\
  \ false\n      call: stigg.create-subscription\n      with:\n        customerId: tools.customerId\n        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-subscription\n      description: Cancel an active customer subscription. Use for churn, downgrades, or account closures.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: stigg.cancel-subscription\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-entitlement\n      description: Check whether a customer has access to a specific feature and what their usage limits are. Use as a feature\n        gate before executing protected functionality.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stigg.check-entitlement\n      with:\n        customerId: tools.customerId\n        featureId: tools.featureId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entitlements\n      description: Get all feature entitlements for a customer to understand their full access profile across all plan features.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stigg.get-entitlements\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: report-usage\n      description: Report measured feature usage for a customer for metered billing calculations. Use after each metered API\n        call or event.\n      hints:\n        readOnly: false\n      call: stigg.report-usage\n      with:\n        customerId: tools.customerId\n        featureId: tools.featureId\n        value: tools.value\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

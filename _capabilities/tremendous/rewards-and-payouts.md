---
categories: []
consumed_apis: []
description: Unified capability for sending and managing rewards, incentives, and payouts worldwide using the Tremendous platform. Enables businesses to send gift cards, prepaid cards, PayPal, bank transfers, and 2000+ other payout methods to employees, customers, survey participants, and research subjects with full delivery tracking and reporting.
layout: capability
name: Tremendous Rewards and Payouts
operations:
- description: List all reward orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a reward order
  method: POST
  name: create-order
  path: /v1/orders
- description: Get order status and rewards
  method: GET
  name: get-order
  path: /v1/orders/{id}
- description: Get reward delivery status
  method: GET
  name: get-reward
  path: /v1/rewards/{id}
- description: Resend reward delivery
  method: POST
  name: resend-reward
  path: /v1/rewards/{id}/resend
- description: Browse available products
  method: GET
  name: list-products
  path: /v1/products
- description: List funding sources
  method: GET
  name: list-funding-sources
  path: /v1/funding-sources
- description: List campaigns
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: List invoices
  method: GET
  name: list-invoices
  path: /v1/invoices
personas: []
provider_name: Tremendous
provider_slug: tremendous
search_terms:
- list funding sources
- list webhook configurations for monitoring reward delivery notifications.
- create order
- list reward orders to track incentive program activity and payout history.
- create a reward order
- list products
- configure a webhook endpoint to receive real-time notifications when orders complete or rewards are delivered.
- browse the catalog of available payout products (gift cards, prepaid cards, paypal, bank transfers, charity donations) filtered by country or currency.
- browse available products
- list reward campaigns to select branding and product catalogs for recipient-choice rewards.
- send a reward or payout to a recipient. specify recipient email, amount, currency, and delivery method (email, link, or phone).
- create webhook
- global payouts
- rewards
- reward orders for sending payouts
- list all reward orders
- order tracking and status
- get the status and details of a specific reward order including all rewards and delivery status.
- market research
- list available funding sources (balance, invoice, credit card) to use when creating orders.
- get campaign
- list campaigns
- list orders
- reward campaigns (branding and product selection)
- list invoices for tracking payout program costs and billing history.
- funding sources for paying orders
- get order status and rewards
- get the delivery status of an individual reward including whether it was delivered and redeemed.
- list webhooks
- individual reward status
- get reward
- available payout products catalog
- resend reward delivery
- payouts
- employee incentives
- get campaign details including available products, email branding, and messaging configuration.
- invoices and billing
- get reward delivery status
- incentives
- list invoices
- resend a reward delivery email to a recipient who did not receive it.
- get order
- resend reward
slug: rewards-and-payouts
source_filename: rewards-and-payouts.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tremendous Rewards and Payouts\n  description: Unified capability for sending and managing rewards, incentives, and payouts worldwide using the Tremendous\n    platform. Enables businesses to send gift cards, prepaid cards, PayPal, bank transfers, and 2000+ other payout methods\n    to employees, customers, survey participants, and research subjects with full delivery tracking and reporting.\n  tags:\n  - Employee Incentives\n  - Global Payouts\n  - Incentives\n  - Market Research\n  - Payouts\n  - Rewards\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TREMENDOUS_API_KEY: TREMENDOUS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: tremendous\n    baseUri: https://testflight.tremendous.com/api/v2\n    description: Tremendous rewards and payouts API\n    authentication:\n      type: bearer\n      token: '{{TREMENDOUS_API_KEY}}'\n    resources:\n    - name: orders\n      path: /orders\n\
  \      description: Reward orders\n      operations:\n      - name: list-orders\n        method: GET\n        description: List Orders\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results (max 100)\n        - name: created_at_gte\n          in: query\n          type: string\n          required: false\n          description: Filter by creation date (gte)\n        - name: created_at_lte\n          in: query\n          type: string\n          required: false\n          description: Filter by creation date (lte)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-order\n        method: POST\n        description: Create Order\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            external_id: '{{tools.external_id}}'\n            payment:\n              funding_source_id: '{{tools.funding_source_id}}'\n            reward:\n              value:\n                denomination: '{{tools.denomination}}'\n                currency_code: '{{tools.currency_code}}'\n              recipient:\n                name: '{{tools.recipient_name}}'\n                email: '{{tools.recipient_email}}'\n              delivery:\n                method: '{{tools.delivery_method}}'\n              campaign_id: '{{tools.campaign_id}}'\n    - name: order-detail\n      path: /orders/{id}\n      description: Single order\n      operations:\n      - name: get-order\n        method: GET\n        description: Get Order\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n\
  \          description: Order ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reward-detail\n      path: /rewards/{id}\n      description: Single reward\n      operations:\n      - name: get-reward\n        method: GET\n        description: Get Reward\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Reward ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reward-resend\n      path: /rewards/{id}/resend\n      description: Resend reward delivery\n      operations:\n      - name: resend-reward\n        method: POST\n        description: Resend Reward\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Reward ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      description: Available payout products\n      operations:\n      - name: list-products\n        method: GET\n        description: List Products\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: ISO 3166-1 alpha-2 country code\n        - name: currency_codes\n          in: query\n          type: string\n          required: false\n          description: Currency codes (comma-separated)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: funding-sources\n      path: /funding_sources\n      description: Funding sources\n      operations:\n      - name: list-funding-sources\n        method: GET\n        description: List Funding Sources\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigns\n      path: /campaigns\n      description: Reward campaigns\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List Campaigns\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign-detail\n      path: /campaigns/{id}\n      description: Single campaign\n      operations:\n      - name: get-campaign\n        method: GET\n        description: Get Campaign\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Campaign ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /organizations\n      description: Organizations\n      operations:\n\
  \      - name: list-organizations\n        method: GET\n        description: List Organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members\n      path: /members\n      description: Organization members\n      operations:\n      - name: list-members\n        method: GET\n        description: List Members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-member\n        method: POST\n        description: Create Member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            name: '{{tools.name}}'\n            role: '{{tools.role}}'\n    - name: invoices\n      path: /invoices\n      description: Invoices\n      operations:\n\
  \      - name: list-invoices\n        method: GET\n        description: List Invoices\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      description: Webhook configuration\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List Webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create Webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tremendous-rewards-api\n    description: Unified REST API for sending and managing rewards and payouts.\n    resources:\n    - path: /v1/orders\n      name: orders\n      description: Reward orders for sending payouts\n      operations:\n      - method: GET\n        name: list-orders\n        description: List all reward orders\n        call: tremendous.list-orders\n        with:\n          offset: rest.offset\n          limit: rest.limit\n          created_at_gte: rest.created_at_gte\n          created_at_lte: rest.created_at_lte\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Create a reward order\n        call: tremendous.create-order\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/orders/{id}\n      name: order-detail\n      description: Order tracking and status\n      operations:\n      - method: GET\n        name: get-order\n        description: Get order status and rewards\n        call: tremendous.get-order\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rewards/{id}\n      name: reward-detail\n      description: Individual reward status\n      operations:\n      - method: GET\n        name: get-reward\n        description: Get reward delivery status\n        call: tremendous.get-reward\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rewards/{id}/resend\n      name: reward-resend\n      description: Resend reward\n      operations:\n      - method: POST\n        name: resend-reward\n        description: Resend reward delivery\n        call: tremendous.resend-reward\n        with:\n\
  \          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: products\n      description: Available payout products catalog\n      operations:\n      - method: GET\n        name: list-products\n        description: Browse available products\n        call: tremendous.list-products\n        with:\n          country: rest.country\n          currency_codes: rest.currency_codes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/funding-sources\n      name: funding-sources\n      description: Funding sources for paying orders\n      operations:\n      - method: GET\n        name: list-funding-sources\n        description: List funding sources\n        call: tremendous.list-funding-sources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns\n      name: campaigns\n      description: Reward campaigns (branding and product selection)\n\
  \      operations:\n      - method: GET\n        name: list-campaigns\n        description: List campaigns\n        call: tremendous.list-campaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoices and billing\n      operations:\n      - method: GET\n        name: list-invoices\n        description: List invoices\n        call: tremendous.list-invoices\n        with:\n          offset: rest.offset\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tremendous-rewards-mcp\n    transport: http\n    description: MCP server for AI-assisted reward sending, payout management, and incentive program tracking.\n    tools:\n    - name: list-orders\n      description: List reward orders to track incentive program activity and payout history.\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: tremendous.list-orders\n      with:\n        offset: tools.offset\n        limit: tools.limit\n        created_at_gte: tools.created_at_gte\n        created_at_lte: tools.created_at_lte\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-order\n      description: Send a reward or payout to a recipient. Specify recipient email, amount, currency, and delivery method\n        (EMAIL, LINK, or PHONE).\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tremendous.create-order\n      with:\n        external_id: tools.external_id\n        funding_source_id: tools.funding_source_id\n        denomination: tools.denomination\n        currency_code: tools.currency_code\n        recipient_name: tools.recipient_name\n        recipient_email: tools.recipient_email\n        delivery_method: tools.delivery_method\n        campaign_id: tools.campaign_id\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-order\n      description: Get the status and details of a specific reward order including all rewards and delivery status.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tremendous.get-order\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-reward\n      description: Get the delivery status of an individual reward including whether it was delivered and redeemed.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tremendous.get-reward\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resend-reward\n      description: Resend a reward delivery email to a recipient who did not receive it.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tremendous.resend-reward\n      with:\n        id: tools.id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-products\n      description: Browse the catalog of available payout products (gift cards, prepaid cards, PayPal, bank transfers, charity\n        donations) filtered by country or currency.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tremendous.list-products\n      with:\n        country: tools.country\n        currency_codes: tools.currency_codes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-funding-sources\n      description: List available funding sources (balance, invoice, credit card) to use when creating orders.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tremendous.list-funding-sources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-campaigns\n      description: List reward campaigns to select branding and product catalogs for recipient-choice rewards.\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: tremendous.list-campaigns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-campaign\n      description: Get campaign details including available products, email branding, and messaging configuration.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tremendous.get-campaign\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: List invoices for tracking payout program costs and billing history.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tremendous.list-invoices\n      with:\n        offset: tools.offset\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhooks\n      description: List webhook configurations for monitoring reward delivery notifications.\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: tremendous.list-webhooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook\n      description: Configure a webhook endpoint to receive real-time notifications when orders complete or rewards are delivered.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tremendous.create-webhook\n      with:\n        url: tools.url\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tremendous/refs/heads/main/capabilities/rewards-and-payouts.yaml
tags:
- Employee Incentives
- Global Payouts
- Incentives
- Market Research
- Payouts
- Rewards
tools:
- description: List reward orders to track incentive program activity and payout history.
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Send a reward or payout to a recipient. Specify recipient email, amount, currency, and delivery method (EMAIL, LINK, or PHONE).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-order
- description: Get the status and details of a specific reward order including all rewards and delivery status.
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: Get the delivery status of an individual reward including whether it was delivered and redeemed.
  hints:
    openWorld: false
    readOnly: true
  name: get-reward
- description: Resend a reward delivery email to a recipient who did not receive it.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resend-reward
- description: Browse the catalog of available payout products (gift cards, prepaid cards, PayPal, bank transfers, charity donations) filtered by country or currency.
  hints:
    openWorld: true
    readOnly: true
  name: list-products
- description: List available funding sources (balance, invoice, credit card) to use when creating orders.
  hints:
    openWorld: true
    readOnly: true
  name: list-funding-sources
- description: List reward campaigns to select branding and product catalogs for recipient-choice rewards.
  hints:
    openWorld: true
    readOnly: true
  name: list-campaigns
- description: Get campaign details including available products, email branding, and messaging configuration.
  hints:
    openWorld: false
    readOnly: true
  name: get-campaign
- description: List invoices for tracking payout program costs and billing history.
  hints:
    openWorld: true
    readOnly: true
  name: list-invoices
- description: List webhook configurations for monitoring reward delivery notifications.
  hints:
    openWorld: true
    readOnly: true
  name: list-webhooks
- description: Configure a webhook endpoint to receive real-time notifications when orders complete or rewards are delivered.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-webhook
---

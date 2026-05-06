---
categories: []
consumed_apis: []
description: Workflow capability for digital reward and gift card distribution using the Runa platform. Combines product discovery, order management, balance monitoring, and cost estimation for B2C payment, employee incentive, customer loyalty, and marketing reward workflows. Serves reward program managers, growth engineers, and operations teams automating digital reward delivery at scale.
layout: capability
name: Runa Rewards Distribution
operations:
- description: Browse available gift cards and payout products
  method: GET
  name: browse-catalog
  path: /v1/catalog
- description: List product categories for catalog filtering
  method: GET
  name: list-categories
  path: /v1/catalog/categories
- description: List countries supported by Runa
  method: GET
  name: list-countries
  path: /v1/catalog/countries
- description: Get product denominations and redemption info
  method: GET
  name: get-product
  path: /v1/catalog/{productId}
- description: Create and send a digital reward to a recipient
  method: POST
  name: send-reward
  path: /v1/rewards
- description: List all reward orders
  method: GET
  name: list-rewards
  path: /v1/rewards
- description: Get reward order status and payout URL
  method: GET
  name: get-reward-status
  path: /v1/rewards/{orderId}
- description: Estimate cost before sending a reward
  method: POST
  name: estimate-reward
  path: /v1/rewards/estimate
- description: Get current account balance
  method: GET
  name: get-balance
  path: /v1/account/balance
personas: []
provider_name: Runa
provider_slug: runa
search_terms:
- get balance
- account balance
- browse catalog
- estimate cost before sending a reward
- get account balance
- get reward status
- get current account balance
- loyalty
- product categories
- create and send a digital reward or gift card to a recipient via runa
- list countries
- payouts
- get product
- send reward
- list product categories
- browse available gift cards and payout products
- create and send a digital reward to a recipient
- list all product categories available in the runa catalog (e.g., retail, dining, gaming)
- get product denominations and redemption info
- list countries supported by runa
- gift cards
- list supported countries
- list all reward orders
- incentives
- get the current runa account balance to check available funds before sending rewards
- supported countries
- estimate the cost of sending a digital reward before placing the order
- product details
- b2c
- get denomination options and redemption instructions for a specific runa product
- runa
- list categories
- digital reward orders
- browse available gift cards and payout products in the runa catalog
- payments
- list all countries where runa can deliver digital rewards
- get reward order status and payout url
- estimate reward
- estimate reward cost
- specific reward order
- rewards
- check the fulfillment status of a reward order and retrieve the payout url
- list product categories for catalog filtering
- list all digital reward orders placed with the runa account
- get product details
- list rewards
- browse available reward products
slug: rewards-distribution
source_filename: rewards-distribution.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Runa Rewards Distribution\n  description: Workflow capability for digital reward and gift card distribution using the Runa platform. Combines product\n    discovery, order management, balance monitoring, and cost estimation for B2C payment, employee incentive, customer loyalty,\n    and marketing reward workflows. Serves reward program managers, growth engineers, and operations teams automating digital\n    reward delivery at scale.\n  tags:\n  - Gift Cards\n  - Rewards\n  - Payments\n  - Incentives\n  - Payouts\n  - B2C\n  - Loyalty\n  - Runa\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RUNA_API_KEY: RUNA_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: payouts-api\n    baseUri: https://api.runa.io/v2\n    description: Runa Payouts API for digital reward and gift card distribution\n    authentication:\n      type: apikey\n      key: X-Api-Key\n      value: '{{RUNA_API_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: orders\n      path: /order\n      description: Digital reward order management\n      operations:\n      - name: create-order\n        method: POST\n        description: Create a new digital reward or gift card order\n        inputParameters:\n        - name: payment_method\n          in: body\n          type: object\n          required: true\n          description: Payment method (type, currency)\n        - name: items\n          in: body\n          type: array\n          required: true\n          description: Order items with face_value, distribution_method, and products\n        - name: X-Idempotency-Key\n          in: header\n          type: string\n          required: false\n          description: Idempotency key (UUID) to prevent duplicate orders\n        - name: X-Execution-Mode\n          in: header\n          type: string\n          required: false\n          description: sync or async execution mode\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-orders\n        method: GET\n        description: List orders for the authenticated account\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Get details for a specific order by ID\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n      - name: estimate-order\n        method: POST\n        description: Estimate the cost of an order before creating it\n        inputParameters:\n        - name: payment_method\n          in: body\n          type: object\n          required: true\n          description: Payment method for estimation\n        - name: items\n          in: body\n          type: array\n          required: true\n          description: Items to estimate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      description: Product catalog browsing\n      operations:\n      - name: list-products\n        method: GET\n        description: Browse available gift card and payout products\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: ISO country code filter\n\
  \        - name: category\n          in: query\n          type: string\n          required: false\n          description: Category name filter\n        - name: currency\n          in: query\n          type: string\n          required: false\n          description: Currency code filter\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search by product name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-product\n        method: GET\n        description: Get details for a specific product\n        inputParameters:\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: Product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-categories\n        method:\
  \ GET\n        description: List all product categories in the Runa catalog\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-countries\n        method: GET\n        description: List all supported countries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: balance\n      path: /balance\n      description: Account balance management\n      operations:\n      - name: get-balance\n        method: GET\n        description: Get account balance by currency\n        inputParameters:\n        - name: currency\n          in: query\n          type: string\n          required: false\n          description: ISO 4217 currency code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: utilities\n      path: /ping\n      description:\
  \ Connectivity and health check\n      operations:\n      - name: ping\n        method: GET\n        description: Verify API connectivity and authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: rewards-distribution-api\n    description: Unified REST API for Runa digital reward and gift card distribution workflows.\n    resources:\n    - path: /v1/catalog\n      name: catalog\n      description: Browse available reward products\n      operations:\n      - method: GET\n        name: browse-catalog\n        description: Browse available gift cards and payout products\n        call: payouts-api.list-products\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalog/categories\n      name: categories\n      description: Product categories\n      operations:\n      - method: GET\n        name: list-categories\n\
  \        description: List product categories for catalog filtering\n        call: payouts-api.list-categories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalog/countries\n      name: countries\n      description: Supported countries\n      operations:\n      - method: GET\n        name: list-countries\n        description: List countries supported by Runa\n        call: payouts-api.list-countries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalog/{productId}\n      name: product\n      description: Product details\n      operations:\n      - method: GET\n        name: get-product\n        description: Get product denominations and redemption info\n        call: payouts-api.get-product\n        with:\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rewards\n      name: rewards\n      description: Digital reward orders\n\
  \      operations:\n      - method: POST\n        name: send-reward\n        description: Create and send a digital reward to a recipient\n        call: payouts-api.create-order\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-rewards\n        description: List all reward orders\n        call: payouts-api.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rewards/{orderId}\n      name: reward\n      description: Specific reward order\n      operations:\n      - method: GET\n        name: get-reward-status\n        description: Get reward order status and payout URL\n        call: payouts-api.get-order\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rewards/estimate\n      name: reward-estimate\n      description: Estimate reward cost\n      operations:\n      - method: POST\n    \
  \    name: estimate-reward\n        description: Estimate cost before sending a reward\n        call: payouts-api.estimate-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/account/balance\n      name: balance\n      description: Account balance\n      operations:\n      - method: GET\n        name: get-balance\n        description: Get current account balance\n        call: payouts-api.get-balance\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: rewards-distribution-mcp\n    transport: http\n    description: MCP server for AI-assisted digital reward and gift card distribution using Runa.\n    tools:\n    - name: browse-catalog\n      description: Browse available gift cards and payout products in the Runa catalog\n      hints:\n        readOnly: true\n        openWorld: true\n      call: payouts-api.list-products\n      with:\n        country: tools.country\n        category:\
  \ tools.category\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product-details\n      description: Get denomination options and redemption instructions for a specific Runa product\n      hints:\n        readOnly: true\n        openWorld: false\n      call: payouts-api.get-product\n      with:\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-product-categories\n      description: List all product categories available in the Runa catalog (e.g., Retail, Dining, Gaming)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: payouts-api.list-categories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-supported-countries\n      description: List all countries where Runa can deliver digital rewards\n      hints:\n        readOnly: true\n        openWorld: false\n      call: payouts-api.list-countries\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: estimate-reward-cost\n      description: Estimate the cost of sending a digital reward before placing the order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: payouts-api.estimate-order\n      with:\n        payment_method: tools.paymentMethod\n        items: tools.items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-reward\n      description: Create and send a digital reward or gift card to a recipient via Runa\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: payouts-api.create-order\n      with:\n        payment_method: tools.paymentMethod\n        items: tools.items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-reward-status\n      description: Check the fulfillment status of a reward order and retrieve the payout URL\n      hints:\n      \
  \  readOnly: true\n        openWorld: false\n      call: payouts-api.get-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-rewards\n      description: List all digital reward orders placed with the Runa account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: payouts-api.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-balance\n      description: Get the current Runa account balance to check available funds before sending rewards\n      hints:\n        readOnly: true\n        openWorld: false\n      call: payouts-api.get-balance\n      with:\n        currency: tools.currency\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/runa/refs/heads/main/capabilities/rewards-distribution.yaml
tags:
- Gift Cards
- Rewards
- Payments
- Incentives
- Payouts
- B2C
- Loyalty
- Runa
tools:
- description: Browse available gift cards and payout products in the Runa catalog
  hints:
    openWorld: true
    readOnly: true
  name: browse-catalog
- description: Get denomination options and redemption instructions for a specific Runa product
  hints:
    openWorld: false
    readOnly: true
  name: get-product-details
- description: List all product categories available in the Runa catalog (e.g., Retail, Dining, Gaming)
  hints:
    openWorld: false
    readOnly: true
  name: list-product-categories
- description: List all countries where Runa can deliver digital rewards
  hints:
    openWorld: false
    readOnly: true
  name: list-supported-countries
- description: Estimate the cost of sending a digital reward before placing the order
  hints:
    openWorld: false
    readOnly: true
  name: estimate-reward-cost
- description: Create and send a digital reward or gift card to a recipient via Runa
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-reward
- description: Check the fulfillment status of a reward order and retrieve the payout URL
  hints:
    openWorld: false
    readOnly: true
  name: get-reward-status
- description: List all digital reward orders placed with the Runa account
  hints:
    openWorld: false
    readOnly: true
  name: list-rewards
- description: Get the current Runa account balance to check available funds before sending rewards
  hints:
    openWorld: false
    readOnly: true
  name: get-account-balance
---

---
categories: []
consumed_apis: []
description: Unified capability for Starbucks food service workflows including menu discovery, store location, loyalty management, and mobile ordering. Enables partner applications to provide full Starbucks experiences covering menu browsing, store finder, rewards tracking, and order placement.
layout: capability
name: Starbucks Food Service
operations:
- description: List all available Starbucks menu categories
  method: GET
  name: list-menu-categories
  path: /v1/menu/categories
- description: List menu items in a category with pricing and options
  method: GET
  name: list-menu-items
  path: /v1/menu/categories/{categoryId}/items
- description: Get full menu item details including nutrition and customization
  method: GET
  name: get-menu-item
  path: /v1/menu/items/{itemId}
- description: Search for Starbucks stores near a location
  method: GET
  name: list-stores
  path: /v1/stores
- description: Get Starbucks store details including hours and amenities
  method: GET
  name: get-store
  path: /v1/stores/{storeId}
- description: Get loyalty account star balance and tier
  method: GET
  name: get-loyalty-account
  path: /v1/loyalty/accounts/{accountId}
- description: List star earning and redemption transactions
  method: GET
  name: list-loyalty-transactions
  path: /v1/loyalty/accounts/{accountId}/transactions
- description: Place a new Starbucks mobile order
  method: POST
  name: create-order
  path: /v1/orders
- description: Get order status and estimated ready time
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
personas: []
provider_name: Starbucks
provider_slug: starbucks
search_terms:
- search for starbucks stores near a location
- view loyalty transaction history
- create order
- list loyalty transactions
- get detailed menu item information
- get store details
- loyalty
- get starbucks store details including hours and amenities
- submit a starbucks mobile order with customized items at a specified store, optionally applying loyalty rewards
- retail
- manage starbucks rewards account
- ordering
- get store
- view history of starbucks star earnings and redemptions for a rewards account
- get loyalty account star balance and tier
- mobile order management
- store locator
- place a new starbucks mobile order
- food service
- list star earning and redemption transactions
- get order status and estimated ready time
- find starbucks locations near specified coordinates or address, with filtering by radius
- list menu items in a category with pricing and options
- find starbucks store locations
- check the current status and estimated pickup time for a starbucks mobile order
- get full menu item details including nutrition and customization
- starbucks
- list stores
- list menu items
- browse all starbucks menu categories including hot coffees, cold coffees, teas, refreshers, food, and merchandise
- get all items in a starbucks menu category with descriptions, pricing, and sizes
- get complete details for a starbucks menu item including nutrition facts, allergens, and customization options
- track order
- list reward transactions
- mobile ordering
- get menu item
- check starbucks rewards star balance, membership tier (welcome/green/gold), and account status
- place order
- browse starbucks menu categories
- list menu categories
- browse items within a menu category
- get loyalty account
- track an order
- list all available starbucks menu categories
- search stores
- coffee
- get starbucks store hours, amenities, drive-thru availability, and mobile ordering status
- get loyalty balance
- get order
slug: food-service
source_filename: food-service.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Starbucks Food Service\n  description: Unified capability for Starbucks food service workflows including menu discovery, store location, loyalty management,\n    and mobile ordering. Enables partner applications to provide full Starbucks experiences covering menu browsing, store\n    finder, rewards tracking, and order placement.\n  tags:\n  - Starbucks\n  - Food Service\n  - Coffee\n  - Mobile Ordering\n  - Loyalty\n  - Store Locator\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STARBUCKS_API_TOKEN: STARBUCKS_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: starbucks\n    baseUri: https://api.starbucks.com\n    description: Starbucks API for menu, stores, loyalty, and ordering\n    authentication:\n      type: bearer\n      token: '{{STARBUCKS_API_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      description: API health and status\n      operations:\n\
  \      - name: get-status\n        method: GET\n        description: Get API status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: menu-categories\n      path: /v1/menu/categories\n      description: Menu category listing\n      operations:\n      - name: list-menu-categories\n        method: GET\n        description: List all menu categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: menu-items\n      path: /v1/menu/categories/{categoryId}/items\n      description: Menu items within a category\n      operations:\n      - name: list-menu-items\n        method: GET\n        description: List menu items for a category\n        inputParameters:\n        - name: categoryId\n          in: path\n          type: string\n          required: true\n          description: Menu category identifier\n        - name:\
  \ limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: menu-item\n      path: /v1/menu/items/{itemId}\n      description: Individual menu item details\n      operations:\n      - name: get-menu-item\n        method: GET\n        description: Get detailed menu item information\n        inputParameters:\n        - name: itemId\n          in: path\n          type: string\n          required: true\n          description: Menu item identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stores\n      path: /v1/stores\n      description: Store location\
  \ search\n      operations:\n      - name: list-stores\n        method: GET\n        description: Search and list Starbucks store locations\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: false\n          description: Latitude for location search\n        - name: longitude\n          in: query\n          type: number\n          required: false\n          description: Longitude for location search\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Text search query for location\n        - name: radius\n          in: query\n          type: integer\n          required: false\n          description: Search radius in miles\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: store\n      path: /v1/stores/{storeId}\n      description: Individual store details\n      operations:\n      - name: get-store\n        method: GET\n        description: Get store details and hours\n        inputParameters:\n        - name: storeId\n          in: path\n          type: string\n          required: true\n          description: Store identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loyalty-account\n      path: /v1/loyalty/accounts/{accountId}\n      description: Loyalty account management\n      operations:\n      - name: get-loyalty-account\n        method: GET\n        description: Get loyalty account star balance and tier\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Loyalty account identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loyalty-transactions\n      path: /v1/loyalty/accounts/{accountId}/transactions\n      description: Loyalty transaction history\n      operations:\n      - name: list-loyalty-transactions\n        method: GET\n        description: List star earning and redemption transactions\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Loyalty account identifier\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n\
  \      path: /v1/orders\n      description: Order management\n      operations:\n      - name: create-order\n        method: POST\n        description: Create a new Starbucks order\n        body:\n          type: json\n          data:\n            storeId: '{{tools.storeId}}'\n            items: '{{tools.items}}'\n            loyaltyAccountId: '{{tools.loyaltyAccountId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: order\n      path: /v1/orders/{orderId}\n      description: Individual order status\n      operations:\n      - name: get-order\n        method: GET\n        description: Get order status and details\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: starbucks-food-service-api\n    description: Unified REST API for Starbucks food service workflows.\n    resources:\n    - path: /v1/menu/categories\n      name: menu-categories\n      description: Browse Starbucks menu categories\n      operations:\n      - method: GET\n        name: list-menu-categories\n        description: List all available Starbucks menu categories\n        call: starbucks.list-menu-categories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/menu/categories/{categoryId}/items\n      name: menu-items\n      description: Browse items within a menu category\n      operations:\n      - method: GET\n        name: list-menu-items\n        description: List menu items in a category with pricing and options\n        call: starbucks.list-menu-items\n        with:\n          categoryId: rest.categoryId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/menu/items/{itemId}\n      name: menu-item\n      description: Get detailed menu item information\n      operations:\n      - method: GET\n        name: get-menu-item\n        description: Get full menu item details including nutrition and customization\n        call: starbucks.get-menu-item\n        with:\n          itemId: rest.itemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stores\n      name: stores\n      description: Find Starbucks store locations\n      operations:\n      - method: GET\n        name: list-stores\n        description: Search for Starbucks stores near a location\n        call: starbucks.list-stores\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n          query: rest.query\n          radius: rest.radius\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stores/{storeId}\n      name: store\n      description: Get store\
  \ details\n      operations:\n      - method: GET\n        name: get-store\n        description: Get Starbucks store details including hours and amenities\n        call: starbucks.get-store\n        with:\n          storeId: rest.storeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loyalty/accounts/{accountId}\n      name: loyalty-account\n      description: Manage Starbucks Rewards account\n      operations:\n      - method: GET\n        name: get-loyalty-account\n        description: Get loyalty account star balance and tier\n        call: starbucks.get-loyalty-account\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loyalty/accounts/{accountId}/transactions\n      name: loyalty-transactions\n      description: View loyalty transaction history\n      operations:\n      - method: GET\n        name: list-loyalty-transactions\n        description: List\
  \ star earning and redemption transactions\n        call: starbucks.list-loyalty-transactions\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Mobile order management\n      operations:\n      - method: POST\n        name: create-order\n        description: Place a new Starbucks mobile order\n        call: starbucks.create-order\n        with:\n          storeId: rest.storeId\n          items: rest.items\n          loyaltyAccountId: rest.loyaltyAccountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}\n      name: order\n      description: Track an order\n      operations:\n      - method: GET\n        name: get-order\n        description: Get order status and estimated ready time\n        call: starbucks.get-order\n        with:\n          orderId: rest.orderId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: starbucks-food-service-mcp\n    transport: http\n    description: MCP server for AI-assisted Starbucks food service workflows.\n    tools:\n    - name: list-menu-categories\n      description: Browse all Starbucks menu categories including Hot Coffees, Cold Coffees, Teas, Refreshers, Food, and Merchandise\n      hints:\n        readOnly: true\n        openWorld: true\n      call: starbucks.list-menu-categories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-menu-items\n      description: Get all items in a Starbucks menu category with descriptions, pricing, and sizes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: starbucks.list-menu-items\n      with:\n        categoryId: tools.categoryId\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-menu-item\n      description:\
  \ Get complete details for a Starbucks menu item including nutrition facts, allergens, and customization\n        options\n      hints:\n        readOnly: true\n        openWorld: true\n      call: starbucks.get-menu-item\n      with:\n        itemId: tools.itemId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-stores\n      description: Find Starbucks locations near specified coordinates or address, with filtering by radius\n      hints:\n        readOnly: true\n        openWorld: true\n      call: starbucks.list-stores\n      with:\n        latitude: tools.latitude\n        longitude: tools.longitude\n        query: tools.query\n        radius: tools.radius\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-store-details\n      description: Get Starbucks store hours, amenities, drive-thru availability, and mobile ordering status\n      hints:\n        readOnly: true\n        idempotent:\
  \ true\n      call: starbucks.get-store\n      with:\n        storeId: tools.storeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-loyalty-balance\n      description: Check Starbucks Rewards star balance, membership tier (Welcome/Green/Gold), and account status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: starbucks.get-loyalty-account\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reward-transactions\n      description: View history of Starbucks star earnings and redemptions for a Rewards account\n      hints:\n        readOnly: true\n        idempotent: true\n      call: starbucks.list-loyalty-transactions\n      with:\n        accountId: tools.accountId\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: place-order\n      description: Submit a Starbucks mobile order with\
  \ customized items at a specified store, optionally applying loyalty\n        rewards\n      hints:\n        readOnly: false\n        destructive: false\n      call: starbucks.create-order\n      with:\n        storeId: tools.storeId\n        items: tools.items\n        loyaltyAccountId: tools.loyaltyAccountId\n        redemptionStars: tools.redemptionStars\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-order\n      description: Check the current status and estimated pickup time for a Starbucks mobile order\n      hints:\n        readOnly: true\n        idempotent: true\n      call: starbucks.get-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/starbucks/refs/heads/main/capabilities/food-service.yaml
tags:
- Starbucks
- Food Service
- Coffee
- Mobile Ordering
- Loyalty
- Store Locator
tools:
- description: Browse all Starbucks menu categories including Hot Coffees, Cold Coffees, Teas, Refreshers, Food, and Merchandise
  hints:
    openWorld: true
    readOnly: true
  name: list-menu-categories
- description: Get all items in a Starbucks menu category with descriptions, pricing, and sizes
  hints:
    openWorld: true
    readOnly: true
  name: list-menu-items
- description: Get complete details for a Starbucks menu item including nutrition facts, allergens, and customization options
  hints:
    openWorld: true
    readOnly: true
  name: get-menu-item
- description: Find Starbucks locations near specified coordinates or address, with filtering by radius
  hints:
    openWorld: true
    readOnly: true
  name: search-stores
- description: Get Starbucks store hours, amenities, drive-thru availability, and mobile ordering status
  hints:
    idempotent: true
    readOnly: true
  name: get-store-details
- description: Check Starbucks Rewards star balance, membership tier (Welcome/Green/Gold), and account status
  hints:
    idempotent: true
    readOnly: true
  name: get-loyalty-balance
- description: View history of Starbucks star earnings and redemptions for a Rewards account
  hints:
    idempotent: true
    readOnly: true
  name: list-reward-transactions
- description: Submit a Starbucks mobile order with customized items at a specified store, optionally applying loyalty rewards
  hints:
    destructive: false
    readOnly: false
  name: place-order
- description: Check the current status and estimated pickup time for a Starbucks mobile order
  hints:
    idempotent: true
    readOnly: true
  name: track-order
---

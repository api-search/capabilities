---
categories: []
consumed_apis: []
description: Unified workflow capability for SaaS procurement intelligence, enabling procurement teams, finance analysts, and software buyers to research products, benchmark fair pricing from 200,000+ real contracts, structure purchase scopes, and automate procurement event notifications. Combines catalog, pricing, scope, and webhook APIs into a single AI-ready interface.
layout: capability
name: Vendr SaaS Procurement Intelligence
operations:
- description: Search for software products and vendors
  method: GET
  name: search-products
  path: /v1/products
- description: Parse natural language purchase requirements into structured scope
  method: POST
  name: create-purchase-scope
  path: /v1/purchase-scopes
- description: Get fair price estimate and negotiation insights
  method: POST
  name: get-price-estimate
  path: /v1/price-estimates
- description: List all active event subscriptions
  method: GET
  name: list-event-subscriptions
  path: /v1/event-subscriptions
- description: Subscribe to procurement workflow events
  method: POST
  name: create-event-subscription
  path: /v1/event-subscriptions
- description: Remove an event subscription
  method: DELETE
  name: delete-event-subscription
  path: /v1/event-subscriptions/{webhookId}
personas: []
provider_name: Vendr
provider_slug: vendr
search_terms:
- get a fair price estimate and negotiation insights for a software purchase based on 200,000+ real contracts
- negotiation
- delete event subscription
- get price estimate
- list event subscriptions
- subscribe to procurement workflow events (deal closed, workflow updated, pricing changed)
- get fair price estimate and negotiation insights
- create purchase scope
- get price benchmark
- unsubscribe from events
- remove an event subscription
- remove a procurement event subscription
- search for software products and vendors
- subscribe to procurement workflow events
- parse natural language purchase requirements (e.g. '10 seats of slack pro annual') into structured scope
- saas
- parse purchase scope
- list all active procurement workflow event subscriptions
- software spend management
- procurement workflow event subscriptions
- define and structure purchase requirements
- search for software products and vendors in the vendr catalog
- list all active event subscriptions
- manage individual event subscriptions
- subscribe to events
- create event subscription
- pricing
- fair price estimates based on real contract data
- vendr
- parse natural language purchase requirements into structured scope
- search products
- browse and search software products in the vendr catalog
- procurement
slug: saas-procurement-intelligence
source_filename: saas-procurement-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vendr SaaS Procurement Intelligence\n  description: Unified workflow capability for SaaS procurement intelligence, enabling procurement teams, finance analysts,\n    and software buyers to research products, benchmark fair pricing from 200,000+ real contracts, structure purchase scopes,\n    and automate procurement event notifications. Combines catalog, pricing, scope, and webhook APIs into a single AI-ready\n    interface.\n  tags:\n  - Vendr\n  - Pricing\n  - Procurement\n  - SaaS\n  - Software Spend Management\n  - Negotiation\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VENDR_API_KEY: VENDR_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: vendr\n    baseUri: https://api.vendr.com\n    description: Vendr SaaS pricing intelligence and procurement API\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{VENDR_API_KEY}}'\n      placement: header\n\
  \    resources:\n    - name: catalog\n      path: /v1/catalog\n      description: Software product catalog with pricing profiles and add-ons\n      operations:\n      - name: search-catalog\n        method: GET\n        description: Search for companies and products in the Vendr catalog\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query for company or product name\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scope\n      path: /v1/scope\n      description: Define and parse purchase scope requirements\n      operations:\n\
  \      - name: submit-scope\n        method: POST\n        description: Submit purchase requirements as text and receive structured scope data\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            text: '{{tools.text}}'\n            productId: '{{tools.productId}}'\n    - name: pricing\n      path: /v1/pricing\n      description: Fair price estimates and negotiation insights\n      operations:\n      - name: get-pricing-estimate\n        method: POST\n        description: Get fair price estimate and negotiation insights for a software purchase\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            text: '{{tools.text}}'\n            productId: '{{tools.productId}}'\n\
  \    - name: webhooks\n      path: /v1/webhooks\n      description: Webhook event subscriptions\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all registered webhook subscriptions\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a new webhook subscription for event notifications\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            events: '{{tools.events}}'\n            secret: '{{tools.secret}}'\n    - name: webhook-by-id\n      path: /v1/webhooks/{webhookId}\n      description: Manage individual webhook subscriptions\n      operations:\n      - name:\
  \ delete-webhook\n        method: DELETE\n        description: Remove a webhook subscription by ID\n        inputParameters:\n        - name: webhookId\n          in: path\n          type: string\n          required: true\n          description: Unique webhook subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vendr-procurement-api\n    description: Unified REST API for SaaS procurement intelligence and spend management.\n    resources:\n    - path: /v1/products\n      name: products\n      description: Browse and search software products in the Vendr catalog\n      operations:\n      - method: GET\n        name: search-products\n        description: Search for software products and vendors\n        call: vendr.search-catalog\n        with:\n          q: rest.q\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/purchase-scopes\n      name: purchase-scopes\n      description: Define and structure purchase requirements\n      operations:\n      - method: POST\n        name: create-purchase-scope\n        description: Parse natural language purchase requirements into structured scope\n        call: vendr.submit-scope\n        with:\n          text: rest.text\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/price-estimates\n      name: price-estimates\n      description: Fair price estimates based on real contract data\n      operations:\n      - method: POST\n        name: get-price-estimate\n        description: Get fair price estimate and negotiation insights\n        call: vendr.get-pricing-estimate\n        with:\n          text: rest.text\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/event-subscriptions\n      name: event-subscriptions\n      description: Procurement workflow event subscriptions\n      operations:\n      - method: GET\n        name: list-event-subscriptions\n        description: List all active event subscriptions\n        call: vendr.list-webhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-event-subscription\n        description: Subscribe to procurement workflow events\n        call: vendr.create-webhook\n        with:\n          url: rest.url\n          events: rest.events\n          secret: rest.secret\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-subscriptions/{webhookId}\n      name: event-subscription-by-id\n      description: Manage individual event subscriptions\n      operations:\n      - method: DELETE\n        name: delete-event-subscription\n        description: Remove an event subscription\n  \
  \      call: vendr.delete-webhook\n        with:\n          webhookId: rest.webhookId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vendr-procurement-mcp\n    transport: http\n    description: MCP server for AI-assisted SaaS procurement intelligence and negotiation.\n    tools:\n    - name: search-products\n      description: Search for software products and vendors in the Vendr catalog\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vendr.search-catalog\n      with:\n        q: tools.q\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: parse-purchase-scope\n      description: Parse natural language purchase requirements (e.g. '10 seats of Slack Pro annual') into structured scope\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vendr.submit-scope\n      with:\n        text: tools.text\n        productId:\
  \ tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-price-benchmark\n      description: Get a fair price estimate and negotiation insights for a software purchase based on 200,000+ real contracts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vendr.get-pricing-estimate\n      with:\n        text: tools.text\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-event-subscriptions\n      description: List all active procurement workflow event subscriptions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vendr.list-webhooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscribe-to-events\n      description: Subscribe to procurement workflow events (deal closed, workflow updated, pricing changed)\n      hints:\n        readOnly: false\n        idempotent: false\n      call: vendr.create-webhook\n\
  \      with:\n        url: tools.url\n        events: tools.events\n        secret: tools.secret\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unsubscribe-from-events\n      description: Remove a procurement event subscription\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: vendr.delete-webhook\n      with:\n        webhookId: tools.webhookId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vendr/refs/heads/main/capabilities/saas-procurement-intelligence.yaml
tags:
- Vendr
- Pricing
- Procurement
- SaaS
- Software Spend Management
- Negotiation
tools:
- description: Search for software products and vendors in the Vendr catalog
  hints:
    openWorld: true
    readOnly: true
  name: search-products
- description: Parse natural language purchase requirements (e.g. '10 seats of Slack Pro annual') into structured scope
  hints:
    openWorld: true
    readOnly: true
  name: parse-purchase-scope
- description: Get a fair price estimate and negotiation insights for a software purchase based on 200,000+ real contracts
  hints:
    openWorld: true
    readOnly: true
  name: get-price-benchmark
- description: List all active procurement workflow event subscriptions
  hints:
    idempotent: true
    readOnly: true
  name: list-event-subscriptions
- description: Subscribe to procurement workflow events (deal closed, workflow updated, pricing changed)
  hints:
    idempotent: false
    readOnly: false
  name: subscribe-to-events
- description: Remove a procurement event subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unsubscribe-from-events
---

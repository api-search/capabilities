---
categories:
- procurement-supply-chain
consumed_apis:
- vendr
description: Workflow capability for SaaS procurement intelligence using Vendr's Catalog and Pricing APIs. Enables procurement teams, finance, and IT to search software catalogs, benchmark pricing, get negotiation guidance, and automate renewal monitoring. Formerly Blissfully, now Vendr.
layout: capability
name: Blissfully SaaS Procurement
operations:
- description: Search and browse software products in the Vendr catalog
  method: GET
  name: list-products
  path: /v1/products
- description: List software vendors
  method: GET
  name: list-vendors
  path: /v1/vendors
- description: Get fair price benchmarks and negotiation guidance
  method: POST
  name: get-pricing-insights
  path: /v1/pricing
personas: []
provider_name: Blissfully
provider_slug: blissfully
search_terms:
- pricing intelligence
- get fair price benchmarks and negotiation guidance
- saas catalog browsing, pricing benchmarks, and negotiation guidance
- list software vendors in the vendr catalog with their product portfolios and category information.
- Finance Analyst
- ai procurement
- analyzes saas spend, benchmarks costs, and identifies savings opportunities
- spend optimization
- portfolio visibility, spend optimization, and renewal management
- researches software options, benchmarks pricing, and negotiates with vendors
- saas management
- software purchasing, negotiation, and vendor management
- create webhook
- AI Assistant
- list software vendors
- get pricing insights
- software vendor catalog
- search and browse software products in the vendr catalog
- list vendors
- software catalog
- software product catalog search and browsing
- IT Manager
- software procurement
- vendor management
- get fair price predictions and negotiation guidance for a software product. powered by vendr's database of real software purchases.
- procurement
- provides ai-assisted procurement recommendations via mcp integration
- pricing intelligence and negotiation guidance
- list products
- evaluates software capabilities and manages the saas portfolio
- saas discovery
- Procurement Manager
- get product
- create a webhook to receive notifications when vendr pricing or catalog data is updated.
- get detailed catalog attributes, features, and add-ons for a specific software product.
- search and browse software products in the vendr catalog. returns structured attributes, features, and available add-ons.
slug: blissfully-saas-procurement
source_filename: blissfully-saas-procurement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Blissfully SaaS Procurement\n  description: >-\n    Workflow capability for SaaS procurement intelligence using Vendr's Catalog and Pricing APIs.\n    Enables procurement teams, finance, and IT to search software catalogs, benchmark pricing,\n    get negotiation guidance, and automate renewal monitoring. Formerly Blissfully, now Vendr.\n  tags:\n    - AI Procurement\n    - Pricing Intelligence\n    - Procurement\n    - SaaS Management\n    - Software Catalog\n    - Vendor Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      VENDR_API_KEY: VENDR_API_KEY\n\ncapability:\n  consumes:\n    - import: vendr\n      location: ./shared/vendr-catalog-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: blissfully-saas-procurement-api\n      description: Unified REST API for SaaS procurement intelligence powered by Vendr data.\n      resources:\n        - path:\
  \ /v1/products\n          name: products\n          description: Software product catalog search and browsing\n          operations:\n            - method: GET\n              name: list-products\n              description: Search and browse software products in the Vendr catalog\n              call: \"vendr.list-products\"\n              with:\n                category: \"rest.category\"\n                vendor_id: \"rest.vendor_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vendors\n          name: vendors\n          description: Software vendor catalog\n          operations:\n            - method: GET\n              name: list-vendors\n              description: List software vendors\n              call: \"vendr.list-vendors\"\n              with:\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/pricing\n          name: pricing\n          description: Pricing intelligence and negotiation guidance\n          operations:\n            - method: POST\n              name: get-pricing-insights\n              description: Get fair price benchmarks and negotiation guidance\n              call: \"vendr.get-pricing-insights\"\n              with:\n                product_id: \"rest.product_id\"\n                seats: \"rest.seats\"\n                contract_length_months: \"rest.contract_length_months\"\n                company_size: \"rest.company_size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: blissfully-saas-procurement-mcp\n      transport: http\n      description: MCP server for AI-assisted SaaS procurement powered by Vendr catalog and pricing data.\n      tools:\n        - name: list-products\n          description: Search and browse software products in the Vendr\
  \ catalog. Returns structured attributes, features, and available add-ons.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vendr.list-products\"\n          with:\n            category: \"tools.category\"\n            vendor_id: \"tools.vendor_id\"\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product\n          description: Get detailed catalog attributes, features, and add-ons for a specific software product.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vendr.get-product\"\n          with:\n            product_id: \"tools.product_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-vendors\n          description: List software vendors in the Vendr catalog with their product portfolios and category\
  \ information.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vendr.list-vendors\"\n          with:\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pricing-insights\n          description: Get fair price predictions and negotiation guidance for a software product. Powered by Vendr's database of real software purchases.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vendr.get-pricing-insights\"\n          with:\n            product_id: \"tools.product_id\"\n            seats: \"tools.seats\"\n            contract_length_months: \"tools.contract_length_months\"\n            company_size: \"tools.company_size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-webhook\n          description: Create a webhook to receive notifications when\
  \ Vendr pricing or catalog data is updated.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"vendr.create-webhook\"\n          with:\n            url: \"tools.url\"\n            events: \"tools.events\"\n            secret: \"tools.secret\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/blissfully/refs/heads/main/capabilities/blissfully-saas-procurement.yaml
tags:
- AI Procurement
- Pricing Intelligence
- Procurement
- SaaS Management
- Software Catalog
- Vendor Management
tools:
- description: Search and browse software products in the Vendr catalog. Returns structured attributes, features, and available add-ons.
  hints:
    openWorld: true
    readOnly: true
  name: list-products
- description: Get detailed catalog attributes, features, and add-ons for a specific software product.
  hints:
    openWorld: true
    readOnly: true
  name: get-product
- description: List software vendors in the Vendr catalog with their product portfolios and category information.
  hints:
    openWorld: true
    readOnly: true
  name: list-vendors
- description: Get fair price predictions and negotiation guidance for a software product. Powered by Vendr's database of real software purchases.
  hints:
    openWorld: true
    readOnly: true
  name: get-pricing-insights
- description: Create a webhook to receive notifications when Vendr pricing or catalog data is updated.
  hints:
    openWorld: false
    readOnly: false
  name: create-webhook
---

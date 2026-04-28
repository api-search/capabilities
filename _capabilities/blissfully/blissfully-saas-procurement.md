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
- create a webhook to receive notifications when vendr pricing or catalog data is updated.
- procurement
- software product catalog search and browsing
- software purchasing, negotiation, and vendor management
- portfolio visibility, spend optimization, and renewal management
- get detailed catalog attributes, features, and add-ons for a specific software product.
- pricing intelligence and negotiation guidance
- search and browse software products in the vendr catalog. returns structured attributes, features, and available add-ons.
- AI Assistant
- get fair price predictions and negotiation guidance for a software product. powered by vendr's database of real software purchases.
- list vendors
- pricing intelligence
- saas catalog browsing, pricing benchmarks, and negotiation guidance
- evaluates software capabilities and manages the saas portfolio
- researches software options, benchmarks pricing, and negotiates with vendors
- software procurement
- Procurement Manager
- spend optimization
- vendor management
- software vendor catalog
- analyzes saas spend, benchmarks costs, and identifies savings opportunities
- provides ai-assisted procurement recommendations via mcp integration
- list software vendors
- search and browse software products in the vendr catalog
- get pricing insights
- ai procurement
- create webhook
- saas management
- IT Manager
- Finance Analyst
- saas discovery
- list products
- software catalog
- get product
- list software vendors in the vendr catalog with their product portfolios and category information.
- get fair price benchmarks and negotiation guidance
slug: blissfully-saas-procurement
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

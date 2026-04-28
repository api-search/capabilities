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
- saas discovery
- search and browse software products in the vendr catalog
- spend optimization
- evaluates software capabilities and manages the saas portfolio
- get fair price predictions and negotiation guidance for a software product. powered by vendr's database of real software purchases.
- saas catalog browsing, pricing benchmarks, and negotiation guidance
- Finance Analyst
- procurement
- ai procurement
- provides ai-assisted procurement recommendations via mcp integration
- IT Manager
- vendor management
- list software vendors in the vendr catalog with their product portfolios and category information.
- search and browse software products in the vendr catalog. returns structured attributes, features, and available add-ons.
- pricing intelligence
- list products
- analyzes saas spend, benchmarks costs, and identifies savings opportunities
- get fair price benchmarks and negotiation guidance
- pricing intelligence and negotiation guidance
- get product
- get pricing insights
- software purchasing, negotiation, and vendor management
- create a webhook to receive notifications when vendr pricing or catalog data is updated.
- software vendor catalog
- list software vendors
- software catalog
- Procurement Manager
- portfolio visibility, spend optimization, and renewal management
- get detailed catalog attributes, features, and add-ons for a specific software product.
- researches software options, benchmarks pricing, and negotiates with vendors
- software procurement
- create webhook
- software product catalog search and browsing
- list vendors
- saas management
- AI Assistant
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

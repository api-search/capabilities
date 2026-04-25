---
consumed_apis:
- ait
description: Workflow capability for industrial product procurement using the Applied Industrial Technologies catalog. Combines product search and order management for procurement teams sourcing bearings, power transmission, and fluid power components.
layout: capability
name: Applied Industrial Technologies Procurement
operations: []
personas: []
provider_name: Applied Industrial Technologies
provider_slug: applied-industrial-technologies
search_terms:
- place order
- sources replacement parts and components for equipment maintenance
- supply chain
- creating and tracking purchase orders
- lists existing purchase orders for the authenticated account
- industrial distribution
- searches the applied industrial technologies product catalog by category or manufacturer
- places a purchase order for industrial products with shipping address
- list orders
- fluid power
- end-to-end workflow for sourcing and ordering industrial components
- gets detailed specifications for a specific industrial product
- bearings
- power transmission
- manages industrial component sourcing and purchase orders
- procurement
- browsing and searching the industrial product catalog
- get product details
- applied industrial technologies
- search products
slug: industrial-procurement
tags:
- Applied Industrial Technologies
- Industrial Distribution
- Procurement
- Supply Chain
tools:
- description: Searches the Applied Industrial Technologies product catalog by category or manufacturer
  hints:
    idempotent: true
    readOnly: true
  name: search-products
- description: Gets detailed specifications for a specific industrial product
  hints:
    idempotent: true
    readOnly: true
  name: get-product-details
- description: Places a purchase order for industrial products with shipping address
  hints:
    destructive: false
    readOnly: false
  name: place-order
- description: Lists existing purchase orders for the authenticated account
  hints:
    idempotent: true
    readOnly: true
  name: list-orders
---

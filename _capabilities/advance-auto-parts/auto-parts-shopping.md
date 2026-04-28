---
categories: []
consumed_apis:
- aap-catalog
description: Unified workflow capability for automotive parts discovery, fitment lookup, inventory checking, ordering, and loyalty management. Designed for automotive technicians, fleet managers, and DIY customers.
layout: capability
name: Advance Auto Parts Shopping
operations:
- description: Search for automotive parts.
  method: GET
  name: search-parts
  path: /v1/parts
- description: Get automotive part details.
  method: GET
  name: get-part
  path: /v1/parts/{productId}
- description: Check part inventory at stores.
  method: GET
  name: check-inventory
  path: /v1/inventory
personas: []
provider_name: Advance Auto Parts
provider_slug: advance-auto-parts
search_terms:
- retail
- check if an automotive part is in stock at nearby advance auto parts stores.
- do-it-yourself automotive enthusiast sourcing parts for self-repairs
- advance auto parts
- parts catalog
- check inventory
- parts catalog search.
- diy customer
- check part availability
- search auto parts
- professional mechanic using the api to source parts for repair jobs
- search for automotive parts by keyword, part number, or vehicle year/make/model.
- loyalty
- get vehicle years
- part details.
- get full specifications, fitment notes, and pricing for a specific automotive part.
- find advance auto parts store locations near a zip code or city.
- fleet operations manager ordering parts for vehicle maintenance programs
- store inventory.
- find nearby stores
- unified workflow for automotive parts discovery, fitment lookup, inventory, and ordering
- supply chain
- get part
- automotive
- search for automotive parts.
- get the range of supported vehicle model years for parts catalog lookups.
- get available vehicle makes for a given model year for fitment-based part search.
- get part details
- lookup vehicle models
- automotive technician
- get available vehicle models for a year and make for fitment-based part search.
- fleet manager
- get automotive part details.
- search parts
- lookup vehicle makes
- e-commerce
- check part inventory at stores.
slug: auto-parts-shopping
tags:
- Advance Auto Parts
- Automotive
- E-Commerce
- Parts Catalog
- Loyalty
tools:
- description: Search for automotive parts by keyword, part number, or vehicle year/make/model.
  hints:
    openWorld: true
    readOnly: true
  name: search-auto-parts
- description: Get full specifications, fitment notes, and pricing for a specific automotive part.
  hints:
    openWorld: false
    readOnly: true
  name: get-part-details
- description: Check if an automotive part is in stock at nearby Advance Auto Parts stores.
  hints:
    openWorld: true
    readOnly: true
  name: check-part-availability
- description: Find Advance Auto Parts store locations near a ZIP code or city.
  hints:
    openWorld: true
    readOnly: true
  name: find-nearby-stores
- description: Get available vehicle makes for a given model year for fitment-based part search.
  hints:
    openWorld: true
    readOnly: true
  name: lookup-vehicle-makes
- description: Get available vehicle models for a year and make for fitment-based part search.
  hints:
    openWorld: true
    readOnly: true
  name: lookup-vehicle-models
- description: Get the range of supported vehicle model years for parts catalog lookups.
  hints:
    openWorld: true
    readOnly: true
  name: get-vehicle-years
---

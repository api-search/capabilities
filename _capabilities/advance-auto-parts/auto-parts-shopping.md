---
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
- e-commerce
- diy customer
- get part details
- lookup vehicle makes
- do-it-yourself automotive enthusiast sourcing parts for self-repairs
- lookup vehicle models
- get part
- retail
- check inventory
- professional mechanic using the api to source parts for repair jobs
- parts catalog search.
- get full specifications, fitment notes, and pricing for a specific automotive part.
- check if an automotive part is in stock at nearby advance auto parts stores.
- get vehicle years
- search for automotive parts.
- check part inventory at stores.
- part details.
- get the range of supported vehicle model years for parts catalog lookups.
- supply chain
- fleet manager
- search for automotive parts by keyword, part number, or vehicle year/make/model.
- advance auto parts
- check part availability
- search auto parts
- unified workflow for automotive parts discovery, fitment lookup, inventory, and ordering
- fleet operations manager ordering parts for vehicle maintenance programs
- store inventory.
- automotive technician
- get automotive part details.
- find advance auto parts store locations near a zip code or city.
- get available vehicle makes for a given model year for fitment-based part search.
- find nearby stores
- parts catalog
- automotive
- get available vehicle models for a year and make for fitment-based part search.
- search parts
- loyalty
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

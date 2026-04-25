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
- check if an automotive part is in stock at nearby advance auto parts stores.
- lookup vehicle makes
- get the range of supported vehicle model years for parts catalog lookups.
- get automotive part details.
- lookup vehicle models
- automotive
- unified workflow for automotive parts discovery, fitment lookup, inventory, and ordering
- advance auto parts
- fleet operations manager ordering parts for vehicle maintenance programs
- check part inventory at stores.
- search for automotive parts.
- check inventory
- fleet manager
- part details.
- diy customer
- find nearby stores
- get part
- get full specifications, fitment notes, and pricing for a specific automotive part.
- search auto parts
- store inventory.
- get available vehicle models for a year and make for fitment-based part search.
- do-it-yourself automotive enthusiast sourcing parts for self-repairs
- parts catalog
- check part availability
- retail
- automotive technician
- supply chain
- e-commerce
- search for automotive parts by keyword, part number, or vehicle year/make/model.
- get vehicle years
- get available vehicle makes for a given model year for fitment-based part search.
- loyalty
- search parts
- find advance auto parts store locations near a zip code or city.
- parts catalog search.
- get part details
- professional mechanic using the api to source parts for repair jobs
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

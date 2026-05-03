---
categories: []
consumed_apis:
- tripadvisor-content
description: Workflow capability for integrating Tripadvisor's travel content into applications. Combines location search, detail retrieval, photos, and reviews into a unified travel discovery and content enrichment workflow. Designed for travel apps, destination guides, hotel comparison sites, and restaurant recommendation platforms.
layout: capability
name: Tripadvisor Travel Content
operations:
- description: Search Tripadvisor for locations by keyword and category
  method: GET
  name: search-locations
  path: /v1/locations/search
- description: Find locations near a specific latitude/longitude
  method: GET
  name: search-nearby
  path: /v1/locations/nearby
- description: Get name, address, rating, and listing URL for a location
  method: GET
  name: get-location
  path: /v1/locations/{locationId}
- description: Get recent photos in multiple sizes
  method: GET
  name: get-photos
  path: /v1/locations/{locationId}/photos
- description: Get up to 5 most recent reviews for a location
  method: GET
  name: get-reviews
  path: /v1/locations/{locationId}/reviews
personas: []
provider_name: Tripadvisor
provider_slug: tripadvisor
search_terms:
- search for hotels, restaurants, and attractions
- hotels
- get traveler reviews
- get location photos
- restaurants
- get photos for a location
- get full details for a specific location
- find locations near a specific latitude/longitude
- locations
- hospitality
- reviews
- search tripadvisor for locations by keyword and category
- get recent high-quality photos for a tripadvisor location. returns photos in multiple size formats (thumbnail, small, medium, large, original).
- get name, address, rating, and listing url for a location
- content
- find nearby locations by coordinates
- get recent traveler reviews
- search tripadvisor for hotels, restaurants, or attractions by keyword, category, address, or geographic coordinates. returns up to 10 matching locations with ids, names, and addresses.
- get recent photos in multiple sizes
- search locations
- get up to 5 most recent reviews for a location
- search travel locations
- get location details
- get photos
- get reviews
- get location
- find nearby attractions
- search nearby
- get the most recent traveler reviews for a tripadvisor location. reviews include rating, text, author, travel date, and trip type.
- find hotels, restaurants, or attractions near a specific geographic point. provide latitude and longitude to discover what's nearby.
- travel
- attractions
- get comprehensive details for a tripadvisor location including name, address, overall rating, review count, ranking, categories, trip types, and direct link to the tripadvisor listing.
slug: travel-content
source_filename: travel-content.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tripadvisor Travel Content\"\n  description: >-\n    Workflow capability for integrating Tripadvisor's travel content into applications.\n    Combines location search, detail retrieval, photos, and reviews into a unified\n    travel discovery and content enrichment workflow. Designed for travel apps,\n    destination guides, hotel comparison sites, and restaurant recommendation platforms.\n  tags:\n    - Attractions\n    - Content\n    - Hotels\n    - Locations\n    - Restaurants\n    - Reviews\n    - Travel\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRIPADVISOR_API_KEY: TRIPADVISOR_API_KEY\n\ncapability:\n  consumes:\n    - import: tripadvisor-content\n      location: ./shared/content-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tripadvisor-travel-content-api\n      description: \"Unified REST API for discovering and displaying Tripadvisor\
  \ travel content.\"\n      resources:\n        - path: /v1/locations/search\n          name: location-search\n          description: \"Search for hotels, restaurants, and attractions\"\n          operations:\n            - method: GET\n              name: search-locations\n              description: \"Search Tripadvisor for locations by keyword and category\"\n              call: \"tripadvisor-content.search-for-locations\"\n              with:\n                searchQuery: \"rest.searchQuery\"\n                category: \"rest.category\"\n                language: \"rest.language\"\n                latLong: \"rest.latLong\"\n                radius: \"rest.radius\"\n                radiusUnit: \"rest.radiusUnit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/locations/nearby\n          name: nearby-search\n          description: \"Find nearby locations by coordinates\"\n          operations:\n            - method:\
  \ GET\n              name: search-nearby\n              description: \"Find locations near a specific latitude/longitude\"\n              call: \"tripadvisor-content.search-for-nearby-locations\"\n              with:\n                latLong: \"rest.latLong\"\n                category: \"rest.category\"\n                language: \"rest.language\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/locations/{locationId}\n          name: location-details\n          description: \"Get full details for a specific location\"\n          operations:\n            - method: GET\n              name: get-location\n              description: \"Get name, address, rating, and listing URL for a location\"\n              call: \"tripadvisor-content.get-location-details\"\n              with:\n                locationId: \"rest.locationId\"\n                language: \"rest.language\"\n                currency: \"rest.currency\"\n \
  \             outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/locations/{locationId}/photos\n          name: location-photos\n          description: \"Get photos for a location\"\n          operations:\n            - method: GET\n              name: get-photos\n              description: \"Get recent photos in multiple sizes\"\n              call: \"tripadvisor-content.get-location-photos\"\n              with:\n                locationId: \"rest.locationId\"\n                language: \"rest.language\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/locations/{locationId}/reviews\n          name: location-reviews\n          description: \"Get recent traveler reviews\"\n          operations:\n            - method: GET\n              name: get-reviews\n              description: \"Get up to 5 most recent reviews for a location\"\n              call: \"tripadvisor-content.get-location-reviews\"\
  \n              with:\n                locationId: \"rest.locationId\"\n                language: \"rest.language\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tripadvisor-travel-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted travel content discovery and enrichment using Tripadvisor.\"\n      tools:\n        - name: search-travel-locations\n          description: >-\n            Search Tripadvisor for hotels, restaurants, or attractions by keyword,\n            category, address, or geographic coordinates. Returns up to 10 matching\n            locations with IDs, names, and addresses.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tripadvisor-content.search-for-locations\"\n          with:\n            searchQuery: \"tools.searchQuery\"\n            category: \"tools.category\"\n            language:\
  \ \"tools.language\"\n            latLong: \"tools.latLong\"\n            radius: \"tools.radius\"\n            radiusUnit: \"tools.radiusUnit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-nearby-attractions\n          description: >-\n            Find hotels, restaurants, or attractions near a specific geographic point.\n            Provide latitude and longitude to discover what's nearby.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tripadvisor-content.search-for-nearby-locations\"\n          with:\n            latLong: \"tools.latLong\"\n            category: \"tools.category\"\n            language: \"tools.language\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-location-details\n          description: >-\n            Get comprehensive details for a Tripadvisor location including name,\n            address,\
  \ overall rating, review count, ranking, categories, trip types,\n            and direct link to the Tripadvisor listing.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tripadvisor-content.get-location-details\"\n          with:\n            locationId: \"tools.locationId\"\n            language: \"tools.language\"\n            currency: \"tools.currency\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-location-photos\n          description: >-\n            Get recent high-quality photos for a Tripadvisor location.\n            Returns photos in multiple size formats (thumbnail, small, medium, large, original).\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tripadvisor-content.get-location-photos\"\n          with:\n            locationId: \"tools.locationId\"\n            language: \"tools.language\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-traveler-reviews\n          description: >-\n            Get the most recent traveler reviews for a Tripadvisor location.\n            Reviews include rating, text, author, travel date, and trip type.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tripadvisor-content.get-location-reviews\"\n          with:\n            locationId: \"tools.locationId\"\n            language: \"tools.language\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tripadvisor/refs/heads/main/capabilities/travel-content.yaml
tags:
- Attractions
- Content
- Hotels
- Locations
- Restaurants
- Reviews
- Travel
tools:
- description: Search Tripadvisor for hotels, restaurants, or attractions by keyword, category, address, or geographic coordinates. Returns up to 10 matching locations with IDs, names, and addresses.
  hints:
    openWorld: true
    readOnly: true
  name: search-travel-locations
- description: Find hotels, restaurants, or attractions near a specific geographic point. Provide latitude and longitude to discover what's nearby.
  hints:
    openWorld: true
    readOnly: true
  name: find-nearby-attractions
- description: Get comprehensive details for a Tripadvisor location including name, address, overall rating, review count, ranking, categories, trip types, and direct link to the Tripadvisor listing.
  hints:
    openWorld: false
    readOnly: true
  name: get-location-details
- description: Get recent high-quality photos for a Tripadvisor location. Returns photos in multiple size formats (thumbnail, small, medium, large, original).
  hints:
    openWorld: false
    readOnly: true
  name: get-location-photos
- description: Get the most recent traveler reviews for a Tripadvisor location. Reviews include rating, text, author, travel date, and trip type.
  hints:
    openWorld: false
    readOnly: true
  name: get-traveler-reviews
---

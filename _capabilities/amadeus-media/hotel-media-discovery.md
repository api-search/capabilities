---
categories:
- travel-booking
consumed_apis:
- hotel-content
- hotel-list
description: Workflow capability for discovering and retrieving hotel media content, combining the Hotel List API for property discovery with the Hotel Content API for rich media retrieval. Used by travel platform developers, OTA content teams, and hospitality technology teams building hotel profile pages.
layout: capability
name: Amadeus Hotel Media Discovery
operations:
- description: Find hotels in a city by IATA code.
  method: GET
  name: get-hotels-by-city
  path: /v1/hotels
- description: Find hotels near geographic coordinates.
  method: GET
  name: get-hotels-by-geocode
  path: /v1/hotels
- description: Get detailed hotel property content.
  method: GET
  name: get-hotel-content
  path: /v1/hotels/{hotelId}/content
- description: Get hotel photos and media assets.
  method: GET
  name: get-hotel-media
  path: /v1/hotels/{hotelId}/media
personas: []
provider_name: Amadeus Media
provider_slug: amadeus-media
search_terms:
- media
- get hotel media
- find hotels near a geographic location using latitude and longitude coordinates.
- hotel media assets including images.
- get hotels by city
- images
- visual media assets including photos and videos for hotel properties.
- hotel property content and descriptions.
- get hotels by geocode
- get hotel content
- get hotel details
- get detailed hotel property content.
- find hotels by city
- find hotels near geographic coordinates.
- content team maintaining hotel profiles, photos, and descriptions on online travel agencies.
- get hotel photos and media assets.
- get hotel photos
- retrieve hotel photos and media assets organized by category (exterior, lobby, rooms, restaurant, pool, spa).
- Travel Platform Developer
- OTA Content Team
- find hotels in a city using its iata code for content and media retrieval.
- retrieve rich hotel property content including descriptions, amenities, address, and contact information.
- amadeus
- find hotels in a city by iata code.
- travel
- find hotels by location
- combines hotel list and hotel content apis for comprehensive hotel property discovery with rich media retrieval.
- hotel property information, descriptions, and classifications.
- hotel discovery and search.
- content
- developer building hotel search and booking experiences requiring property data and media.
- hotels
slug: hotel-media-discovery
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amadeus Hotel Media Discovery\n  description: >-\n    Workflow capability for discovering and retrieving hotel media content, combining the Hotel List API for property discovery with the Hotel Content API for rich media retrieval. Used by travel platform developers, OTA content teams, and hospitality technology teams building hotel profile pages.\n  tags:\n    - Amadeus\n    - Hotels\n    - Media\n    - Content\n    - Travel\n    - Images\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AMADEUS_API_KEY: AMADEUS_API_KEY\n      AMADEUS_API_SECRET: AMADEUS_API_SECRET\n      AMADEUS_BEARER_TOKEN: AMADEUS_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: hotel-content\n      location: ./shared/hotel-content.yaml\n    - import: hotel-list\n      location: ./shared/hotel-list.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: hotel-media-discovery-api\n  \
  \    description: Unified REST API for hotel property discovery and media retrieval.\n      resources:\n        - path: /v1/hotels\n          name: hotels\n          description: Hotel discovery and search.\n          operations:\n            - method: GET\n              name: get-hotels-by-city\n              description: Find hotels in a city by IATA code.\n              call: \"hotel-list.get-hotels-by-city\"\n              with:\n                cityCode: \"rest.cityCode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-hotels-by-geocode\n              description: Find hotels near geographic coordinates.\n              call: \"hotel-list.get-hotels-by-geocode\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n      \
  \  - path: /v1/hotels/{hotelId}/content\n          name: hotel-content\n          description: Hotel property content and descriptions.\n          operations:\n            - method: GET\n              name: get-hotel-content\n              description: Get detailed hotel property content.\n              call: \"hotel-content.get-hotel-content\"\n              with:\n                hotelIds: \"rest.hotelId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hotels/{hotelId}/media\n          name: hotel-media\n          description: Hotel media assets including images.\n          operations:\n            - method: GET\n              name: get-hotel-media\n              description: Get hotel photos and media assets.\n              call: \"hotel-content.get-hotel-media\"\n              with:\n                hotelIds: \"rest.hotelId\"\n              outputParameters:\n                - type: object\n                 \
  \ mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: hotel-media-discovery-mcp\n      transport: http\n      description: MCP server for AI-assisted hotel content and media discovery.\n      tools:\n        - name: find-hotels-by-city\n          description: Find hotels in a city using its IATA code for content and media retrieval.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hotel-list.get-hotels-by-city\"\n          with:\n            cityCode: \"tools.cityCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-hotels-by-location\n          description: Find hotels near a geographic location using latitude and longitude coordinates.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hotel-list.get-hotels-by-geocode\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-hotel-details\n          description: Retrieve rich hotel property content including descriptions, amenities, address, and contact information.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hotel-content.get-hotel-content\"\n          with:\n            hotelIds: \"tools.hotelIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-hotel-photos\n          description: Retrieve hotel photos and media assets organized by category (exterior, lobby, rooms, restaurant, pool, spa).\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hotel-content.get-hotel-media\"\n          with:\n            hotelIds: \"tools.hotelIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amadeus-media/refs/heads/main/capabilities/hotel-media-discovery.yaml
tags:
- Amadeus
- Hotels
- Media
- Content
- Travel
- Images
tools:
- description: Find hotels in a city using its IATA code for content and media retrieval.
  hints:
    openWorld: true
    readOnly: true
  name: find-hotels-by-city
- description: Find hotels near a geographic location using latitude and longitude coordinates.
  hints:
    openWorld: true
    readOnly: true
  name: find-hotels-by-location
- description: Retrieve rich hotel property content including descriptions, amenities, address, and contact information.
  hints:
    openWorld: true
    readOnly: true
  name: get-hotel-details
- description: Retrieve hotel photos and media assets organized by category (exterior, lobby, rooms, restaurant, pool, spa).
  hints:
    openWorld: true
    readOnly: true
  name: get-hotel-photos
---

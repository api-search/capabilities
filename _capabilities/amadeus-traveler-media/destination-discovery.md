---
categories:
- travel-booking
consumed_apis:
- points-of-interest
- hotel-ratings
description: Workflow capability for discovering destinations and media content, combining Points of Interest, Hotel Ratings, Travel Recommendations, and Location Score APIs. Used by travel app developers, destination marketing organizations, and travel content platforms building rich destination discovery experiences.
layout: capability
name: Amadeus Destination Discovery
operations:
- description: Find attractions and points of interest near a location.
  method: GET
  name: search-pois
  path: /v1/destinations/pois
- description: Get details for a specific point of interest.
  method: GET
  name: get-poi
  path: /v1/destinations/pois/{poiId}
- description: Get hotel sentiment ratings.
  method: GET
  name: get-hotel-ratings
  path: /v1/hotels/ratings
personas: []
provider_name: Amadeus Traveler Media
provider_slug: amadeus-traveler-media
search_terms:
- tourism
- get attraction details
- get poi
- search attractions
- discovery
- points of interest
- hotel sentiment ratings.
- content
- points of interest discovery.
- search pois
- media
- travel
- retrieve detailed information about a specific tourist attraction or point of interest.
- content manager building rich destination guides with attractions and ratings.
- find attractions and points of interest near a location.
- Travel App Developer
- destination
- get hotel sentiment ratings.
- amadeus
- Destination Content Manager
- photos
- destinations
- hotels
- find tourist attractions, museums, restaurants, and other points of interest near a geographic location.
- developer building destination discovery and travel planning applications.
- hotel ratings and traveler sentiment data.
- get details for a specific point of interest.
- individual point of interest details.
- retrieve sentiment-based ratings for hotels derived from traveler reviews, covering location, comfort, service, food, and facilities categories.
- discover destinations with pois, hotel ratings, and recommendations.
- get hotel sentiment ratings
- tourist attractions, pois, and destination information.
- get hotel ratings
slug: destination-discovery
source_filename: destination-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amadeus Destination Discovery\n  description: >-\n    Workflow capability for discovering destinations and media content, combining\n    Points of Interest, Hotel Ratings, Travel Recommendations, and Location Score\n    APIs. Used by travel app developers, destination marketing organizations, and\n    travel content platforms building rich destination discovery experiences.\n  tags:\n    - Amadeus\n    - Destinations\n    - Discovery\n    - Hotels\n    - Media\n    - Points of Interest\n    - Tourism\n    - Travel\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AMADEUS_BEARER_TOKEN: AMADEUS_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: points-of-interest\n      location: ./shared/points-of-interest.yaml\n    - import: hotel-ratings\n      location: ./shared/hotel-ratings.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: destination-discovery-api\n\
  \      description: Unified REST API for destination content and traveler media.\n      resources:\n        - path: /v1/destinations/pois\n          name: pois\n          description: Points of interest discovery.\n          operations:\n            - method: GET\n              name: search-pois\n              description: Find attractions and points of interest near a location.\n              call: \"points-of-interest.get-points-of-interest\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/destinations/pois/{poiId}\n          name: poi\n          description: Individual point of interest details.\n          operations:\n            - method: GET\n              name: get-poi\n              description: Get details for a specific point of interest.\n              call: \"points-of-interest.get-poi-by-id\"\
  \n              with:\n                poiId: \"rest.poiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hotels/ratings\n          name: hotel-ratings\n          description: Hotel sentiment ratings.\n          operations:\n            - method: GET\n              name: get-hotel-ratings\n              description: Get hotel sentiment ratings.\n              call: \"hotel-ratings.get-hotel-ratings\"\n              with:\n                hotelIds: \"rest.hotelIds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: destination-discovery-mcp\n      transport: http\n      description: MCP server for AI-assisted destination discovery and travel media.\n      tools:\n        - name: search-attractions\n          description: Find tourist attractions, museums, restaurants, and other points of interest near a geographic\
  \ location.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"points-of-interest.get-points-of-interest\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-attraction-details\n          description: Retrieve detailed information about a specific tourist attraction or point of interest.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"points-of-interest.get-poi-by-id\"\n          with:\n            poiId: \"tools.poiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-hotel-sentiment-ratings\n          description: Retrieve sentiment-based ratings for hotels derived from traveler reviews, covering location, comfort, service, food, and facilities categories.\n          hints:\n   \
  \         readOnly: true\n            openWorld: true\n          call: \"hotel-ratings.get-hotel-ratings\"\n          with:\n            hotelIds: \"tools.hotelIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amadeus-traveler-media/refs/heads/main/capabilities/destination-discovery.yaml
tags:
- Amadeus
- Destinations
- Discovery
- Hotels
- Media
- Points of Interest
- Tourism
- Travel
tools:
- description: Find tourist attractions, museums, restaurants, and other points of interest near a geographic location.
  hints:
    openWorld: true
    readOnly: true
  name: search-attractions
- description: Retrieve detailed information about a specific tourist attraction or point of interest.
  hints:
    openWorld: true
    readOnly: true
  name: get-attraction-details
- description: Retrieve sentiment-based ratings for hotels derived from traveler reviews, covering location, comfort, service, food, and facilities categories.
  hints:
    openWorld: true
    readOnly: true
  name: get-hotel-sentiment-ratings
---

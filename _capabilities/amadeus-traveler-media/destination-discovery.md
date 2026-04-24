---
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
- retrieve sentiment-based ratings for hotels derived from traveler reviews, covering location, comfort, service, food, and facilities categories.
- hotel ratings and traveler sentiment data.
- points of interest
- Destination Content Manager
- discovery
- retrieve detailed information about a specific tourist attraction or point of interest.
- search pois
- content
- find tourist attractions, museums, restaurants, and other points of interest near a geographic location.
- developer building destination discovery and travel planning applications.
- tourism
- search attractions
- destinations
- get poi
- get hotel sentiment ratings
- amadeus
- destination
- Travel App Developer
- tourist attractions, pois, and destination information.
- find attractions and points of interest near a location.
- content manager building rich destination guides with attractions and ratings.
- media
- get hotel ratings
- points of interest discovery.
- photos
- discover destinations with pois, hotel ratings, and recommendations.
- hotel sentiment ratings.
- travel
- individual point of interest details.
- get hotel sentiment ratings.
- get details for a specific point of interest.
- hotels
- get attraction details
slug: destination-discovery
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

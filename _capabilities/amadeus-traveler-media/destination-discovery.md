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
- get details for a specific point of interest.
- travel
- tourism
- points of interest
- get poi
- developer building destination discovery and travel planning applications.
- Destination Content Manager
- Travel App Developer
- content
- retrieve sentiment-based ratings for hotels derived from traveler reviews, covering location, comfort, service, food, and facilities categories.
- get hotel sentiment ratings.
- points of interest discovery.
- discovery
- get attraction details
- content manager building rich destination guides with attractions and ratings.
- photos
- find tourist attractions, museums, restaurants, and other points of interest near a geographic location.
- individual point of interest details.
- discover destinations with pois, hotel ratings, and recommendations.
- search attractions
- amadeus
- hotel ratings and traveler sentiment data.
- search pois
- media
- retrieve detailed information about a specific tourist attraction or point of interest.
- destinations
- destination
- find attractions and points of interest near a location.
- hotel sentiment ratings.
- get hotel sentiment ratings
- get hotel ratings
- tourist attractions, pois, and destination information.
- hotels
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

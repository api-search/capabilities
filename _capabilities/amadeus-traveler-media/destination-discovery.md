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
- discovery
- hotels
- travel
- get hotel ratings
- developer building destination discovery and travel planning applications.
- content manager building rich destination guides with attractions and ratings.
- destinations
- points of interest
- destination
- get details for a specific point of interest.
- tourist attractions, pois, and destination information.
- hotel sentiment ratings.
- search attractions
- discover destinations with pois, hotel ratings, and recommendations.
- hotel ratings and traveler sentiment data.
- Destination Content Manager
- find attractions and points of interest near a location.
- individual point of interest details.
- get poi
- tourism
- search pois
- get attraction details
- amadeus
- retrieve sentiment-based ratings for hotels derived from traveler reviews, covering location, comfort, service, food, and facilities categories.
- find tourist attractions, museums, restaurants, and other points of interest near a geographic location.
- retrieve detailed information about a specific tourist attraction or point of interest.
- get hotel sentiment ratings
- photos
- points of interest discovery.
- content
- Travel App Developer
- media
- get hotel sentiment ratings.
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

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
- search attractions
- content manager building rich destination guides with attractions and ratings.
- tourist attractions, pois, and destination information.
- media
- get poi
- photos
- hotel sentiment ratings.
- discover destinations with pois, hotel ratings, and recommendations.
- Travel App Developer
- search pois
- get details for a specific point of interest.
- discovery
- individual point of interest details.
- points of interest
- destination
- get hotel sentiment ratings
- destinations
- hotels
- tourism
- get hotel sentiment ratings.
- retrieve detailed information about a specific tourist attraction or point of interest.
- retrieve sentiment-based ratings for hotels derived from traveler reviews, covering location, comfort, service, food, and facilities categories.
- amadeus
- travel
- developer building destination discovery and travel planning applications.
- get hotel ratings
- get attraction details
- hotel ratings and traveler sentiment data.
- find tourist attractions, museums, restaurants, and other points of interest near a geographic location.
- find attractions and points of interest near a location.
- Destination Content Manager
- content
- points of interest discovery.
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

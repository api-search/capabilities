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
- hotel ratings and traveler sentiment data.
- retrieve sentiment-based ratings for hotels derived from traveler reviews, covering location, comfort, service, food, and facilities categories.
- points of interest discovery.
- get hotel ratings
- destination
- search pois
- get poi
- retrieve detailed information about a specific tourist attraction or point of interest.
- tourist attractions, pois, and destination information.
- points of interest
- hotels
- discover destinations with pois, hotel ratings, and recommendations.
- search attractions
- content manager building rich destination guides with attractions and ratings.
- find attractions and points of interest near a location.
- tourism
- travel
- get hotel sentiment ratings
- Travel App Developer
- individual point of interest details.
- hotel sentiment ratings.
- get attraction details
- media
- get hotel sentiment ratings.
- photos
- content
- discovery
- destinations
- find tourist attractions, museums, restaurants, and other points of interest near a geographic location.
- developer building destination discovery and travel planning applications.
- amadeus
- Destination Content Manager
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

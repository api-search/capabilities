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
- content
- get poi
- get attraction details
- discover destinations with pois, hotel ratings, and recommendations.
- retrieve sentiment-based ratings for hotels derived from traveler reviews, covering location, comfort, service, food, and facilities categories.
- search pois
- amadeus
- destination
- find tourist attractions, museums, restaurants, and other points of interest near a geographic location.
- tourist attractions, pois, and destination information.
- retrieve detailed information about a specific tourist attraction or point of interest.
- photos
- discovery
- Destination Content Manager
- search attractions
- travel
- destinations
- hotel ratings and traveler sentiment data.
- hotel sentiment ratings.
- points of interest
- get hotel sentiment ratings.
- get hotel sentiment ratings
- get details for a specific point of interest.
- get hotel ratings
- hotels
- tourism
- points of interest discovery.
- find attractions and points of interest near a location.
- content manager building rich destination guides with attractions and ratings.
- media
- developer building destination discovery and travel planning applications.
- Travel App Developer
- individual point of interest details.
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

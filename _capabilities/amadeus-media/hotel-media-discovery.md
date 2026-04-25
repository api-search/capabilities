---
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
- hotel property information, descriptions, and classifications.
- find hotels near geographic coordinates.
- images
- get hotel photos and media assets.
- get hotel details
- retrieve hotel photos and media assets organized by category (exterior, lobby, rooms, restaurant, pool, spa).
- combines hotel list and hotel content apis for comprehensive hotel property discovery with rich media retrieval.
- get hotel media
- find hotels in a city by iata code.
- hotel property content and descriptions.
- hotel discovery and search.
- retrieve rich hotel property content including descriptions, amenities, address, and contact information.
- find hotels near a geographic location using latitude and longitude coordinates.
- find hotels by location
- hotels
- content team maintaining hotel profiles, photos, and descriptions on online travel agencies.
- visual media assets including photos and videos for hotel properties.
- OTA Content Team
- travel
- Travel Platform Developer
- find hotels in a city using its iata code for content and media retrieval.
- get hotel content
- get hotels by geocode
- media
- developer building hotel search and booking experiences requiring property data and media.
- content
- get hotels by city
- hotel media assets including images.
- get hotel photos
- amadeus
- find hotels by city
- get detailed hotel property content.
slug: hotel-media-discovery
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

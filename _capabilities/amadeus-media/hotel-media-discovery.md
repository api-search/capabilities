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
- visual media assets including photos and videos for hotel properties.
- Travel Platform Developer
- find hotels near geographic coordinates.
- get hotel photos and media assets.
- find hotels by city
- images
- get hotel content
- get hotel media
- find hotels in a city using its iata code for content and media retrieval.
- find hotels near a geographic location using latitude and longitude coordinates.
- get detailed hotel property content.
- hotel property content and descriptions.
- get hotel details
- hotel media assets including images.
- travel
- amadeus
- content
- find hotels by location
- OTA Content Team
- retrieve hotel photos and media assets organized by category (exterior, lobby, rooms, restaurant, pool, spa).
- content team maintaining hotel profiles, photos, and descriptions on online travel agencies.
- hotel discovery and search.
- hotels
- get hotel photos
- find hotels in a city by iata code.
- media
- get hotels by geocode
- hotel property information, descriptions, and classifications.
- developer building hotel search and booking experiences requiring property data and media.
- retrieve rich hotel property content including descriptions, amenities, address, and contact information.
- get hotels by city
- combines hotel list and hotel content apis for comprehensive hotel property discovery with rich media retrieval.
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

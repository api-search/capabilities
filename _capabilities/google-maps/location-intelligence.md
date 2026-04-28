---
categories: []
consumed_apis:
- google-maps-directions
- google-maps-geocoding
- google-maps-places
description: Unified workflow combining Google Maps Directions, Geocoding, and Places APIs for location-aware applications. Enables developers to geocode addresses, compute routes, search for places, and retrieve place details in a single integration.
layout: capability
name: Google Maps Location Intelligence
operations:
- description: Geocode an address or reverse geocode coordinates
  method: GET
  name: geocode
  path: /v1/geocode
- description: Get directions between two or more locations
  method: GET
  name: get-directions
  path: /v1/directions
- description: Get detailed information about a place
  method: GET
  name: get-place-details
  path: /v1/places/{placeId}
- description: Search for places using a text query
  method: POST
  name: search-places-text
  path: /v1/places/search-text
- description: Search for places near a location
  method: POST
  name: search-places-nearby
  path: /v1/places/search-nearby
- description: Get place predictions for input text
  method: POST
  name: autocomplete-places
  path: /v1/places/autocomplete
personas: []
provider_name: Google Maps Platform
provider_slug: google-maps
search_terms:
- route computation between locations
- get place predictions for input text
- get place details
- geocode
- directions
- autocomplete places
- solar
- place details retrieval
- maps
- search places nearby
- get place photo
- get place autocomplete predictions as the user types
- location-based place search
- places
- search for places using a natural language text query like 'pizza in new york'
- location
- place autocomplete predictions
- get a photo for a place by place id and photo reference
- get directions
- text-based place search
- navigation
- google maps
- search for places using a text query
- get detailed information about a place including address, rating, hours, and reviews
- search places text
- geocode an address or reverse geocode coordinates
- get directions between two or more locations with support for driving, walking, bicycling, and transit
- routing
- search for places near a specific location with type filters
- geolocation
- environment
- address to coordinate conversion and reverse geocoding
- get detailed information about a place
- get directions between two or more locations
- geocode an address to coordinates or reverse geocode coordinates to an address
- search for places near a location
- geocoding
slug: location-intelligence
tags:
- Google Maps
- Location
- Geocoding
- Directions
- Places
tools:
- description: Geocode an address to coordinates or reverse geocode coordinates to an address
  hints:
    openWorld: true
    readOnly: true
  name: geocode
- description: Get directions between two or more locations with support for driving, walking, bicycling, and transit
  hints:
    openWorld: true
    readOnly: true
  name: get-directions
- description: Get detailed information about a place including address, rating, hours, and reviews
  hints:
    openWorld: true
    readOnly: true
  name: get-place-details
- description: Search for places using a natural language text query like 'pizza in New York'
  hints:
    openWorld: true
    readOnly: true
  name: search-places-text
- description: Search for places near a specific location with type filters
  hints:
    openWorld: true
    readOnly: true
  name: search-places-nearby
- description: Get place autocomplete predictions as the user types
  hints:
    openWorld: true
    readOnly: true
  name: autocomplete-places
- description: Get a photo for a place by place ID and photo reference
  hints:
    openWorld: true
    readOnly: true
  name: get-place-photo
---

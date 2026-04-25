---
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
- address to coordinate conversion and reverse geocoding
- solar
- search places nearby
- geocode an address or reverse geocode coordinates
- autocomplete places
- geocoding
- get place autocomplete predictions as the user types
- search for places using a natural language text query like 'pizza in new york'
- get detailed information about a place
- get place predictions for input text
- place autocomplete predictions
- directions
- geocode an address to coordinates or reverse geocode coordinates to an address
- geocode
- text-based place search
- places
- get a photo for a place by place id and photo reference
- google maps
- search for places near a specific location with type filters
- routing
- get place photo
- geolocation
- route computation between locations
- location
- get place details
- search for places using a text query
- search for places near a location
- environment
- get directions between two or more locations with support for driving, walking, bicycling, and transit
- navigation
- location-based place search
- place details retrieval
- get directions between two or more locations
- maps
- get directions
- search places text
- get detailed information about a place including address, rating, hours, and reviews
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

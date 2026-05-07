---
categories: []
consumed_apis: []
description: Use Radar APIs as building blocks for location-based products and services like pickup and delivery tracking, location-triggered notifications, location verification, store locators, address autocomplete, and more. Or, use Radar APIs to manage your Radar data, including users, geofences, and events.
layout: capability
name: Radar API
operations:
- description: Track a user location
  method: POST
  name: post-track
  path: /track
- description: Forward geocode an address
  method: GET
  name: get-geocode-forward
  path: /geocode/forward
- description: Reverse geocode coordinates
  method: GET
  name: get-geocode-reverse
  path: /geocode/reverse
- description: IP geocode
  method: GET
  name: get-geocode-ip
  path: /geocode/ip
- description: Address autocomplete
  method: GET
  name: get-search-autocomplete
  path: /search/autocomplete
- description: Search users
  method: GET
  name: get-search-users
  path: /search/users
- description: Search geofences
  method: GET
  name: get-search-geofences
  path: /search/geofences
- description: Search places
  method: GET
  name: get-search-places
  path: /search/places
- description: Validate an address
  method: GET
  name: get-addresses-validate
  path: /addresses/validate
- description: Calculate distance between two points
  method: GET
  name: get-route-distance
  path: /route/distance
- description: Distance matrix routing
  method: GET
  name: get-route-matrix
  path: /route/matrix
- description: Match a sequence of coordinates to roads
  method: GET
  name: get-route-match
  path: /route/match
- description: Get directions between points
  method: GET
  name: get-route-directions
  path: /route/directions
- description: Route optimization
  method: GET
  name: get-route-optimize
  path: /route/optimize
- description: List users
  method: GET
  name: get-users
  path: /users
- description: Retrieve a user
  method: GET
  name: get-users-userid
  path: /users/{userId}
- description: Update a user
  method: PUT
  name: put-users-userid
  path: /users/{userId}
- description: Delete a user
  method: DELETE
  name: delete-users-userid
  path: /users/{userId}
- description: List geofences
  method: GET
  name: get-geofences
  path: /geofences
- description: Create a geofence
  method: POST
  name: post-geofences
  path: /geofences
- description: Retrieve a geofence
  method: GET
  name: get-geofences-geofenceid
  path: /geofences/{geofenceId}
- description: Update a geofence
  method: PUT
  name: put-geofences-geofenceid
  path: /geofences/{geofenceId}
- description: Delete a geofence
  method: DELETE
  name: delete-geofences-geofenceid
  path: /geofences/{geofenceId}
- description: List events
  method: GET
  name: get-events
  path: /events
- description: Retrieve an event
  method: GET
  name: get-events-eventid
  path: /events/{eventId}
personas: []
provider_name: Radar
provider_slug: radar
search_terms:
- retrieve a geofence
- get geofences geofenceid
- calculate distance between two points
- get search geofences
- post geofences
- delete geofences geofenceid
- reverse geocode coordinates
- list events
- geocoding
- search geofences
- get route match
- get geocode forward
- api
- get events eventid
- track a user location
- delete a user
- ip geocode
- get route optimize
- create a geofence
- forward geocode an address
- get search places
- put users userid
- get route matrix
- get users userid
- search users
- match a sequence of coordinates to roads
- get geocode ip
- get search users
- get search autocomplete
- list users
- get route distance
- route optimization
- routing
- get events
- location
- get directions between points
- retrieve a user
- maps
- get addresses validate
- validate an address
- address autocomplete
- post track
- get route directions
- put geofences geofenceid
- get geofences
- retrieve an event
- search places
- list geofences
- radar
- delete users userid
- update a user
- get geocode reverse
- update a geofence
- get users
- delete a geofence
- geofencing
- distance matrix routing
slug: radar-capability
source_filename: radar-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Radar API\n  description: Use Radar APIs as building blocks for location-based products and services like pickup and delivery tracking,\n    location-triggered notifications, location verification, store locators, address autocomplete, and more. Or, use Radar\n    APIs to manage your Radar data, including users, geofences, and events.\n  tags:\n  - Radar\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: radar\n    baseUri: https://api.radar.io/v1\n    description: Radar API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{RADAR_TOKEN}}'\n    resources:\n    - name: track\n      path: /track\n      operations:\n      - name: post-track\n        method: POST\n        description: Track a user location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: geocode-forward\n      path: /geocode/forward\n      operations:\n      - name: get-geocode-forward\n        method: GET\n        description: Forward geocode an address\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: geocode-reverse\n      path: /geocode/reverse\n      operations:\n      - name: get-geocode-reverse\n        method: GET\n        description: Reverse geocode coordinates\n        inputParameters:\n        - name: coordinates\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: geocode-ip\n      path: /geocode/ip\n      operations:\n      - name: get-geocode-ip\n        method:\
  \ GET\n        description: IP geocode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-autocomplete\n      path: /search/autocomplete\n      operations:\n      - name: get-search-autocomplete\n        method: GET\n        description: Address autocomplete\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-users\n      path: /search/users\n      operations:\n      - name: get-search-users\n        method: GET\n        description: Search users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-geofences\n      path: /search/geofences\n      operations:\n      - name: get-search-geofences\n\
  \        method: GET\n        description: Search geofences\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-places\n      path: /search/places\n      operations:\n      - name: get-search-places\n        method: GET\n        description: Search places\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: addresses-validate\n      path: /addresses/validate\n      operations:\n      - name: get-addresses-validate\n        method: GET\n        description: Validate an address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: route-distance\n      path: /route/distance\n      operations:\n      - name: get-route-distance\n        method: GET\n        description: Calculate distance between two points\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: route-matrix\n      path: /route/matrix\n      operations:\n      - name: get-route-matrix\n        method: GET\n        description: Distance matrix routing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: route-match\n      path: /route/match\n      operations:\n      - name: get-route-match\n        method: GET\n        description: Match a sequence of coordinates to roads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: route-directions\n      path: /route/directions\n      operations:\n      - name: get-route-directions\n        method: GET\n        description: Get directions between points\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: route-optimize\n      path: /route/optimize\n      operations:\n      - name: get-route-optimize\n        method: GET\n        description: Route optimization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: get-users\n        method: GET\n        description: List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid\n      path: /users/{userId}\n      operations:\n      - name: get-users-userid\n        method: GET\n        description: Retrieve a user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: put-users-userid\n        method: PUT\n        description: Update a user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-users-userid\n        method: DELETE\n        description: Delete a user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: geofences\n      path: /geofences\n      operations:\n      - name: get-geofences\n        method: GET\n        description: List geofences\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-geofences\n     \
  \   method: POST\n        description: Create a geofence\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: geofences-geofenceid\n      path: /geofences/{geofenceId}\n      operations:\n      - name: get-geofences-geofenceid\n        method: GET\n        description: Retrieve a geofence\n        inputParameters:\n        - name: geofenceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-geofences-geofenceid\n        method: PUT\n        description: Update a geofence\n        inputParameters:\n        - name: geofenceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-geofences-geofenceid\n\
  \        method: DELETE\n        description: Delete a geofence\n        inputParameters:\n        - name: geofenceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      operations:\n      - name: get-events\n        method: GET\n        description: List events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-eventid\n      path: /events/{eventId}\n      operations:\n      - name: get-events-eventid\n        method: GET\n        description: Retrieve an event\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: radar-rest\n    description: REST adapter for Radar API.\n    resources:\n    - path: /track\n      name: post-track\n      operations:\n      - method: POST\n        name: post-track\n        description: Track a user location\n        call: radar.post-track\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /geocode/forward\n      name: get-geocode-forward\n      operations:\n      - method: GET\n        name: get-geocode-forward\n        description: Forward geocode an address\n        call: radar.get-geocode-forward\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /geocode/reverse\n      name: get-geocode-reverse\n      operations:\n      - method: GET\n        name: get-geocode-reverse\n        description: Reverse geocode coordinates\n        call: radar.get-geocode-reverse\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /geocode/ip\n      name: get-geocode-ip\n      operations:\n      - method: GET\n        name: get-geocode-ip\n        description: IP geocode\n        call: radar.get-geocode-ip\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search/autocomplete\n      name: get-search-autocomplete\n      operations:\n      - method: GET\n        name: get-search-autocomplete\n        description: Address autocomplete\n        call: radar.get-search-autocomplete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search/users\n      name: get-search-users\n      operations:\n      - method: GET\n        name: get-search-users\n        description: Search users\n        call: radar.get-search-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search/geofences\n      name: get-search-geofences\n      operations:\n      - method: GET\n        name: get-search-geofences\n\
  \        description: Search geofences\n        call: radar.get-search-geofences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search/places\n      name: get-search-places\n      operations:\n      - method: GET\n        name: get-search-places\n        description: Search places\n        call: radar.get-search-places\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /addresses/validate\n      name: get-addresses-validate\n      operations:\n      - method: GET\n        name: get-addresses-validate\n        description: Validate an address\n        call: radar.get-addresses-validate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /route/distance\n      name: get-route-distance\n      operations:\n      - method: GET\n        name: get-route-distance\n        description: Calculate distance between two points\n        call: radar.get-route-distance\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /route/matrix\n      name: get-route-matrix\n      operations:\n      - method: GET\n        name: get-route-matrix\n        description: Distance matrix routing\n        call: radar.get-route-matrix\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /route/match\n      name: get-route-match\n      operations:\n      - method: GET\n        name: get-route-match\n        description: Match a sequence of coordinates to roads\n        call: radar.get-route-match\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /route/directions\n      name: get-route-directions\n      operations:\n      - method: GET\n        name: get-route-directions\n        description: Get directions between points\n        call: radar.get-route-directions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /route/optimize\n      name: get-route-optimize\n\
  \      operations:\n      - method: GET\n        name: get-route-optimize\n        description: Route optimization\n        call: radar.get-route-optimize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: get-users\n      operations:\n      - method: GET\n        name: get-users\n        description: List users\n        call: radar.get-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}\n      name: get-users-userid\n      operations:\n      - method: GET\n        name: get-users-userid\n        description: Retrieve a user\n        call: radar.get-users-userid\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}\n      name: put-users-userid\n      operations:\n      - method: PUT\n        name: put-users-userid\n        description: Update a user\n        call: radar.put-users-userid\n\
  \        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}\n      name: delete-users-userid\n      operations:\n      - method: DELETE\n        name: delete-users-userid\n        description: Delete a user\n        call: radar.delete-users-userid\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /geofences\n      name: get-geofences\n      operations:\n      - method: GET\n        name: get-geofences\n        description: List geofences\n        call: radar.get-geofences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /geofences\n      name: post-geofences\n      operations:\n      - method: POST\n        name: post-geofences\n        description: Create a geofence\n        call: radar.post-geofences\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /geofences/{geofenceId}\n      name: get-geofences-geofenceid\n      operations:\n      - method: GET\n        name: get-geofences-geofenceid\n        description: Retrieve a geofence\n        call: radar.get-geofences-geofenceid\n        with:\n          geofenceId: rest.geofenceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /geofences/{geofenceId}\n      name: put-geofences-geofenceid\n      operations:\n      - method: PUT\n        name: put-geofences-geofenceid\n        description: Update a geofence\n        call: radar.put-geofences-geofenceid\n        with:\n          geofenceId: rest.geofenceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /geofences/{geofenceId}\n      name: delete-geofences-geofenceid\n      operations:\n      - method: DELETE\n        name: delete-geofences-geofenceid\n        description: Delete a geofence\n        call: radar.delete-geofences-geofenceid\n       \
  \ with:\n          geofenceId: rest.geofenceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events\n      name: get-events\n      operations:\n      - method: GET\n        name: get-events\n        description: List events\n        call: radar.get-events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events/{eventId}\n      name: get-events-eventid\n      operations:\n      - method: GET\n        name: get-events-eventid\n        description: Retrieve an event\n        call: radar.get-events-eventid\n        with:\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: radar-mcp\n    transport: http\n    description: MCP adapter for Radar API for AI agent use.\n    tools:\n    - name: post-track\n      description: Track a user location\n      hints:\n        readOnly: false\n        destructive: false\n  \
  \      idempotent: false\n      call: radar.post-track\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-geocode-forward\n      description: Forward geocode an address\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-geocode-forward\n      with:\n        query: tools.query\n      inputParameters:\n      - name: query\n        type: string\n        description: query\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-geocode-reverse\n      description: Reverse geocode coordinates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-geocode-reverse\n      with:\n        coordinates: tools.coordinates\n      inputParameters:\n      - name: coordinates\n        type: string\n        description: coordinates\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-geocode-ip\n      description: IP geocode\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-geocode-ip\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-search-autocomplete\n      description: Address autocomplete\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-search-autocomplete\n      with:\n        query: tools.query\n      inputParameters:\n      - name: query\n        type: string\n        description: query\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-search-users\n      description: Search users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-search-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-search-geofences\n\
  \      description: Search geofences\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-search-geofences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-search-places\n      description: Search places\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-search-places\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-addresses-validate\n      description: Validate an address\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-addresses-validate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-route-distance\n      description: Calculate distance between two points\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-route-distance\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-route-matrix\n      description: Distance matrix routing\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-route-matrix\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-route-match\n      description: Match a sequence of coordinates to roads\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-route-match\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-route-directions\n      description: Get directions between points\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-route-directions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-route-optimize\n      description: Route optimization\n      hints:\n       \
  \ readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-route-optimize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-users\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-users-userid\n      description: Retrieve a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-users-userid\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-users-userid\n      description: Update a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n\
  \      call: radar.put-users-userid\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-users-userid\n      description: Delete a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: radar.delete-users-userid\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-geofences\n      description: List geofences\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-geofences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-geofences\n      description:\
  \ Create a geofence\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: radar.post-geofences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-geofences-geofenceid\n      description: Retrieve a geofence\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-geofences-geofenceid\n      with:\n        geofenceId: tools.geofenceId\n      inputParameters:\n      - name: geofenceId\n        type: string\n        description: geofenceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-geofences-geofenceid\n      description: Update a geofence\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: radar.put-geofences-geofenceid\n      with:\n        geofenceId: tools.geofenceId\n      inputParameters:\n      - name: geofenceId\n      \
  \  type: string\n        description: geofenceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-geofences-geofenceid\n      description: Delete a geofence\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: radar.delete-geofences-geofenceid\n      with:\n        geofenceId: tools.geofenceId\n      inputParameters:\n      - name: geofenceId\n        type: string\n        description: geofenceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-events\n      description: List events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radar.get-events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-events-eventid\n      description: Retrieve an event\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: radar.get-events-eventid\n      with:\n        eventId: tools.eventId\n      inputParameters:\n      - name: eventId\n        type: string\n        description: eventId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    RADAR_TOKEN: RADAR_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/radar/refs/heads/main/capabilities/radar-capability.yaml
tags:
- Radar
- API
tools:
- description: Track a user location
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-track
- description: Forward geocode an address
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-geocode-forward
- description: Reverse geocode coordinates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-geocode-reverse
- description: IP geocode
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-geocode-ip
- description: Address autocomplete
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-search-autocomplete
- description: Search users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-search-users
- description: Search geofences
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-search-geofences
- description: Search places
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-search-places
- description: Validate an address
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-addresses-validate
- description: Calculate distance between two points
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-route-distance
- description: Distance matrix routing
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-route-matrix
- description: Match a sequence of coordinates to roads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-route-match
- description: Get directions between points
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-route-directions
- description: Route optimization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-route-optimize
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-users
- description: Retrieve a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-users-userid
- description: Update a user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-users-userid
- description: Delete a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-users-userid
- description: List geofences
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-geofences
- description: Create a geofence
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-geofences
- description: Retrieve a geofence
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-geofences-geofenceid
- description: Update a geofence
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-geofences-geofenceid
- description: Delete a geofence
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-geofences-geofenceid
- description: List events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-events
- description: Retrieve an event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-events-eventid
---

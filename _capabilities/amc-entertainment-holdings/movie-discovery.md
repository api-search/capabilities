---
categories: []
consumed_apis: []
description: Workflow capability for movie discovery and showtime search using the AMC Theatres API. Allows partner sites and apps to surface now-playing, advance, and coming-soon movies, find theatres by location, and look up showtimes by theatre, date, or proximity to a user's location. Designed for entertainment listings, movie discovery apps, and ticket-aggregator integrations.
layout: capability
name: AMC Movie Discovery
operations:
- description: List now-playing movies.
  method: GET
  name: list-movies-now-playing
  path: /movies
- description: List coming-soon movies.
  method: GET
  name: list-movies-coming-soon
  path: /movies
- description: ''
  method: GET
  name: get-movie
  path: /movies/{idOrSlug}
- description: Search theatres by name/state/city.
  method: GET
  name: search-theatres
  path: /theatres
- description: ''
  method: GET
  name: list-theatre-showtimes
  path: /theatres/{theatre-number}/showtimes
- description: List showtimes within proximity of a coordinate on a date.
  method: GET
  name: list-nearby-showtimes
  path: /showtimes/near/{latitude}/{longitude}/{date}
personas: []
provider_name: AMC Entertainment Holdings
provider_slug: amc-entertainment-holdings
search_terms:
- movies
- get nearby amc showtimes
- loyalty
- search theatres
- get movie
- theatres
- list nearby showtimes
- concessions
- list coming-soon movies.
- movie discovery
- get details for an amc movie by id or slug.
- showtimes
- get showtimes at a specific amc theatre, optionally filtered by movie.
- list theatre showtimes
- locations
- list movies now playing
- list now-playing movies.
- search amc theatres
- get amc theatre showtimes
- list movies coming soon
- entertainment
- list the current amc now-playing movies.
- search
- amc theatres
- search theatres by name/state/city.
- search amc theatres by name, state, or city.
- find amc showtimes near a coordinate on a date.
- get amc movie
- ticketing
- list showtimes within proximity of a coordinate on a date.
- fortune 500
slug: movie-discovery
source_filename: movie-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AMC Movie Discovery\n  description: Workflow capability for movie discovery and showtime search using the AMC Theatres API. Allows partner sites\n    and apps to surface now-playing, advance, and coming-soon movies, find theatres by location, and look up showtimes by\n    theatre, date, or proximity to a user's location. Designed for entertainment listings, movie discovery apps, and ticket-aggregator\n    integrations.\n  tags:\n  - AMC Theatres\n  - Movie Discovery\n  - Showtimes\n  - Locations\n  - Search\n  created: '2026-05-05'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AMC_VENDOR_KEY: AMC_VENDOR_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amc-theatres-api\n    baseUri: https://api.amctheatres.com\n    auth:\n      type: apiKey\n      in: header\n      name: X-AMC-Vendor-Key\n      value: '{{AMC_VENDOR_KEY}}'\n    resources:\n    - name: theatres\n      path: /v2\n      operations:\n      -\
  \ id: list-theatres\n        method: GET\n        path: /theatres\n        description: List all active AMC theatres.\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n        - name: state\n          in: query\n          type: string\n        - name: city\n          in: query\n          type: string\n        - name: market\n          in: query\n          type: string\n        - name: brand\n          in: query\n          type: string\n        - name: page-size\n          in: query\n          type: integer\n        - name: page-number\n          in: query\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-theatre\n        method: GET\n        path: /theatres/{idOrSlug}\n        description: Get a single theatre by id or slug.\n        inputParameters:\n        - name: idOrSlug\n          in: path\n          type: string\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - id: list-theatre-seating-layouts\n        method: GET\n        path: /theatres/{theatre-number}/seating-layouts\n        description: List seating layouts for an auditorium.\n        inputParameters:\n        - name: theatre-number\n          in: path\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: movies\n      path: /v2\n      operations:\n      - id: list-movies\n        method: GET\n        path: /movies\n        description: List all movies.\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n        - name: page-size\n          in: query\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-movies-now-playing\n        method: GET\n        path: /movies/views/now-playing\n        description: List now-playing\
  \ movies.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-movies-coming-soon\n        method: GET\n        path: /movies/views/coming-soon\n        description: List coming-soon movies.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-movies-advance\n        method: GET\n        path: /movies/views/advance\n        description: List advance ticket movies.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-movie\n        method: GET\n        path: /movies/{idOrSlug}\n        description: Get a movie by id or slug.\n        inputParameters:\n        - name: idOrSlug\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: showtimes\n      path: /v2\n      operations:\n      - id: list-theatre-showtimes\n\
  \        method: GET\n        path: /theatres/{theatre-number}/showtimes\n        description: List future showtimes for a theatre.\n        inputParameters:\n        - name: theatre-number\n          in: path\n          type: integer\n        - name: movie-id\n          in: query\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-theatre-showtimes-by-date\n        method: GET\n        path: /theatres/{theatre-number}/showtimes/{date}\n        description: List showtimes for a theatre on a date.\n        inputParameters:\n        - name: theatre-number\n          in: path\n          type: integer\n        - name: date\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-showtime\n        method: GET\n        path: /showtimes/{id}\n        description: Get a showtime by id.\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-showtimes-by-location\n        method: GET\n        path: /showtimes/views/current-location/{date}/{latitude}/{longitude}\n        description: List showtimes near a latitude/longitude on a date.\n        inputParameters:\n        - name: date\n          in: path\n          type: string\n        - name: latitude\n          in: path\n          type: number\n        - name: longitude\n          in: path\n          type: number\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /v2\n      operations:\n      - id: list-location-suggestions\n        method: GET\n        path: /location-suggestions\n        description: Suggest locations by zip / city / state / theatre name.\n        inputParameters:\n        - name: query\n          in:\
  \ query\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: markets\n      path: /v1\n      operations:\n      - id: list-markets\n        method: GET\n        path: /markets\n        description: List all AMC markets.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: states\n      path: /v1\n      operations:\n      - id: list-states\n        method: GET\n        path: /states\n        description: List all states.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /v3\n      operations:\n      - id: create-order\n        method: POST\n        path: /orders\n        description: Create a new order.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-order\n        method: GET\n        path: /orders/{order-id}\n\
  \        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: add-order-product\n        method: POST\n        path: /orders/{order-id}/products\n        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: add-order-payment\n        method: POST\n        path: /orders/{order-id}/payments\n        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: delete-order\n        method: DELETE\n        path: /orders/{order-id}\n        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n      - id: apply-loyalty-rewards\n        method:\
  \ POST\n        path: /orders/{order-id}/loyalty-rewards-application\n        inputParameters:\n        - name: order-id\n          in: path\n          type: string\n    - name: concessions\n      path: /v1\n      operations:\n      - id: list-theatre-concessions\n        method: GET\n        path: /theatres/{theatre-id}/concessions\n        inputParameters:\n        - name: theatre-id\n          in: path\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: list-concession-categories\n        method: GET\n        path: /theatres/{theatre-id}/concessions/categories\n        inputParameters:\n        - name: theatre-id\n          in: path\n          type: integer\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loyalty\n      path: /v4\n      operations:\n      - id: get-loyalty-account\n        method: GET\n        path: /loyalty-accounts/{loyalty-account-id}\n\
  \        inputParameters:\n        - name: loyalty-account-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: get-loyalty-account-by-email\n        method: GET\n        path: /loyalty-accounts/email-{email-address}\n        inputParameters:\n        - name: email-address\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: create-loyalty-redemption\n        method: POST\n        path: /loyalty-accounts/{loyalty-account-id}/redemptions\n        inputParameters:\n        - name: loyalty-account-id\n          in: path\n          type: string\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /v1\n      operations:\n      - id: list-webhook-events\n        method: GET\n        path: /webhook-events\n        description:\
  \ List available webhook events.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: subscribe-webhook\n        method: POST\n        path: /webhooks\n        description: Subscribe to a webhook event.\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - id: unsubscribe-webhook\n        method: DELETE\n        path: /webhooks/{webhook-token-id}\n        inputParameters:\n        - name: webhook-token-id\n          in: path\n          type: string\n  exposes:\n  - type: rest\n    port: 8092\n    namespace: amc-discovery-api\n    description: Unified REST API for AMC movie and theatre discovery.\n    resources:\n    - path: /movies\n      name: movies\n      operations:\n      - method: GET\n        name: list-movies-now-playing\n        description: List now-playing movies.\n        call: amc-theatres-api.list-movies-now-playing\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: GET\n        name: list-movies-coming-soon\n        description: List coming-soon movies.\n        call: amc-theatres-api.list-movies-coming-soon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /movies/{idOrSlug}\n      name: movie\n      operations:\n      - method: GET\n        name: get-movie\n        call: amc-theatres-api.get-movie\n        with:\n          idOrSlug: rest.idOrSlug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /theatres\n      name: theatres\n      operations:\n      - method: GET\n        name: search-theatres\n        description: Search theatres by name/state/city.\n        call: amc-theatres-api.list-theatres\n        with:\n          name: rest.name\n          state: rest.state\n          city: rest.city\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /theatres/{theatre-number}/showtimes\n      name: theatre-showtimes\n\
  \      operations:\n      - method: GET\n        name: list-theatre-showtimes\n        call: amc-theatres-api.list-theatre-showtimes\n        with:\n          theatre-number: rest.theatre-number\n          movie-id: rest.movie-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /showtimes/near/{latitude}/{longitude}/{date}\n      name: nearby-showtimes\n      operations:\n      - method: GET\n        name: list-nearby-showtimes\n        description: List showtimes within proximity of a coordinate on a date.\n        call: amc-theatres-api.list-showtimes-by-location\n        with:\n          date: rest.date\n          latitude: rest.latitude\n          longitude: rest.longitude\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: amc-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted AMC movie and showtime discovery.\n    tools:\n    - name: list-movies-now-playing\n\
  \      description: List the current AMC now-playing movies.\n      call: amc-theatres-api.list-movies-now-playing\n    - name: search-amc-theatres\n      description: Search AMC theatres by name, state, or city.\n      call: amc-theatres-api.list-theatres\n    - name: get-amc-theatre-showtimes\n      description: Get showtimes at a specific AMC theatre, optionally filtered by movie.\n      call: amc-theatres-api.list-theatre-showtimes\n    - name: get-nearby-amc-showtimes\n      description: Find AMC showtimes near a coordinate on a date.\n      call: amc-theatres-api.list-showtimes-by-location\n    - name: get-amc-movie\n      description: Get details for an AMC movie by id or slug.\n      call: amc-theatres-api.get-movie\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amc-entertainment-holdings/refs/heads/main/capabilities/movie-discovery.yaml
tags:
- AMC Theatres
- Movie Discovery
- Showtimes
- Locations
- Search
tools:
- description: List the current AMC now-playing movies.
  hints: {}
  name: list-movies-now-playing
- description: Search AMC theatres by name, state, or city.
  hints: {}
  name: search-amc-theatres
- description: Get showtimes at a specific AMC theatre, optionally filtered by movie.
  hints: {}
  name: get-amc-theatre-showtimes
- description: Find AMC showtimes near a coordinate on a date.
  hints: {}
  name: get-nearby-amc-showtimes
- description: Get details for an AMC movie by id or slug.
  hints: {}
  name: get-amc-movie
---

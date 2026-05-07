---
categories: []
consumed_apis: []
description: Workflow capability for discovering movies, finding nearby Regal theatres, checking showtimes, and purchasing tickets with Regal Crown Club loyalty integration. Designed for mobile apps, concierge services, and entertainment recommendation platforms.
layout: capability
name: Regal Cinema Ticketing
operations:
- description: List currently playing and upcoming movies
  method: GET
  name: list-movies
  path: /v1/movies
- description: Get details for a specific movie
  method: GET
  name: get-movie
  path: /v1/movies/{movieId}
- description: List theatres with optional proximity search
  method: GET
  name: list-theatres
  path: /v1/theatres
- description: Get details for a specific theatre
  method: GET
  name: get-theatre
  path: /v1/theatres/{theatreId}
- description: List showtimes by movie, theatre, or date
  method: GET
  name: list-showtimes
  path: /v1/showtimes
- description: Purchase tickets for a showtime
  method: POST
  name: purchase-tickets
  path: /v1/tickets
- description: Get details for a ticket order
  method: GET
  name: get-ticket-order
  path: /v1/tickets/{orderId}
- description: Get loyalty member details and credit balance
  method: GET
  name: get-loyalty-member
  path: /v1/loyalty/members/{memberId}
- description: Add loyalty credits to a member account
  method: POST
  name: add-loyalty-credits
  path: /v1/loyalty/members/{memberId}/credits
personas: []
provider_name: regal-entertainment-group
provider_slug: regal-entertainment-group
search_terms:
- movies
- get details for a specific theatre
- get theatre
- theatre details
- list theatres
- get regal crown club member status, tier, and credit balance
- locate nearby regal theatres
- loyalty
- list movies
- add loyalty credits to a member account
- get movie
- list currently playing and upcoming movies
- ticket order details
- add loyalty credits
- cinema
- browse movies now playing and coming soon
- movie details
- look up showtimes for a movie at a theatre on a given date
- get details for a specific regal theatre including amenities and screen count
- showtime schedules
- showtimes
- award regal crown club credits to a member after a qualifying purchase
- retrieve a ticket order with barcodes and confirmation code
- get details for a ticket order
- get loyalty member
- browse movies currently playing and upcoming at regal cinemas
- theatre
- get ticket order
- entertainment
- loyalty member profile
- list showtimes by movie, theatre, or date
- find regal theatre locations near a geographic coordinate or by state
- get full details for a specific movie including cast, runtime, and rating
- list theatres with optional proximity search
- loyalty credit management
- get loyalty member details and credit balance
- find nearby theatres
- fortune 500
- ticket purchasing
- list showtimes
- ticketing
- purchase tickets
- purchase tickets for a showtime and optionally earn regal crown club credits
- purchase tickets for a showtime
- get details for a specific movie
slug: cinema-ticketing
source_filename: cinema-ticketing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Regal Cinema Ticketing\n  description: Workflow capability for discovering movies, finding nearby Regal theatres, checking showtimes, and purchasing\n    tickets with Regal Crown Club loyalty integration. Designed for mobile apps, concierge services, and entertainment recommendation\n    platforms.\n  tags:\n  - Cinema\n  - Movies\n  - Ticketing\n  - Showtimes\n  - Loyalty\n  - Entertainment\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REGAL_API_KEY: REGAL_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: regal-cinema\n    baseUri: https://api.regmovies.com/v1\n    description: Regal Cinema API for movies, theatres, showtimes, ticketing, and loyalty\n    authentication:\n      type: apikey\n      key: Ocp-Apim-Subscription-Key\n      value: '{{REGAL_API_KEY}}'\n      placement: header\n    resources:\n    - name: movies\n      path: /movies\n      description: Movie catalog\
  \ and metadata\n      operations:\n      - name: list-movies\n        method: GET\n        description: List currently playing and upcoming movies\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by movie status (now_playing, upcoming, all)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of movies to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-movie\n        method: GET\n        description: Retrieve details for a specific movie\n        inputParameters:\n        - name: movieId\n          in: path\n          type: string\n          required: true\n     \
  \     description: Unique movie identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: theatres\n      path: /theatres\n      description: Theatre locations and details\n      operations:\n      - name: list-theatres\n        method: GET\n        description: List Regal theatre locations\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by US state code\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude for proximity search\n        - name: lng\n          in: query\n          type: number\n          required: false\n          description: Longitude for proximity search\n        - name: radius\n          in: query\n          type: integer\n          required: false\n          description: Search radius in miles\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-theatre\n        method: GET\n        description: Retrieve details for a specific theatre\n        inputParameters:\n        - name: theatreId\n          in: path\n          type: string\n          required: true\n          description: Unique theatre identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: showtimes\n      path: /showtimes\n      description: Showtime schedules and availability\n      operations:\n      - name: list-showtimes\n        method: GET\n        description: List showtimes filtered by movie, theatre, or date\n        inputParameters:\n        - name: movieId\n          in: query\n          type: string\n          required: false\n          description: Filter by movie ID\n        - name: theatreId\n          in: query\n      \
  \    type: string\n          required: false\n          description: Filter by theatre ID\n        - name: date\n          in: query\n          type: string\n          required: false\n          description: Date in YYYY-MM-DD format\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Filter by screening format (IMAX, 4DX, RPX, 2D, 3D)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets\n      path: /tickets\n      description: Ticket purchasing and order management\n      operations:\n      - name: purchase-tickets\n        method: POST\n        description: Purchase tickets for a specific showtime\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            showtimeId:\
  \ '{{tools.showtimeId}}'\n            tickets: '{{tools.tickets}}'\n            loyaltyMemberId: '{{tools.loyaltyMemberId}}'\n            paymentToken: '{{tools.paymentToken}}'\n      - name: get-ticket-order\n        method: GET\n        description: Retrieve details for a specific ticket order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order ID to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loyalty\n      path: /loyalty\n      description: Regal Crown Club loyalty rewards\n      operations:\n      - name: get-loyalty-member\n        method: GET\n        description: Retrieve loyalty member details and credit balance\n        inputParameters:\n        - name: memberId\n          in: path\n          type: string\n          required: true\n          description: Regal Crown Club member\
  \ ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-loyalty-credits\n        method: POST\n        description: Add loyalty credits to a member account\n        inputParameters:\n        - name: memberId\n          in: path\n          type: string\n          required: true\n          description: Regal Crown Club member ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            credits: '{{tools.credits}}'\n            reason: '{{tools.reason}}'\n            orderId: '{{tools.orderId}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: regal-ticketing-api\n    description: Unified REST API for Regal cinema discovery, showtimes, and ticketing.\n    resources:\n    - path: /v1/movies\n      name: movies\n      description: Browse movies now playing\
  \ and coming soon\n      operations:\n      - method: GET\n        name: list-movies\n        description: List currently playing and upcoming movies\n        call: regal-cinema.list-movies\n        with:\n          status: rest.status\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/movies/{movieId}\n      name: movie-detail\n      description: Movie details\n      operations:\n      - method: GET\n        name: get-movie\n        description: Get details for a specific movie\n        call: regal-cinema.get-movie\n        with:\n          movieId: rest.movieId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/theatres\n      name: theatres\n      description: Locate nearby Regal theatres\n      operations:\n      - method: GET\n        name: list-theatres\n        description: List theatres with optional proximity search\n        call: regal-cinema.list-theatres\n\
  \        with:\n          state: rest.state\n          lat: rest.lat\n          lng: rest.lng\n          radius: rest.radius\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/theatres/{theatreId}\n      name: theatre-detail\n      description: Theatre details\n      operations:\n      - method: GET\n        name: get-theatre\n        description: Get details for a specific theatre\n        call: regal-cinema.get-theatre\n        with:\n          theatreId: rest.theatreId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/showtimes\n      name: showtimes\n      description: Showtime schedules\n      operations:\n      - method: GET\n        name: list-showtimes\n        description: List showtimes by movie, theatre, or date\n        call: regal-cinema.list-showtimes\n        with:\n          movieId: rest.movieId\n          theatreId: rest.theatreId\n          date: rest.date\n          format: rest.format\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tickets\n      name: tickets\n      description: Ticket purchasing\n      operations:\n      - method: POST\n        name: purchase-tickets\n        description: Purchase tickets for a showtime\n        call: regal-cinema.purchase-tickets\n        with:\n          showtimeId: rest.showtimeId\n          tickets: rest.tickets\n          loyaltyMemberId: rest.loyaltyMemberId\n          paymentToken: rest.paymentToken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tickets/{orderId}\n      name: ticket-order\n      description: Ticket order details\n      operations:\n      - method: GET\n        name: get-ticket-order\n        description: Get details for a ticket order\n        call: regal-cinema.get-ticket-order\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loyalty/members/{memberId}\n\
  \      name: loyalty-member\n      description: Loyalty member profile\n      operations:\n      - method: GET\n        name: get-loyalty-member\n        description: Get loyalty member details and credit balance\n        call: regal-cinema.get-loyalty-member\n        with:\n          memberId: rest.memberId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loyalty/members/{memberId}/credits\n      name: loyalty-credits\n      description: Loyalty credit management\n      operations:\n      - method: POST\n        name: add-loyalty-credits\n        description: Add loyalty credits to a member account\n        call: regal-cinema.add-loyalty-credits\n        with:\n          memberId: rest.memberId\n          credits: rest.credits\n          reason: rest.reason\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: regal-ticketing-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted cinema discovery, showtime lookup, and ticket purchasing.\n    tools:\n    - name: list-movies\n      description: Browse movies currently playing and upcoming at Regal cinemas\n      hints:\n        readOnly: true\n        openWorld: true\n      call: regal-cinema.list-movies\n      with:\n        status: tools.status\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-movie\n      description: Get full details for a specific movie including cast, runtime, and rating\n      hints:\n        readOnly: true\n      call: regal-cinema.get-movie\n      with:\n        movieId: tools.movieId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-nearby-theatres\n      description: Find Regal theatre locations near a geographic coordinate or by state\n      hints:\n        readOnly: true\n        openWorld: true\n      call: regal-cinema.list-theatres\n\
  \      with:\n        lat: tools.lat\n        lng: tools.lng\n        radius: tools.radius\n        state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-theatre\n      description: Get details for a specific Regal theatre including amenities and screen count\n      hints:\n        readOnly: true\n      call: regal-cinema.get-theatre\n      with:\n        theatreId: tools.theatreId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-showtimes\n      description: Look up showtimes for a movie at a theatre on a given date\n      hints:\n        readOnly: true\n      call: regal-cinema.list-showtimes\n      with:\n        movieId: tools.movieId\n        theatreId: tools.theatreId\n        date: tools.date\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: purchase-tickets\n      description: Purchase tickets for a showtime and optionally earn Regal\
  \ Crown Club credits\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: regal-cinema.purchase-tickets\n      with:\n        showtimeId: tools.showtimeId\n        tickets: tools.tickets\n        loyaltyMemberId: tools.loyaltyMemberId\n        paymentToken: tools.paymentToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ticket-order\n      description: Retrieve a ticket order with barcodes and confirmation code\n      hints:\n        readOnly: true\n      call: regal-cinema.get-ticket-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-loyalty-member\n      description: Get Regal Crown Club member status, tier, and credit balance\n      hints:\n        readOnly: true\n      call: regal-cinema.get-loyalty-member\n      with:\n        memberId: tools.memberId\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n    - name: add-loyalty-credits\n      description: Award Regal Crown Club credits to a member after a qualifying purchase\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: regal-cinema.add-loyalty-credits\n      with:\n        memberId: tools.memberId\n        credits: tools.credits\n        reason: tools.reason\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/regal-entertainment-group/refs/heads/main/capabilities/cinema-ticketing.yaml
tags:
- Cinema
- Movies
- Ticketing
- Showtimes
- Loyalty
- Entertainment
tools:
- description: Browse movies currently playing and upcoming at Regal cinemas
  hints:
    openWorld: true
    readOnly: true
  name: list-movies
- description: Get full details for a specific movie including cast, runtime, and rating
  hints:
    readOnly: true
  name: get-movie
- description: Find Regal theatre locations near a geographic coordinate or by state
  hints:
    openWorld: true
    readOnly: true
  name: find-nearby-theatres
- description: Get details for a specific Regal theatre including amenities and screen count
  hints:
    readOnly: true
  name: get-theatre
- description: Look up showtimes for a movie at a theatre on a given date
  hints:
    readOnly: true
  name: list-showtimes
- description: Purchase tickets for a showtime and optionally earn Regal Crown Club credits
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: purchase-tickets
- description: Retrieve a ticket order with barcodes and confirmation code
  hints:
    readOnly: true
  name: get-ticket-order
- description: Get Regal Crown Club member status, tier, and credit balance
  hints:
    readOnly: true
  name: get-loyalty-member
- description: Award Regal Crown Club credits to a member after a qualifying purchase
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-loyalty-credits
---

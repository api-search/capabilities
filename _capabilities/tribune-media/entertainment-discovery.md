---
categories: []
consumed_apis: []
description: Unified entertainment discovery workflow combining TV programming guides, movie showtimes, celebrity appearances, and sports event schedules. Powers content recommendation apps, EPG integrations, and entertainment platform features.
layout: capability
name: TMS Entertainment Discovery
operations:
- description: Get TV lineups available for a postal code
  method: GET
  name: get-lineups
  path: /v1/lineups
- description: Get the TV programming grid for a lineup
  method: GET
  name: get-tv-grid
  path: /v1/lineups/{lineupId}/grid
- description: Search for TV programs, movies, and shows
  method: GET
  name: search-programs
  path: /v1/programs
- description: Get detailed metadata for a program
  method: GET
  name: get-program
  path: /v1/programs/{tmsId}
- description: Get new episodes and premieres airing on a lineup
  method: GET
  name: get-new-show-airings
  path: /v1/programs/new-airings
- description: Get movies in local theatres with showtimes
  method: GET
  name: get-movie-showings
  path: /v1/movies/showings
- description: Get movies airing on a TV lineup
  method: GET
  name: get-movie-airings
  path: /v1/movies/tv-airings
- description: Get live sports events for a sport on a lineup
  method: GET
  name: get-sport-event-airings
  path: /v1/sports/{sportsId}/events
- description: Get all airings for a sports organization
  method: GET
  name: get-organization-airings
  path: /v1/sports/organizations/{organizationId}/airings
- description: Get celebrity details and biography
  method: GET
  name: get-celebrity
  path: /v1/celebrities/{personId}
- description: Get TV shows featuring a celebrity
  method: GET
  name: get-celebrity-airings
  path: /v1/celebrities/{personId}/airings
- description: Get celebrities appearing on talk shows
  method: GET
  name: get-talk-show-airings
  path: /v1/celebrities/talk-shows
personas: []
provider_name: Tribune Media
provider_slug: tribune-media
search_terms:
- tv program search and discovery
- get live sports
- get new episodes and premieres airing on a lineup
- tv programming grid schedule
- sports
- get movie showings
- find movies airing on tv channels for a lineup
- celebrity information
- search programs
- sports organization airings (mlb, nba, nfl, etc.)
- movies
- search for tv programs, movies, and shows
- detailed program metadata
- get celebrities appearing on talk shows
- get the full tv programming grid showing what is on across all channels
- get talk show airings
- get all tv airings for a sports league or organization (mlb, nfl, nba, etc.)
- get tv lineups
- content discovery
- get celebrity
- celebrity
- get sports league airings
- find which celebrities are appearing on talk shows today
- get organization airings
- get tv shows featuring a celebrity
- get new show airings
- movies currently showing in theatres
- tv lineup and channel information
- programming guide
- get detailed metadata for a tv program or movie by tms id
- find new episodes and series premieres airing on a tv lineup
- tribune media
- get tv lineups available for a postal code
- find upcoming tv appearances for a celebrity
- get biography and details for a celebrity by their tms person id
- get live sports events airing on tv for a specific sport
- television
- celebrity talk show appearances
- get movies on tv
- get movies in local theatres with showtimes
- get program details
- get the full list of tv program genre categories
- get all airings for a sports organization
- live sports events on tv
- get sport event airings
- media
- get lineups
- movies airing on tv
- entertainment
- celebrity tv appearances
- get tv grid
- get detailed metadata for a program
- get live sports events for a sport on a lineup
- search for tv shows, movies, specials, or sports programs by keyword
- get movie airings
- get celebrity details and biography
- new show airings on a lineup
- get celebrity airings
- find tv lineups (cable, satellite, ota) available for a postal code
- get celebrity info
- get program genres
- broadcasting
- get talk show guests
- find movies currently playing at nearby theatres with showtimes
- get celebrity tv appearances
- get movies airing on a tv lineup
- get movie theatre showings
- get program
- get the tv programming grid for a lineup
slug: entertainment-discovery
source_filename: entertainment-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TMS Entertainment Discovery\n  description: Unified entertainment discovery workflow combining TV programming guides, movie showtimes, celebrity appearances,\n    and sports event schedules. Powers content recommendation apps, EPG integrations, and entertainment platform features.\n  tags:\n  - Tribune Media\n  - Entertainment\n  - Television\n  - Movies\n  - Sports\n  - Celebrity\n  - Programming Guide\n  - Content Discovery\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TMS_API_KEY: TMS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: tms-onconnect\n    baseUri: https://data.tmsapi.com\n    description: TMS OnConnect entertainment metadata API\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{TMS_API_KEY}}'\n      placement: query\n    resources:\n    - name: lineups\n      path: /v1.1/lineups\n      description: TV lineup management and channel\
  \ listings\n      operations:\n      - name: get-lineups\n        method: GET\n        description: Get lineups by postal code\n        inputParameters:\n        - name: postalCode\n          in: query\n          type: string\n          required: true\n          description: ZIP or postal code for lineup lookup\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: Two-letter country code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-lineup-channels\n        method: GET\n        description: Get channels for a specific lineup\n        inputParameters:\n        - name: lineupId\n          in: path\n          type: string\n          required: true\n          description: Lineup identifier\n        - name: imageSize\n          in: query\n          type: string\n          required: false\n          description: Image size\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-lineup-grid\n        method: GET\n        description: Get TV grid schedule for lineup\n        inputParameters:\n        - name: lineupId\n          in: path\n          type: string\n          required: true\n          description: Lineup identifier\n        - name: startDateTime\n          in: query\n          type: string\n          required: true\n          description: Grid start time (ISO 8601)\n        - name: endDateTime\n          in: query\n          type: string\n          required: false\n          description: Grid end time (ISO 8601)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: programs\n      path: /v1.1/programs\n      description: TV program search and metadata\n      operations:\n      - name: search-programs\n        method: GET\n \
  \       description: Search programs by free-form query\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: entityType\n          in: query\n          type: string\n          required: false\n          description: Filter by entity type (movie, show, special, sports)\n        - name: genres\n          in: query\n          type: string\n          required: false\n          description: Filter by genres\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-program\n        method: GET\n        description: Get detailed\
  \ metadata for a program\n        inputParameters:\n        - name: tmsId\n          in: path\n          type: string\n          required: true\n          description: TMS program identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-program-airings\n        method: GET\n        description: Get all airings for a program\n        inputParameters:\n        - name: tmsId\n          in: path\n          type: string\n          required: true\n          description: TMS program identifier\n        - name: lineupId\n          in: query\n          type: string\n          required: false\n          description: Lineup to search\n        - name: startDateTime\n          in: query\n          type: string\n          required: false\n          description: Start time for airings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: get-new-show-airings\n        method: GET\n        description: Get new show airings on a lineup\n        inputParameters:\n        - name: lineupId\n          in: query\n          type: string\n          required: true\n          description: Lineup identifier\n        - name: startDateTime\n          in: query\n          type: string\n          required: true\n          description: Start time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-program-genres\n        method: GET\n        description: Get list of program genres\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: movies\n      path: /v1.1/movies\n      description: Movie showtime and airing information\n      operations:\n      - name: get-movie-showings\n        method: GET\n        description: Get movies in local theatres\
  \ with showtimes\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Start date for showings\n        - name: zip\n          in: query\n          type: string\n          required: false\n          description: ZIP code for location\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude coordinate\n        - name: lng\n          in: query\n          type: number\n          required: false\n          description: Longitude coordinate\n        - name: radius\n          in: query\n          type: integer\n          required: false\n          description: Search radius\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-movie-airings\n        method: GET\n        description: Get movies airing on TV lineup\n        inputParameters:\n\
  \        - name: lineupId\n          in: query\n          type: string\n          required: true\n          description: Lineup identifier\n        - name: startDateTime\n          in: query\n          type: string\n          required: true\n          description: Start time for airing window\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-movie-showtimes\n        method: GET\n        description: Get showtimes for a specific movie\n        inputParameters:\n        - name: movieId\n          in: path\n          type: string\n          required: true\n          description: Movie identifier\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Start date\n        - name: zip\n          in: query\n          type: string\n          required: false\n          description: ZIP code\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: sports\n      path: /v1.1/sports\n      description: Sports event and team information\n      operations:\n      - name: get-sport\n        method: GET\n        description: Get sport details with organizations\n        inputParameters:\n        - name: sportsId\n          in: path\n          type: string\n          required: true\n          description: Sport identifier\n        - name: includeOrg\n          in: query\n          type: boolean\n          required: false\n          description: Include organization details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-sport-event-airings\n        method: GET\n        description: Get live sports events on a lineup\n        inputParameters:\n        - name: sportsId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Sport identifier\n        - name: lineupId\n          in: query\n          type: string\n          required: true\n          description: Lineup to search\n        - name: startDateTime\n          in: query\n          type: string\n          required: true\n          description: Start time\n        - name: liveOnly\n          in: query\n          type: boolean\n          required: false\n          description: Filter to live events only\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-organization-airings\n        method: GET\n        description: Get airings for a sports organization\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: lineupId\n          in: query\n          type: string\n          required: false\n          description: Lineup identifier\n\
  \        - name: startDateTime\n          in: query\n          type: string\n          required: false\n          description: Start time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-team-airings\n        method: GET\n        description: Get airings for a specific sports team\n        inputParameters:\n        - name: teamBrandId\n          in: path\n          type: string\n          required: true\n          description: Team brand identifier\n        - name: lineupId\n          in: query\n          type: string\n          required: false\n          description: Lineup identifier\n        - name: startDateTime\n          in: query\n          type: string\n          required: false\n          description: Start time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: celebrities\n      path: /v1.1/celebs\n\
  \      description: Celebrity information and TV appearance scheduling\n      operations:\n      - name: get-celebrity\n        method: GET\n        description: Get celebrity details\n        inputParameters:\n        - name: personId\n          in: path\n          type: string\n          required: true\n          description: Person identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-celebrity-airings\n        method: GET\n        description: Get TV airings featuring a celebrity\n        inputParameters:\n        - name: personId\n          in: path\n          type: string\n          required: true\n          description: Person identifier\n        - name: lineupId\n          in: query\n          type: string\n          required: false\n          description: Lineup to search\n        - name: startDateTime\n          in: query\n          type: string\n          required: false\n\
  \          description: Start time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-talk-show-airings\n        method: GET\n        description: Get celebrity talk show appearances\n        inputParameters:\n        - name: lineupId\n          in: query\n          type: string\n          required: true\n          description: Lineup identifier\n        - name: startDateTime\n          in: query\n          type: string\n          required: true\n          description: Start time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: entertainment-discovery-api\n    description: Unified REST API for entertainment content discovery.\n    resources:\n    - path: /v1/lineups\n      name: lineups\n      description: TV lineup and channel information\n      operations:\n\
  \      - method: GET\n        name: get-lineups\n        description: Get TV lineups available for a postal code\n        call: tms-onconnect.get-lineups\n        with:\n          postalCode: rest.postalCode\n          country: rest.country\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lineups/{lineupId}/grid\n      name: tv-grid\n      description: TV programming grid schedule\n      operations:\n      - method: GET\n        name: get-tv-grid\n        description: Get the TV programming grid for a lineup\n        call: tms-onconnect.get-lineup-grid\n        with:\n          lineupId: rest.lineupId\n          startDateTime: rest.startDateTime\n          endDateTime: rest.endDateTime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/programs\n      name: programs\n      description: TV program search and discovery\n      operations:\n      - method: GET\n        name: search-programs\n        description:\
  \ Search for TV programs, movies, and shows\n        call: tms-onconnect.search-programs\n        with:\n          q: rest.q\n          entityType: rest.entityType\n          genres: rest.genres\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/programs/{tmsId}\n      name: program-detail\n      description: Detailed program metadata\n      operations:\n      - method: GET\n        name: get-program\n        description: Get detailed metadata for a program\n        call: tms-onconnect.get-program\n        with:\n          tmsId: rest.tmsId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/programs/new-airings\n      name: new-airings\n      description: New show airings on a lineup\n      operations:\n      - method: GET\n        name: get-new-show-airings\n        description: Get new episodes and premieres airing on a lineup\n        call: tms-onconnect.get-new-show-airings\n\
  \        with:\n          lineupId: rest.lineupId\n          startDateTime: rest.startDateTime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/movies/showings\n      name: movie-showings\n      description: Movies currently showing in theatres\n      operations:\n      - method: GET\n        name: get-movie-showings\n        description: Get movies in local theatres with showtimes\n        call: tms-onconnect.get-movie-showings\n        with:\n          startDate: rest.startDate\n          zip: rest.zip\n          lat: rest.lat\n          lng: rest.lng\n          radius: rest.radius\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/movies/tv-airings\n      name: movie-tv-airings\n      description: Movies airing on TV\n      operations:\n      - method: GET\n        name: get-movie-airings\n        description: Get movies airing on a TV lineup\n        call: tms-onconnect.get-movie-airings\n        with:\n\
  \          lineupId: rest.lineupId\n          startDateTime: rest.startDateTime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sports/{sportsId}/events\n      name: sports-events\n      description: Live sports events on TV\n      operations:\n      - method: GET\n        name: get-sport-event-airings\n        description: Get live sports events for a sport on a lineup\n        call: tms-onconnect.get-sport-event-airings\n        with:\n          sportsId: rest.sportsId\n          lineupId: rest.lineupId\n          startDateTime: rest.startDateTime\n          liveOnly: rest.liveOnly\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sports/organizations/{organizationId}/airings\n      name: organization-airings\n      description: Sports organization airings (MLB, NBA, NFL, etc.)\n      operations:\n      - method: GET\n        name: get-organization-airings\n        description: Get all airings for a sports\
  \ organization\n        call: tms-onconnect.get-organization-airings\n        with:\n          organizationId: rest.organizationId\n          lineupId: rest.lineupId\n          startDateTime: rest.startDateTime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/celebrities/{personId}\n      name: celebrity-detail\n      description: Celebrity information\n      operations:\n      - method: GET\n        name: get-celebrity\n        description: Get celebrity details and biography\n        call: tms-onconnect.get-celebrity\n        with:\n          personId: rest.personId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/celebrities/{personId}/airings\n      name: celebrity-airings\n      description: Celebrity TV appearances\n      operations:\n      - method: GET\n        name: get-celebrity-airings\n        description: Get TV shows featuring a celebrity\n        call: tms-onconnect.get-celebrity-airings\n\
  \        with:\n          personId: rest.personId\n          lineupId: rest.lineupId\n          startDateTime: rest.startDateTime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/celebrities/talk-shows\n      name: talk-show-appearances\n      description: Celebrity talk show appearances\n      operations:\n      - method: GET\n        name: get-talk-show-airings\n        description: Get celebrities appearing on talk shows\n        call: tms-onconnect.get-talk-show-airings\n        with:\n          lineupId: rest.lineupId\n          startDateTime: rest.startDateTime\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: entertainment-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted entertainment content discovery and recommendations.\n    tools:\n    - name: get-tv-lineups\n      description: Find TV lineups (cable, satellite, OTA) available for a\
  \ postal code\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tms-onconnect.get-lineups\n      with:\n        postalCode: tools.postalCode\n        country: tools.country\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tv-grid\n      description: Get the full TV programming grid showing what is on across all channels\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tms-onconnect.get-lineup-grid\n      with:\n        lineupId: tools.lineupId\n        startDateTime: tools.startDateTime\n        endDateTime: tools.endDateTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-programs\n      description: Search for TV shows, movies, specials, or sports programs by keyword\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tms-onconnect.search-programs\n      with:\n        q: tools.q\n        entityType: tools.entityType\n        genres:\
  \ tools.genres\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-program-details\n      description: Get detailed metadata for a TV program or movie by TMS ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tms-onconnect.get-program\n      with:\n        tmsId: tools.tmsId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-new-show-airings\n      description: Find new episodes and series premieres airing on a TV lineup\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tms-onconnect.get-new-show-airings\n      with:\n        lineupId: tools.lineupId\n        startDateTime: tools.startDateTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-movie-theatre-showings\n      description: Find movies currently playing at nearby theatres with showtimes\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: tms-onconnect.get-movie-showings\n      with:\n        startDate: tools.startDate\n        zip: tools.zip\n        lat: tools.lat\n        lng: tools.lng\n        radius: tools.radius\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-movies-on-tv\n      description: Find movies airing on TV channels for a lineup\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tms-onconnect.get-movie-airings\n      with:\n        lineupId: tools.lineupId\n        startDateTime: tools.startDateTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-live-sports\n      description: Get live sports events airing on TV for a specific sport\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tms-onconnect.get-sport-event-airings\n      with:\n        sportsId: tools.sportsId\n        lineupId: tools.lineupId\n        startDateTime: tools.startDateTime\n        liveOnly:\
  \ tools.liveOnly\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sports-league-airings\n      description: Get all TV airings for a sports league or organization (MLB, NFL, NBA, etc.)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tms-onconnect.get-organization-airings\n      with:\n        organizationId: tools.organizationId\n        lineupId: tools.lineupId\n        startDateTime: tools.startDateTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-celebrity-info\n      description: Get biography and details for a celebrity by their TMS person ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tms-onconnect.get-celebrity\n      with:\n        personId: tools.personId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-celebrity-tv-appearances\n      description: Find upcoming TV appearances for a celebrity\n      hints:\n\
  \        readOnly: true\n        openWorld: false\n      call: tms-onconnect.get-celebrity-airings\n      with:\n        personId: tools.personId\n        lineupId: tools.lineupId\n        startDateTime: tools.startDateTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-talk-show-guests\n      description: Find which celebrities are appearing on talk shows today\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tms-onconnect.get-talk-show-airings\n      with:\n        lineupId: tools.lineupId\n        startDateTime: tools.startDateTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-program-genres\n      description: Get the full list of TV program genre categories\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tms-onconnect.get-program-genres\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tribune-media/refs/heads/main/capabilities/entertainment-discovery.yaml
tags:
- Tribune Media
- Entertainment
- Television
- Movies
- Sports
- Celebrity
- Programming Guide
- Content Discovery
tools:
- description: Find TV lineups (cable, satellite, OTA) available for a postal code
  hints:
    openWorld: false
    readOnly: true
  name: get-tv-lineups
- description: Get the full TV programming grid showing what is on across all channels
  hints:
    openWorld: false
    readOnly: true
  name: get-tv-grid
- description: Search for TV shows, movies, specials, or sports programs by keyword
  hints:
    openWorld: true
    readOnly: true
  name: search-programs
- description: Get detailed metadata for a TV program or movie by TMS ID
  hints:
    openWorld: false
    readOnly: true
  name: get-program-details
- description: Find new episodes and series premieres airing on a TV lineup
  hints:
    openWorld: false
    readOnly: true
  name: get-new-show-airings
- description: Find movies currently playing at nearby theatres with showtimes
  hints:
    openWorld: false
    readOnly: true
  name: get-movie-theatre-showings
- description: Find movies airing on TV channels for a lineup
  hints:
    openWorld: false
    readOnly: true
  name: get-movies-on-tv
- description: Get live sports events airing on TV for a specific sport
  hints:
    openWorld: false
    readOnly: true
  name: get-live-sports
- description: Get all TV airings for a sports league or organization (MLB, NFL, NBA, etc.)
  hints:
    openWorld: false
    readOnly: true
  name: get-sports-league-airings
- description: Get biography and details for a celebrity by their TMS person ID
  hints:
    openWorld: false
    readOnly: true
  name: get-celebrity-info
- description: Find upcoming TV appearances for a celebrity
  hints:
    openWorld: false
    readOnly: true
  name: get-celebrity-tv-appearances
- description: Find which celebrities are appearing on talk shows today
  hints:
    openWorld: false
    readOnly: true
  name: get-talk-show-guests
- description: Get the full list of TV program genre categories
  hints:
    openWorld: false
    readOnly: true
  name: get-program-genres
---

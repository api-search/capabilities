---
categories: []
consumed_apis: []
description: The IGDB (Internet Game Database) API provides programmatic access to a comprehensive video game database, including games, platforms, companies, genres, release dates, covers, screenshots, and user reviews. Authentication uses Twitch OAuth Client Credentials. All requests require a Client-ID header and an Authorization Bearer token. Most endpoints accept POST requests with an Apicalypse query body for filtering, sorting, and field selection.
layout: capability
name: IGDB API
operations:
- description: Query games
  method: POST
  name: post-games
  path: /games
- description: Query platforms
  method: POST
  name: post-platforms
  path: /platforms
- description: Query companies
  method: POST
  name: post-companies
  path: /companies
- description: Query involved companies
  method: POST
  name: post-involved-companies
  path: /involved_companies
- description: Query genres
  method: POST
  name: post-genres
  path: /genres
- description: Query themes
  method: POST
  name: post-themes
  path: /themes
- description: Query game modes
  method: POST
  name: post-game-modes
  path: /game_modes
- description: Query game covers
  method: POST
  name: post-covers
  path: /covers
- description: Query screenshots
  method: POST
  name: post-screenshots
  path: /screenshots
- description: Query artworks
  method: POST
  name: post-artworks
  path: /artworks
- description: Query release dates
  method: POST
  name: post-release-dates
  path: /release_dates
- description: Query collections
  method: POST
  name: post-collections
  path: /collections
- description: Query franchises
  method: POST
  name: post-franchises
  path: /franchises
- description: Query keywords
  method: POST
  name: post-keywords
  path: /keywords
- description: Query age ratings
  method: POST
  name: post-age-ratings
  path: /age_ratings
- description: Query game websites
  method: POST
  name: post-websites
  path: /websites
- description: Search across IGDB entities
  method: POST
  name: post-search
  path: /search
personas: []
provider_name: IGDB
provider_slug: igdb
search_terms:
- post age ratings
- query franchises
- post genres
- query keywords
- query platforms
- search across igdb entities
- query companies
- query genres
- query game covers
- post screenshots
- post involved companies
- post games
- query age ratings
- query themes
- post companies
- post search
- post collections
- post game modes
- post release dates
- gaming
- query artworks
- query game modes
- post websites
- query involved companies
- api
- query screenshots
- post covers
- post franchises
- post artworks
- query game websites
- entertainment
- game database
- igdb
- post keywords
- query games
- post themes
- video games
- query release dates
- post platforms
- query collections
slug: igdb-capability
source_filename: igdb-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: IGDB API\n  description: The IGDB (Internet Game Database) API provides programmatic access to a comprehensive video game database,\n    including games, platforms, companies, genres, release dates, covers, screenshots, and user reviews. Authentication uses\n    Twitch OAuth Client Credentials. All requests require a Client-ID header and an Authorization Bearer token. Most endpoints\n    accept POST requests with an Apicalypse query body for filtering, sorting, and field selection.\n  tags:\n  - Igdb\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: igdb\n    baseUri: https://api.igdb.com/v4\n    description: IGDB API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Client-ID\n      value: '{{IGDB_TOKEN}}'\n    resources:\n    - name: games\n      path: /games\n      operations:\n      - name: post-games\n        method: POST\n        description:\
  \ Query games\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: platforms\n      path: /platforms\n      operations:\n      - name: post-platforms\n        method: POST\n        description: Query platforms\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies\n      path: /companies\n      operations:\n      - name: post-companies\n        method: POST\n        description: Query companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: involved-companies\n      path: /involved_companies\n      operations:\n      - name: post-involved-companies\n        method: POST\n        description: Query involved companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: genres\n      path: /genres\n      operations:\n      - name: post-genres\n        method: POST\n        description: Query genres\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: themes\n      path: /themes\n      operations:\n      - name: post-themes\n        method: POST\n        description: Query themes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: game-modes\n      path: /game_modes\n      operations:\n      - name: post-game-modes\n        method: POST\n        description: Query game modes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: covers\n      path: /covers\n      operations:\n      - name: post-covers\n        method: POST\n        description: Query game covers\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: screenshots\n      path: /screenshots\n      operations:\n      - name: post-screenshots\n        method: POST\n        description: Query screenshots\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artworks\n      path: /artworks\n      operations:\n      - name: post-artworks\n        method: POST\n        description: Query artworks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: release-dates\n      path: /release_dates\n      operations:\n      - name: post-release-dates\n        method: POST\n        description: Query release dates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \  - name: collections\n      path: /collections\n      operations:\n      - name: post-collections\n        method: POST\n        description: Query collections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: franchises\n      path: /franchises\n      operations:\n      - name: post-franchises\n        method: POST\n        description: Query franchises\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: keywords\n      path: /keywords\n      operations:\n      - name: post-keywords\n        method: POST\n        description: Query keywords\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: age-ratings\n      path: /age_ratings\n      operations:\n      - name: post-age-ratings\n        method: POST\n        description:\
  \ Query age ratings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: websites\n      path: /websites\n      operations:\n      - name: post-websites\n        method: POST\n        description: Query game websites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      operations:\n      - name: post-search\n        method: POST\n        description: Search across IGDB entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: igdb-rest\n    description: REST adapter for IGDB API.\n    resources:\n    - path: /games\n      name: post-games\n      operations:\n      - method: POST\n        name: post-games\n        description: Query games\n     \
  \   call: igdb.post-games\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /platforms\n      name: post-platforms\n      operations:\n      - method: POST\n        name: post-platforms\n        description: Query platforms\n        call: igdb.post-platforms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies\n      name: post-companies\n      operations:\n      - method: POST\n        name: post-companies\n        description: Query companies\n        call: igdb.post-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /involved_companies\n      name: post-involved-companies\n      operations:\n      - method: POST\n        name: post-involved-companies\n        description: Query involved companies\n        call: igdb.post-involved-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /genres\n      name: post-genres\n\
  \      operations:\n      - method: POST\n        name: post-genres\n        description: Query genres\n        call: igdb.post-genres\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /themes\n      name: post-themes\n      operations:\n      - method: POST\n        name: post-themes\n        description: Query themes\n        call: igdb.post-themes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /game_modes\n      name: post-game-modes\n      operations:\n      - method: POST\n        name: post-game-modes\n        description: Query game modes\n        call: igdb.post-game-modes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /covers\n      name: post-covers\n      operations:\n      - method: POST\n        name: post-covers\n        description: Query game covers\n        call: igdb.post-covers\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /screenshots\n      name: post-screenshots\n      operations:\n      - method: POST\n        name: post-screenshots\n        description: Query screenshots\n        call: igdb.post-screenshots\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /artworks\n      name: post-artworks\n      operations:\n      - method: POST\n        name: post-artworks\n        description: Query artworks\n        call: igdb.post-artworks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /release_dates\n      name: post-release-dates\n      operations:\n      - method: POST\n        name: post-release-dates\n        description: Query release dates\n        call: igdb.post-release-dates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collections\n      name: post-collections\n      operations:\n      - method: POST\n        name: post-collections\n        description: Query collections\n\
  \        call: igdb.post-collections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /franchises\n      name: post-franchises\n      operations:\n      - method: POST\n        name: post-franchises\n        description: Query franchises\n        call: igdb.post-franchises\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /keywords\n      name: post-keywords\n      operations:\n      - method: POST\n        name: post-keywords\n        description: Query keywords\n        call: igdb.post-keywords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /age_ratings\n      name: post-age-ratings\n      operations:\n      - method: POST\n        name: post-age-ratings\n        description: Query age ratings\n        call: igdb.post-age-ratings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /websites\n      name: post-websites\n      operations:\n\
  \      - method: POST\n        name: post-websites\n        description: Query game websites\n        call: igdb.post-websites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search\n      name: post-search\n      operations:\n      - method: POST\n        name: post-search\n        description: Search across IGDB entities\n        call: igdb.post-search\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: igdb-mcp\n    transport: http\n    description: MCP adapter for IGDB API for AI agent use.\n    tools:\n    - name: post-games\n      description: Query games\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-games\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-platforms\n      description: Query platforms\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: igdb.post-platforms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-companies\n      description: Query companies\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-companies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-involved-companies\n      description: Query involved companies\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-involved-companies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-genres\n      description: Query genres\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-genres\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-themes\n      description: Query themes\n      hints:\n   \
  \     readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-themes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-game-modes\n      description: Query game modes\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-game-modes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-covers\n      description: Query game covers\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-covers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-screenshots\n      description: Query screenshots\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-screenshots\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-artworks\n      description:\
  \ Query artworks\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-artworks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-release-dates\n      description: Query release dates\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-release-dates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-collections\n      description: Query collections\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-collections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-franchises\n      description: Query franchises\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-franchises\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: post-keywords\n      description: Query keywords\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-keywords\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-age-ratings\n      description: Query age ratings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-age-ratings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-websites\n      description: Query game websites\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-websites\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-search\n      description: Search across IGDB entities\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: igdb.post-search\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    IGDB_TOKEN: IGDB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/igdb/refs/heads/main/capabilities/igdb-capability.yaml
tags:
- Igdb
- API
tools:
- description: Query games
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-games
- description: Query platforms
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-platforms
- description: Query companies
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-companies
- description: Query involved companies
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-involved-companies
- description: Query genres
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-genres
- description: Query themes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-themes
- description: Query game modes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-game-modes
- description: Query game covers
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-covers
- description: Query screenshots
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-screenshots
- description: Query artworks
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-artworks
- description: Query release dates
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-release-dates
- description: Query collections
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-collections
- description: Query franchises
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-franchises
- description: Query keywords
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-keywords
- description: Query age ratings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-age-ratings
- description: Query game websites
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-websites
- description: Search across IGDB entities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-search
---

---
categories: []
consumed_apis: []
description: Workflow capability for entertainment content discovery and metadata enrichment using TiVo's Video Metadata API. Combines content search, ID-based lookup, imagery retrieval, and episode data for streaming platforms, smart TV applications, IPTV providers, and content recommendation systems.
layout: capability
name: TiVo Entertainment Metadata
operations:
- description: Search for movies, TV shows, and other entertainment content
  method: GET
  name: search-content
  path: /v1/content/search
- description: Get complete metadata for a content item by ID
  method: GET
  name: lookup-content-by-id
  path: /v1/content/{contentId}
- description: Get posters, backdrops, and stills for a content item
  method: GET
  name: get-content-images
  path: /v1/content/{contentId}/images
- description: Get all seasons for a TV series
  method: GET
  name: get-content-seasons
  path: /v1/content/{contentId}/seasons
- description: Get episodes for a TV series with optional season filter
  method: GET
  name: get-content-episodes
  path: /v1/content/{contentId}/episodes
- description: Get biography and credits for a cast or crew member
  method: GET
  name: lookup-person
  path: /v1/people/{personId}
personas: []
provider_name: Tivo
provider_slug: tivo
search_terms:
- search for movies, tv shows, and other entertainment content
- search tivo's entertainment catalog for movies, tv series, or episodes by title, genre, year, or type
- get episodes for a tv series with optional season filter
- movies
- full metadata for a specific content item
- get complete metadata for a content item by id
- content discovery
- get content images
- entertainment imagery for a content item
- season listing for a tv series
- get biography and credits for a cast or crew member
- get posters, backdrops, stills, and promotional images for a tivo content item
- music
- get content seasons
- list all seasons of a tv series with episode counts and season metadata
- list tv series episodes with air dates, titles, and descriptions, optionally filtered by season
- get all seasons for a tv series
- television
- lookup content by id
- get biography, birth information, filmography credits, and images for an actor, director, or writer
- search content
- search entertainment content by flexible metadata fields
- get posters, backdrops, and stills for a content item
- entertainment
- retrieve full tivo metadata for a content item using its rovi, tmdb, or eidr identifier
- person profiles and filmography
- streaming
- episode listing for a tv series
- metadata
- get content episodes
- lookup person
slug: entertainment-metadata
source_filename: entertainment-metadata.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TiVo Entertainment Metadata\n  description: Workflow capability for entertainment content discovery and metadata enrichment using TiVo's Video Metadata\n    API. Combines content search, ID-based lookup, imagery retrieval, and episode data for streaming platforms, smart TV applications,\n    IPTV providers, and content recommendation systems.\n  tags:\n  - Entertainment\n  - Metadata\n  - Television\n  - Movies\n  - Streaming\n  - Content Discovery\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TIVO_API_TOKEN: TIVO_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tivo-video\n    baseUri: https://data.tivo.com\n    description: TiVo Video Metadata REST API\n    authentication:\n      type: bearer\n      token: '{{TIVO_API_TOKEN}}'\n    resources:\n    - name: content-search\n      path: /v3/content/search\n      description: Search for entertainment content by metadata fields\n\
  \      operations:\n      - name: search-content\n        method: GET\n        description: Search for TV shows, movies, and other content by flexible metadata fields\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query text\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: 'Content type: movie, series, episode, person, sport, program'\n        - name: genre\n          in: query\n          type: string\n          required: false\n          description: Genre filter\n        - name: year\n          in: query\n          type: integer\n          required: false\n          description: Release year filter\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Language code (ISO 639-1)\n        - name: limit\n          in: query\n          type: integer\n   \
  \       required: false\n          description: Maximum results to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: Additional fields to include\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-lookup\n      path: /v3/content/{contentId}\n      description: Retrieve content by known identifier\n      operations:\n      - name: lookup-content-by-id\n        method: GET\n        description: Look up content metadata using a known Rovi, TMDB, or EIDR identifier\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Content identifier\n        - name: idType\n          in: query\n       \
  \   type: string\n          required: false\n          description: 'Identifier type: rovi, rovi2, tmdb, eidr'\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: 'Additional fields: cast, images'\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Language for localized metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-images\n      path: /v3/content/{contentId}/images\n      description: Retrieve entertainment imagery\n      operations:\n      - name: get-content-images\n        method: GET\n        description: Get posters, backdrops, stills, and other images for a content item\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Content identifier\n\
  \        - name: type\n          in: query\n          type: string\n          required: false\n          description: 'Image type: poster, backdrop, still, headshot, logo'\n        - name: width\n          in: query\n          type: integer\n          required: false\n          description: Preferred image width in pixels\n        - name: height\n          in: query\n          type: integer\n          required: false\n          description: Preferred image height in pixels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-seasons\n      path: /v3/content/{contentId}/seasons\n      description: Retrieve TV series season data\n      operations:\n      - name: get-content-seasons\n        method: GET\n        description: Get season information for a TV series\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n         \
  \ description: Series content identifier\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Language code for localized data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-episodes\n      path: /v3/content/{contentId}/episodes\n      description: Retrieve TV series episode listings\n      operations:\n      - name: get-content-episodes\n        method: GET\n        description: Get episode listings for a TV series or season\n        inputParameters:\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Series content identifier\n        - name: season\n          in: query\n          type: integer\n          required: false\n          description: Season number to filter\n        - name: limit\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Maximum episodes to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: person-lookup\n      path: /v3/people/{personId}\n      description: Retrieve person metadata\n      operations:\n      - name: lookup-person\n        method: GET\n        description: Get biography, filmography, and images for a person\n        inputParameters:\n        - name: personId\n          in: path\n          type: string\n          required: true\n          description: Person identifier\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: 'Additional fields: credits, images, biography'\n        - name: language\n          in: query\n          type: string\n          required:\
  \ false\n          description: Language code for localized data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tivo-entertainment-api\n    description: Unified REST API for TiVo entertainment content discovery and metadata.\n    resources:\n    - path: /v1/content/search\n      name: content-search\n      description: Search entertainment content by flexible metadata fields\n      operations:\n      - method: GET\n        name: search-content\n        description: Search for movies, TV shows, and other entertainment content\n        call: tivo-video.search-content\n        with:\n          q: rest.q\n          type: rest.type\n          genre: rest.genre\n          year: rest.year\n          language: rest.language\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/content/{contentId}\n      name: content\n      description: Full metadata for a specific content item\n      operations:\n      - method: GET\n        name: lookup-content-by-id\n        description: Get complete metadata for a content item by ID\n        call: tivo-video.lookup-content-by-id\n        with:\n          contentId: rest.contentId\n          idType: rest.idType\n          include: rest.include\n          language: rest.language\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/{contentId}/images\n      name: content-images\n      description: Entertainment imagery for a content item\n      operations:\n      - method: GET\n        name: get-content-images\n        description: Get posters, backdrops, and stills for a content item\n        call: tivo-video.get-content-images\n        with:\n          contentId: rest.contentId\n          type: rest.type\n          width: rest.width\n          height: rest.height\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/{contentId}/seasons\n      name: seasons\n      description: Season listing for a TV series\n      operations:\n      - method: GET\n        name: get-content-seasons\n        description: Get all seasons for a TV series\n        call: tivo-video.get-content-seasons\n        with:\n          contentId: rest.contentId\n          language: rest.language\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content/{contentId}/episodes\n      name: episodes\n      description: Episode listing for a TV series\n      operations:\n      - method: GET\n        name: get-content-episodes\n        description: Get episodes for a TV series with optional season filter\n        call: tivo-video.get-content-episodes\n        with:\n          contentId: rest.contentId\n          season: rest.season\n          limit: rest.limit\n          offset: rest.offset\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/people/{personId}\n      name: people\n      description: Person profiles and filmography\n      operations:\n      - method: GET\n        name: lookup-person\n        description: Get biography and credits for a cast or crew member\n        call: tivo-video.lookup-person\n        with:\n          personId: rest.personId\n          include: rest.include\n          language: rest.language\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tivo-entertainment-mcp\n    transport: http\n    description: MCP server for AI-assisted entertainment content discovery and metadata enrichment.\n    tools:\n    - name: search-content\n      description: Search TiVo's entertainment catalog for movies, TV series, or episodes by title, genre, year, or type\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tivo-video.search-content\n\
  \      with:\n        q: tools.q\n        type: tools.type\n        genre: tools.genre\n        year: tools.year\n        language: tools.language\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-content-by-id\n      description: Retrieve full TiVo metadata for a content item using its Rovi, TMDB, or EIDR identifier\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tivo-video.lookup-content-by-id\n      with:\n        contentId: tools.contentId\n        idType: tools.idType\n        include: tools.include\n        language: tools.language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-images\n      description: Get posters, backdrops, stills, and promotional images for a TiVo content item\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tivo-video.get-content-images\n      with:\n        contentId: tools.contentId\n    \
  \    type: tools.type\n        width: tools.width\n        height: tools.height\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-seasons\n      description: List all seasons of a TV series with episode counts and season metadata\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tivo-video.get-content-seasons\n      with:\n        contentId: tools.contentId\n        language: tools.language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-episodes\n      description: List TV series episodes with air dates, titles, and descriptions, optionally filtered by season\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tivo-video.get-content-episodes\n      with:\n        contentId: tools.contentId\n        season: tools.season\n        limit: tools.limit\n        offset: tools.offset\n      outputParameters:\n      - type: object\n        mapping: $.\n  \
  \  - name: lookup-person\n      description: Get biography, birth information, filmography credits, and images for an actor, director, or writer\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tivo-video.lookup-person\n      with:\n        personId: tools.personId\n        include: tools.include\n        language: tools.language\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tivo/refs/heads/main/capabilities/entertainment-metadata.yaml
tags:
- Entertainment
- Metadata
- Television
- Movies
- Streaming
- Content Discovery
tools:
- description: Search TiVo's entertainment catalog for movies, TV series, or episodes by title, genre, year, or type
  hints:
    openWorld: true
    readOnly: true
  name: search-content
- description: Retrieve full TiVo metadata for a content item using its Rovi, TMDB, or EIDR identifier
  hints:
    openWorld: false
    readOnly: true
  name: lookup-content-by-id
- description: Get posters, backdrops, stills, and promotional images for a TiVo content item
  hints:
    openWorld: false
    readOnly: true
  name: get-content-images
- description: List all seasons of a TV series with episode counts and season metadata
  hints:
    openWorld: false
    readOnly: true
  name: get-content-seasons
- description: List TV series episodes with air dates, titles, and descriptions, optionally filtered by season
  hints:
    openWorld: false
    readOnly: true
  name: get-content-episodes
- description: Get biography, birth information, filmography credits, and images for an actor, director, or writer
  hints:
    openWorld: false
    readOnly: true
  name: lookup-person
---

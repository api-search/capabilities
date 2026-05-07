---
categories: []
consumed_apis: []
description: Workflow capability for discovering, searching, and researching movies, TV series, and people using The Movie Database. Supports entertainment recommendation apps, streaming service aggregators, media library tools, and AI assistants answering questions about films and television.
layout: capability
name: Entertainment Discovery
operations:
- description: Search movies, TV series, and people simultaneously.
  method: GET
  name: search-multi
  path: /v1/search
- description: Search movies by title with optional year filter.
  method: GET
  name: search-movies
  path: /v1/movies/search
- description: Get complete movie details by TMDB ID.
  method: GET
  name: get-movie-details
  path: /v1/movies/{movie_id}
- description: Get recommendations based on a movie.
  method: GET
  name: get-movie-recommendations
  path: /v1/movies/{movie_id}/recommendations
- description: Get currently popular movies.
  method: GET
  name: get-popular-movies
  path: /v1/movies/popular
- description: Get top rated movies on TMDB.
  method: GET
  name: get-top-rated-movies
  path: /v1/movies/top-rated
- description: Search TV series by title.
  method: GET
  name: search-tv
  path: /v1/tv/search
- description: Get complete TV series details by TMDB ID.
  method: GET
  name: get-tv-details
  path: /v1/tv/{series_id}
- description: Get trending movies, TV, and people.
  method: GET
  name: get-trending
  path: /v1/trending/{time_window}
- description: Discover movies using genre, rating, and release year filters.
  method: GET
  name: discover-movies
  path: /v1/discover/movies
- description: Get profile for an actor or crew member.
  method: GET
  name: get-person-details
  path: /v1/people/{person_id}
personas: []
provider_name: The Movie Database
provider_slug: the-movie-database
search_terms:
- movies
- streaming
- get movie credits
- get movie recommendations
- get the cast and crew for a movie.
- get a list of currently popular movies on tmdb.
- get movie details
- get profile for an actor or crew member.
- discover movies
- top-rated movies list.
- search multi
- get top rated movies on tmdb.
- get full movie details including genres, production companies, budget, revenue, and ratings.
- get complete movie details by tmdb id.
- get the cast and crew for a tv series.
- search tv
- get trending movies, tv, and people.
- discover movies by genre and other filters.
- person profile information.
- search tv series by title.
- search for tv series by title.
- get recommended movies based on a seed movie.
- detailed tv series information.
- get currently popular movies.
- get tv details
- search for movies by title with optional year and language filters.
- discover movies using genre, rating, and release year filters.
- search tv series
- get trending content
- search for tv series.
- search for movies by title.
- popular movies list.
- get trending movies, tv series, or people for today or this week.
- get full details for a tv series including seasons, networks, and episode counts.
- search across movies, tv series, and people simultaneously with a single query.
- television
- search all media
- people
- get recommendations based on a movie.
- detailed movie information.
- discover movies filtered by genre, minimum rating, sort order, and release year.
- get person profile
- get person details
- entertainment
- discover movies by genre
- search movies by title with optional year filter.
- trending content for the day or week.
- get top rated movies
- get trending
- search movies
- get profile, biography, and filmography for an actor, director, or crew member.
- cross-media search across movies, tv, and people.
- get popular movies
- search movies, tv series, and people simultaneously.
- get tv credits
- movie recommendations.
- get complete tv series details by tmdb id.
slug: entertainment-discovery
source_filename: entertainment-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Entertainment Discovery\n  description: Workflow capability for discovering, searching, and researching movies, TV series, and people using The Movie\n    Database. Supports entertainment recommendation apps, streaming service aggregators, media library tools, and AI assistants\n    answering questions about films and television.\n  tags:\n  - Entertainment\n  - Movies\n  - People\n  - Streaming\n  - Television\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TMDB_ACCESS_TOKEN: TMDB_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tmdb\n    baseUri: https://api.themoviedb.org/3\n    description: The Movie Database API v3 — movies, TV, people, and images.\n    authentication:\n      type: bearer\n      token: '{{TMDB_ACCESS_TOKEN}}'\n    resources:\n    - name: search\n      path: /search\n      description: Search across movies, TV series, people, and all media.\n      operations:\n\
  \      - name: search-movies\n        method: GET\n        description: Search for movies by title.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Movie title search query.\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: ISO 639-1 language code.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: year\n          in: query\n          type: integer\n          required: false\n          description: Filter by release year.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-tv\n        method: GET\n        description: Search for TV series by title.\n        inputParameters:\n        - name: query\n          in: query\n          type:\
  \ string\n          required: true\n          description: TV series title search query.\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: ISO 639-1 language code.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-people\n        method: GET\n        description: Search for people (actors, directors, crew) by name.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Person name search query.\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: ISO 639-1 language code.\n        - name: page\n          in: query\n          type: integer\n\
  \          required: false\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-multi\n        method: GET\n        description: Search across movies, TV series, and people simultaneously.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query.\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: ISO 639-1 language code.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: movies\n      path: /movie\n      description: Movie data, discovery, and trending.\n      operations:\n\
  \      - name: get-movie-details\n        method: GET\n        description: Get full details for a movie by ID.\n        inputParameters:\n        - name: movie_id\n          in: path\n          type: integer\n          required: true\n          description: TMDB movie ID.\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: ISO 639-1 language code.\n        - name: append_to_response\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of sub-requests to append.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-movie-credits\n        method: GET\n        description: Get cast and crew credits for a movie.\n        inputParameters:\n        - name: movie_id\n          in: path\n          type: integer\n          required: true\n          description: TMDB movie\
  \ ID.\n        - name: language\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-movie-recommendations\n        method: GET\n        description: Get movie recommendations based on a movie.\n        inputParameters:\n        - name: movie_id\n          in: path\n          type: integer\n          required: true\n        - name: language\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-popular-movies\n        method: GET\n        description: Get a list of currently popular movies.\n        inputParameters:\n        - name: language\n          in: query\n      \
  \    type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: region\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-top-rated-movies\n        method: GET\n        description: Get the top rated movies on TMDB.\n        inputParameters:\n        - name: language\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tv\n      path: /tv\n      description: TV series data, episodes, and trending.\n      operations:\n      - name: get-tv-details\n        method: GET\n        description:\
  \ Get full details for a TV series by ID.\n        inputParameters:\n        - name: series_id\n          in: path\n          type: integer\n          required: true\n          description: TMDB TV series ID.\n        - name: language\n          in: query\n          type: string\n          required: false\n        - name: append_to_response\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-tv-credits\n        method: GET\n        description: Get cast and crew credits for a TV series.\n        inputParameters:\n        - name: series_id\n          in: path\n          type: integer\n          required: true\n        - name: language\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: get-popular-tv\n        method: GET\n        description: Get a list of currently popular TV series.\n        inputParameters:\n        - name: language\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trending\n      path: /trending\n      description: Trending movies, TV, and people.\n      operations:\n      - name: get-trending\n        method: GET\n        description: Get trending movies, TV series, or people for a time window.\n        inputParameters:\n        - name: time_window\n          in: path\n          type: string\n          required: true\n          description: Time window — day or week.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: people\n      path: /person\n      description: Person profiles and credits.\n      operations:\n      - name: get-person-details\n        method: GET\n        description: Get full details for a person (actor, director, etc.).\n        inputParameters:\n        - name: person_id\n          in: path\n          type: integer\n          required: true\n          description: TMDB person ID.\n        - name: language\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-person-credits\n        method: GET\n        description: Get combined movie and TV credits for a person.\n        inputParameters:\n        - name: person_id\n          in: path\n          type: integer\n          required: true\n        - name: language\n          in: query\n          type: string\n          required: false\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: discover\n      path: /discover\n      description: Discover movies and TV series by genre, rating, and other filters.\n      operations:\n      - name: discover-movies\n        method: GET\n        description: Discover movies using extensive filters.\n        inputParameters:\n        - name: language\n          in: query\n          type: string\n          required: false\n        - name: sort_by\n          in: query\n          type: string\n          required: false\n        - name: with_genres\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: vote_average_gte\n          in: query\n          type: number\n          required: false\n        - name: year\n          in: query\n          type: integer\n          required:\
  \ false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: discover-tv\n        method: GET\n        description: Discover TV series using extensive filters.\n        inputParameters:\n        - name: language\n          in: query\n          type: string\n          required: false\n        - name: sort_by\n          in: query\n          type: string\n          required: false\n        - name: with_genres\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: entertainment-discovery-api\n    description: Unified REST API for movie and TV discovery, search, and detailed information.\n    resources:\n    -\
  \ path: /v1/search\n      name: search\n      description: Cross-media search across movies, TV, and people.\n      operations:\n      - method: GET\n        name: search-multi\n        description: Search movies, TV series, and people simultaneously.\n        call: tmdb.search-multi\n        with:\n          query: rest.query\n          language: rest.language\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/movies/search\n      name: movie-search\n      description: Search for movies by title.\n      operations:\n      - method: GET\n        name: search-movies\n        description: Search movies by title with optional year filter.\n        call: tmdb.search-movies\n        with:\n          query: rest.query\n          language: rest.language\n          year: rest.year\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/movies/{movie_id}\n      name:\
  \ movie-detail\n      description: Detailed movie information.\n      operations:\n      - method: GET\n        name: get-movie-details\n        description: Get complete movie details by TMDB ID.\n        call: tmdb.get-movie-details\n        with:\n          movie_id: rest.movie_id\n          language: rest.language\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/movies/{movie_id}/recommendations\n      name: movie-recommendations\n      description: Movie recommendations.\n      operations:\n      - method: GET\n        name: get-movie-recommendations\n        description: Get recommendations based on a movie.\n        call: tmdb.get-movie-recommendations\n        with:\n          movie_id: rest.movie_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/movies/popular\n      name: popular-movies\n      description: Popular movies list.\n      operations:\n      - method: GET\n        name: get-popular-movies\n\
  \        description: Get currently popular movies.\n        call: tmdb.get-popular-movies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/movies/top-rated\n      name: top-rated-movies\n      description: Top-rated movies list.\n      operations:\n      - method: GET\n        name: get-top-rated-movies\n        description: Get top rated movies on TMDB.\n        call: tmdb.get-top-rated-movies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tv/search\n      name: tv-search\n      description: Search for TV series.\n      operations:\n      - method: GET\n        name: search-tv\n        description: Search TV series by title.\n        call: tmdb.search-tv\n        with:\n          query: rest.query\n          language: rest.language\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tv/{series_id}\n      name: tv-detail\n      description:\
  \ Detailed TV series information.\n      operations:\n      - method: GET\n        name: get-tv-details\n        description: Get complete TV series details by TMDB ID.\n        call: tmdb.get-tv-details\n        with:\n          series_id: rest.series_id\n          language: rest.language\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trending/{time_window}\n      name: trending\n      description: Trending content for the day or week.\n      operations:\n      - method: GET\n        name: get-trending\n        description: Get trending movies, TV, and people.\n        call: tmdb.get-trending\n        with:\n          time_window: rest.time_window\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/discover/movies\n      name: discover-movies\n      description: Discover movies by genre and other filters.\n      operations:\n      - method: GET\n        name: discover-movies\n        description: Discover\
  \ movies using genre, rating, and release year filters.\n        call: tmdb.discover-movies\n        with:\n          with_genres: rest.with_genres\n          sort_by: rest.sort_by\n          year: rest.year\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/people/{person_id}\n      name: person-detail\n      description: Person profile information.\n      operations:\n      - method: GET\n        name: get-person-details\n        description: Get profile for an actor or crew member.\n        call: tmdb.get-person-details\n        with:\n          person_id: rest.person_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: entertainment-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted entertainment discovery, movie research, and content recommendations.\n    tools:\n    - name: search-all-media\n      description: Search across movies, TV series,\
  \ and people simultaneously with a single query.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tmdb.search-multi\n      with:\n        query: tools.query\n        language: tools.language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-movies\n      description: Search for movies by title with optional year and language filters.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tmdb.search-movies\n      with:\n        query: tools.query\n        year: tools.year\n        language: tools.language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-movie-details\n      description: Get full movie details including genres, production companies, budget, revenue, and ratings.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tmdb.get-movie-details\n      with:\n        movie_id: tools.movie_id\n        language: tools.language\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-movie-credits\n      description: Get the cast and crew for a movie.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tmdb.get-movie-credits\n      with:\n        movie_id: tools.movie_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-movie-recommendations\n      description: Get recommended movies based on a seed movie.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tmdb.get-movie-recommendations\n      with:\n        movie_id: tools.movie_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-tv-series\n      description: Search for TV series by title.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tmdb.search-tv\n      with:\n        query: tools.query\n        language: tools.language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-tv-details\n      description: Get full details for a TV series including seasons, networks, and episode counts.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tmdb.get-tv-details\n      with:\n        series_id: tools.series_id\n        language: tools.language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tv-credits\n      description: Get the cast and crew for a TV series.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tmdb.get-tv-credits\n      with:\n        series_id: tools.series_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trending-content\n      description: Get trending movies, TV series, or people for today or this week.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tmdb.get-trending\n      with:\n        time_window: tools.time_window\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: discover-movies-by-genre\n      description: Discover movies filtered by genre, minimum rating, sort order, and release year.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tmdb.discover-movies\n      with:\n        with_genres: tools.with_genres\n        sort_by: tools.sort_by\n        vote_average_gte: tools.vote_average_gte\n        year: tools.year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-popular-movies\n      description: Get a list of currently popular movies on TMDB.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tmdb.get-popular-movies\n      with:\n        language: tools.language\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-person-profile\n      description: Get profile, biography, and filmography for an actor, director, or crew member.\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: tmdb.get-person-details\n      with:\n        person_id: tools.person_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/the-movie-database/refs/heads/main/capabilities/entertainment-discovery.yaml
tags:
- Entertainment
- Movies
- People
- Streaming
- Television
tools:
- description: Search across movies, TV series, and people simultaneously with a single query.
  hints:
    openWorld: true
    readOnly: true
  name: search-all-media
- description: Search for movies by title with optional year and language filters.
  hints:
    openWorld: true
    readOnly: true
  name: search-movies
- description: Get full movie details including genres, production companies, budget, revenue, and ratings.
  hints:
    openWorld: false
    readOnly: true
  name: get-movie-details
- description: Get the cast and crew for a movie.
  hints:
    openWorld: false
    readOnly: true
  name: get-movie-credits
- description: Get recommended movies based on a seed movie.
  hints:
    openWorld: false
    readOnly: true
  name: get-movie-recommendations
- description: Search for TV series by title.
  hints:
    openWorld: true
    readOnly: true
  name: search-tv-series
- description: Get full details for a TV series including seasons, networks, and episode counts.
  hints:
    openWorld: false
    readOnly: true
  name: get-tv-details
- description: Get the cast and crew for a TV series.
  hints:
    openWorld: false
    readOnly: true
  name: get-tv-credits
- description: Get trending movies, TV series, or people for today or this week.
  hints:
    openWorld: true
    readOnly: true
  name: get-trending-content
- description: Discover movies filtered by genre, minimum rating, sort order, and release year.
  hints:
    openWorld: true
    readOnly: true
  name: discover-movies-by-genre
- description: Get a list of currently popular movies on TMDB.
  hints:
    openWorld: true
    readOnly: true
  name: get-popular-movies
- description: Get profile, biography, and filmography for an actor, director, or crew member.
  hints:
    openWorld: false
    readOnly: true
  name: get-person-profile
---

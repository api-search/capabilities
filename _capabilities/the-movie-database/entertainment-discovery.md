---
api_specs:
- filename: the-movie-database-openapi.json
  format: json
  label: tmdb
  slug: tmdb
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/the-movie-database/refs/heads/main/openapi/the-movie-database-openapi.json
categories: []
consumed_apis:
- tmdb
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
- search movies by title with optional year filter.
- get popular movies
- search all media
- search for movies by title with optional year and language filters.
- get complete movie details by tmdb id.
- get trending movies, tv series, or people for today or this week.
- discover movies by genre
- get top rated movies on tmdb.
- search tv
- get tv details
- get profile for an actor or crew member.
- discover movies filtered by genre, minimum rating, sort order, and release year.
- movies
- search for movies by title.
- get movie recommendations
- detailed tv series information.
- movie recommendations.
- search movies
- get movie details
- search multi
- get the cast and crew for a tv series.
- get the cast and crew for a movie.
- get full details for a tv series including seasons, networks, and episode counts.
- get movie credits
- streaming
- discover movies
- get profile, biography, and filmography for an actor, director, or crew member.
- discover movies by genre and other filters.
- get currently popular movies.
- entertainment
- get trending content
- television
- get tv credits
- search movies, tv series, and people simultaneously.
- popular movies list.
- cross-media search across movies, tv, and people.
- person profile information.
- trending content for the day or week.
- get trending
- detailed movie information.
- get a list of currently popular movies on tmdb.
- get top rated movies
- get person profile
- get recommendations based on a movie.
- search tv series
- get trending movies, tv, and people.
- get complete tv series details by tmdb id.
- get person details
- get full movie details including genres, production companies, budget, revenue, and ratings.
- search across movies, tv series, and people simultaneously with a single query.
- discover movies using genre, rating, and release year filters.
- people
- search tv series by title.
- search for tv series by title.
- get recommended movies based on a seed movie.
- search for tv series.
- top-rated movies list.
slug: entertainment-discovery
source_filename: entertainment-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Entertainment Discovery\"\n  description: >-\n    Workflow capability for discovering, searching, and researching movies, TV series,\n    and people using The Movie Database. Supports entertainment recommendation apps,\n    streaming service aggregators, media library tools, and AI assistants answering\n    questions about films and television.\n  tags:\n    - Entertainment\n    - Movies\n    - People\n    - Streaming\n    - Television\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TMDB_ACCESS_TOKEN: TMDB_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: tmdb\n      location: ./shared/the-movie-database.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: entertainment-discovery-api\n      description: \"Unified REST API for movie and TV discovery, search, and detailed information.\"\n      resources:\n        - path: /v1/search\n          name: search\n\
  \          description: Cross-media search across movies, TV, and people.\n          operations:\n            - method: GET\n              name: search-multi\n              description: Search movies, TV series, and people simultaneously.\n              call: \"tmdb.search-multi\"\n              with:\n                query: \"rest.query\"\n                language: \"rest.language\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/movies/search\n          name: movie-search\n          description: Search for movies by title.\n          operations:\n            - method: GET\n              name: search-movies\n              description: Search movies by title with optional year filter.\n              call: \"tmdb.search-movies\"\n              with:\n                query: \"rest.query\"\n                language: \"rest.language\"\n                year: \"rest.year\"\n        \
  \        page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/movies/{movie_id}\n          name: movie-detail\n          description: Detailed movie information.\n          operations:\n            - method: GET\n              name: get-movie-details\n              description: Get complete movie details by TMDB ID.\n              call: \"tmdb.get-movie-details\"\n              with:\n                movie_id: \"rest.movie_id\"\n                language: \"rest.language\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/movies/{movie_id}/recommendations\n          name: movie-recommendations\n          description: Movie recommendations.\n          operations:\n            - method: GET\n              name: get-movie-recommendations\n              description: Get recommendations based on a movie.\n              call: \"tmdb.get-movie-recommendations\"\
  \n              with:\n                movie_id: \"rest.movie_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/movies/popular\n          name: popular-movies\n          description: Popular movies list.\n          operations:\n            - method: GET\n              name: get-popular-movies\n              description: Get currently popular movies.\n              call: \"tmdb.get-popular-movies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/movies/top-rated\n          name: top-rated-movies\n          description: Top-rated movies list.\n          operations:\n            - method: GET\n              name: get-top-rated-movies\n              description: Get top rated movies on TMDB.\n              call: \"tmdb.get-top-rated-movies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n \
  \       - path: /v1/tv/search\n          name: tv-search\n          description: Search for TV series.\n          operations:\n            - method: GET\n              name: search-tv\n              description: Search TV series by title.\n              call: \"tmdb.search-tv\"\n              with:\n                query: \"rest.query\"\n                language: \"rest.language\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tv/{series_id}\n          name: tv-detail\n          description: Detailed TV series information.\n          operations:\n            - method: GET\n              name: get-tv-details\n              description: Get complete TV series details by TMDB ID.\n              call: \"tmdb.get-tv-details\"\n              with:\n                series_id: \"rest.series_id\"\n                language: \"rest.language\"\n              outputParameters:\n          \
  \      - type: object\n                  mapping: \"$.\"\n        - path: /v1/trending/{time_window}\n          name: trending\n          description: Trending content for the day or week.\n          operations:\n            - method: GET\n              name: get-trending\n              description: Get trending movies, TV, and people.\n              call: \"tmdb.get-trending\"\n              with:\n                time_window: \"rest.time_window\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/discover/movies\n          name: discover-movies\n          description: Discover movies by genre and other filters.\n          operations:\n            - method: GET\n              name: discover-movies\n              description: Discover movies using genre, rating, and release year filters.\n              call: \"tmdb.discover-movies\"\n              with:\n                with_genres: \"rest.with_genres\"\n           \
  \     sort_by: \"rest.sort_by\"\n                year: \"rest.year\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/people/{person_id}\n          name: person-detail\n          description: Person profile information.\n          operations:\n            - method: GET\n              name: get-person-details\n              description: Get profile for an actor or crew member.\n              call: \"tmdb.get-person-details\"\n              with:\n                person_id: \"rest.person_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: entertainment-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted entertainment discovery, movie research, and content recommendations.\"\n      tools:\n        - name: search-all-media\n          description: Search across movies, TV series,\
  \ and people simultaneously with a single query.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tmdb.search-multi\"\n          with:\n            query: \"tools.query\"\n            language: \"tools.language\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-movies\n          description: Search for movies by title with optional year and language filters.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tmdb.search-movies\"\n          with:\n            query: \"tools.query\"\n            year: \"tools.year\"\n            language: \"tools.language\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-movie-details\n          description: Get full movie details including genres, production companies, budget, revenue, and ratings.\n          hints:\n            readOnly: true\n\
  \            openWorld: false\n          call: \"tmdb.get-movie-details\"\n          with:\n            movie_id: \"tools.movie_id\"\n            language: \"tools.language\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-movie-credits\n          description: Get the cast and crew for a movie.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tmdb.get-movie-credits\"\n          with:\n            movie_id: \"tools.movie_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-movie-recommendations\n          description: Get recommended movies based on a seed movie.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tmdb.get-movie-recommendations\"\n          with:\n            movie_id: \"tools.movie_id\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: search-tv-series\n          description: Search for TV series by title.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tmdb.search-tv\"\n          with:\n            query: \"tools.query\"\n            language: \"tools.language\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-tv-details\n          description: Get full details for a TV series including seasons, networks, and episode counts.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tmdb.get-tv-details\"\n          with:\n            series_id: \"tools.series_id\"\n            language: \"tools.language\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-tv-credits\n          description: Get the cast and crew for a TV series.\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"tmdb.get-tv-credits\"\n          with:\n            series_id: \"tools.series_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-trending-content\n          description: Get trending movies, TV series, or people for today or this week.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tmdb.get-trending\"\n          with:\n            time_window: \"tools.time_window\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: discover-movies-by-genre\n          description: Discover movies filtered by genre, minimum rating, sort order, and release year.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tmdb.discover-movies\"\n          with:\n            with_genres: \"tools.with_genres\"\n            sort_by: \"tools.sort_by\"\n            vote_average_gte: \"tools.vote_average_gte\"\
  \n            year: \"tools.year\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-popular-movies\n          description: Get a list of currently popular movies on TMDB.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tmdb.get-popular-movies\"\n          with:\n            language: \"tools.language\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-person-profile\n          description: Get profile, biography, and filmography for an actor, director, or crew member.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tmdb.get-person-details\"\n          with:\n            person_id: \"tools.person_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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

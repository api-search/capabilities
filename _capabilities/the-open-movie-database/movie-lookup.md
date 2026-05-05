---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Movie Lookup
operations: []
personas: []
provider_name: The Open Movie Database
provider_slug: the-open-movie-database
search_terms:
- television
- metadata
- imdb
- movies
- entertainment
slug: movie-lookup
source_filename: movie-lookup.yaml
source_heading: Capability Spec
source_yaml: "name: Movie Lookup\nversion: 1.0.0-alpha1\ndescription: >-\n  Workflow capability for discovering and retrieving movie, series, and episode\n  information using The Open Movie Database (OMDb) API. Supports title search,\n  direct IMDb ID lookups, TV season/episode retrieval, and access to aggregated\n  ratings from IMDb, Rotten Tomatoes, and Metacritic.\ntags:\n  - Entertainment\n  - Movies\n  - Television\n  - IMDb\n  - Metadata\n\nadapters:\n  rest:\n    port: 8080\n    type: rest\n  mcp:\n    port: 9090\n    type: mcp\n\napis:\n  - name: The Open Movie Database API\n    shared: capabilities/shared/the-open-movie-database.yaml\n    operations:\n      - operationId: searchMovies\n        description: >-\n          Search for movies, series, or episodes by title keyword. Returns\n          paginated results with title, year, IMDb ID, type, and poster URL.\n      - operationId: getMovie\n        description: >-\n          Retrieve full metadata for a specific movie, TV series,\
  \ or episode\n          using IMDb ID or exact title. Returns cast, crew, plot, ratings,\n          box office, and more.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/the-open-movie-database/refs/heads/main/capabilities/movie-lookup.yaml
tags: []
tools: []
---

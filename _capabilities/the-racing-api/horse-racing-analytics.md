---
categories: []
consumed_apis: []
description: Unified workflow for horse racing research, form analysis, and racecard review. Combines racecards, results, horse form, jockey and trainer statistics for racing analysts and application developers.
layout: capability
name: The Racing API Horse Racing Analytics
operations:
- description: Get racecards for today or tomorrow
  method: GET
  name: list-racecards
  path: /v1/racecards
- description: Get historical race results with filters
  method: GET
  name: list-results
  path: /v1/results
- description: List all racing courses
  method: GET
  name: list-courses
  path: /v1/courses
- description: Search for horses by name
  method: GET
  name: search-horses
  path: /v1/horses
- description: Get historical results for a specific horse
  method: GET
  name: get-horse-results
  path: /v1/horses/{id}
- description: Search for jockeys by name
  method: GET
  name: search-jockeys
  path: /v1/jockeys
- description: Search for trainers by name
  method: GET
  name: search-trainers
  path: /v1/trainers
personas: []
provider_name: The Racing API
provider_slug: the-racing-api
search_terms:
- analytics
- list all racing regions with region codes
- list courses
- get jockey results
- search for a jockey by name
- trainer search and statistics
- get full historical race results for a specific horse
- list all racing courses
- get racecards for major featured races
- list regions
- search for a horse owner by name
- get free racecards
- get historical results for a specific horse
- get horse results
- search horses
- get historical training results for a trainer
- get big race cards
- get historical race results filtered by date, region, course, or race type
- racecards
- search for a horse by name to find its id for detailed form queries
- get today's or tomorrow's race cards with runners, odds, and form
- get todays results
- get jockey course analysis
- get historical riding results for a jockey
- jockey search and statistics
- search sires
- get racecards for today or tomorrow
- betting
- list racecards
- get sire offspring performance statistics by race class
- list all available racing courses with ids and regions
- list results
- get trainer results
- search owners
- horse racing
- sports
- search for a trainer by name
- get sire class analysis
- search for a sire by name for breeding analysis
- statistics
- racing courses and regions
- get free-tier racecards for basic race information
- historical race results
- search for jockeys by name
- get jockey performance statistics broken down by course
- horse search and form data
- search trainers
- get historical race results with filters
- get all race results from today
- search jockeys
- search for horses by name
- search for trainers by name
- today's and future race entry cards
- individual horse form and history
slug: horse-racing-analytics
source_filename: horse-racing-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: The Racing API Horse Racing Analytics\n  description: Unified workflow for horse racing research, form analysis, and racecard review. Combines racecards, results,\n    horse form, jockey and trainer statistics for racing analysts and application developers.\n  tags:\n  - Horse Racing\n  - Sports\n  - Analytics\n  - Racecards\n  - Statistics\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RACING_API_USERNAME: RACING_API_USERNAME\n    RACING_API_PASSWORD: RACING_API_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: racing\n    baseUri: https://api.theracingapi.com\n    description: Horse racing data API with racecards, results, and analytics\n    authentication:\n      type: basic\n      username: '{{RACING_API_USERNAME}}'\n      password: '{{RACING_API_PASSWORD}}'\n    resources:\n    - name: courses\n      path: /v1/courses\n      description: Horse racing courses and regions\n\
  \      operations:\n      - name: get-regions\n        method: GET\n        description: Get a list of regions with region codes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-courses\n        method: GET\n        description: Get a list of courses with course IDs and regions\n        inputParameters:\n        - name: region_codes\n          in: query\n          type: array\n          required: false\n          description: Filter by region codes (e.g. gb, ire)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: racecards\n      path: /v1/racecards\n      description: Race entry cards with runners, odds, and form\n      operations:\n      - name: get-free-racecards\n        method: GET\n        description: Get free racecards for today\n        inputParameters:\n        - name: day\n          in: query\n\
  \          type: string\n          required: false\n          description: Day filter (today, tomorrow)\n        - name: region_codes\n          in: query\n          type: array\n          required: false\n          description: Filter by region codes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-standard-racecards\n        method: GET\n        description: Get standard racecards with full runner details\n        inputParameters:\n        - name: day\n          in: query\n          type: string\n          required: false\n          description: Day filter\n        - name: region_codes\n          in: query\n          type: array\n          required: false\n          description: Filter by region codes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pro-racecards\n        method: GET\n       \
  \ description: Get pro racecards with advanced data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-big-race-racecards\n        method: GET\n        description: Get racecards for major races\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results\n      path: /v1/results\n      description: Historical race results\n      operations:\n      - name: get-results\n        method: GET\n        description: Get historical race results with filters\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date YYYY-MM-DD\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: End date YYYY-MM-DD\n        - name: region\n          in: query\n  \
  \        type: string\n          required: false\n          description: Region code\n        - name: course\n          in: query\n          type: string\n          required: false\n          description: Course ID\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Race type (flat, chase, hurdle, nh_flat)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return\n        - name: skip\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-todays-results\n        method: GET\n        description: Get today's race results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: horses\n      path: /v1/horses\n      description: Horse search and form data\n      operations:\n      - name: search-horses\n        method: GET\n        description: Search horses by name\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Horse name to search\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-horse-results\n        method: GET\n        description: Get full historical results for a horse\n        inputParameters:\n        - name: horse_id\n          in: path\n          type: string\n          required: true\n          description: Horse identifier\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Start date filter\n        - name: end_date\n          in: query\n          type: string\n\
  \          required: false\n          description: End date filter\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jockeys\n      path: /v1/jockeys\n      description: Jockey search and performance analytics\n      operations:\n      - name: search-jockeys\n        method: GET\n        description: Search jockeys by name\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Jockey name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-jockey-results\n        method: GET\n        description: Get historical results for a jockey\n        inputParameters:\n        - name: jockey_id\n\
  \          in: path\n          type: string\n          required: true\n          description: Jockey identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-jockey-course-analysis\n        method: GET\n        description: Get jockey statistics by course\n        inputParameters:\n        - name: jockey_id\n          in: path\n          type: string\n          required: true\n          description: Jockey identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trainers\n      path: /v1/trainers\n      description: Trainer search and performance analytics\n      operations:\n      - name: search-trainers\n        method: GET\n        description: Search trainers by name\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n     \
  \     description: Trainer name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-trainer-results\n        method: GET\n        description: Get historical results for a trainer\n        inputParameters:\n        - name: trainer_id\n          in: path\n          type: string\n          required: true\n          description: Trainer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: owners\n      path: /v1/owners\n      description: Owner search and analytics\n      operations:\n      - name: search-owners\n        method: GET\n        description: Search owners by name\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Owner name\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: sires\n      path: /v1/sires\n      description: Sire breeding analysis\n      operations:\n      - name: search-sires\n        method: GET\n        description: Search sires by name\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Sire name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-sire-class-analysis\n        method: GET\n        description: Get sire offspring statistics by race class\n        inputParameters:\n        - name: sire_id\n          in: path\n          type: string\n          required: true\n          description: Sire identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ racing-analytics-api\n    description: Unified REST API for horse racing analytics, form research, and racecard review.\n    resources:\n    - path: /v1/racecards\n      name: racecards\n      description: Today's and future race entry cards\n      operations:\n      - method: GET\n        name: list-racecards\n        description: Get racecards for today or tomorrow\n        call: racing.get-standard-racecards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/results\n      name: results\n      description: Historical race results\n      operations:\n      - method: GET\n        name: list-results\n        description: Get historical race results with filters\n        call: racing.get-results\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses\n      name: courses\n      description: Racing courses and regions\n      operations:\n      - method: GET\n        name: list-courses\n        description:\
  \ List all racing courses\n        call: racing.get-courses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/horses\n      name: horses\n      description: Horse search and form data\n      operations:\n      - method: GET\n        name: search-horses\n        description: Search for horses by name\n        call: racing.search-horses\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/horses/{id}\n      name: horse-detail\n      description: Individual horse form and history\n      operations:\n      - method: GET\n        name: get-horse-results\n        description: Get historical results for a specific horse\n        call: racing.get-horse-results\n        with:\n          horse_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jockeys\n      name: jockeys\n      description: Jockey search and statistics\n   \
  \   operations:\n      - method: GET\n        name: search-jockeys\n        description: Search for jockeys by name\n        call: racing.search-jockeys\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trainers\n      name: trainers\n      description: Trainer search and statistics\n      operations:\n      - method: GET\n        name: search-trainers\n        description: Search for trainers by name\n        call: racing.search-trainers\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: racing-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted horse racing research and form analysis.\n    tools:\n    - name: list-racecards\n      description: Get today's or tomorrow's race cards with runners, odds, and form\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: racing.get-standard-racecards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-free-racecards\n      description: Get free-tier racecards for basic race information\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.get-free-racecards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-big-race-cards\n      description: Get racecards for major featured races\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.get-big-race-racecards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-results\n      description: Get historical race results filtered by date, region, course, or race type\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.get-results\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-todays-results\n      description: Get all\
  \ race results from today\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.get-todays-results\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-courses\n      description: List all available racing courses with IDs and regions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.get-courses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-regions\n      description: List all racing regions with region codes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.get-regions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-horses\n      description: Search for a horse by name to find its ID for detailed form queries\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.search-horses\n      with:\n        name: tools.name\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-horse-results\n      description: Get full historical race results for a specific horse\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.get-horse-results\n      with:\n        horse_id: tools.horse_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-jockeys\n      description: Search for a jockey by name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.search-jockeys\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-jockey-results\n      description: Get historical riding results for a jockey\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.get-jockey-results\n      with:\n        jockey_id: tools.jockey_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-jockey-course-analysis\n      description:\
  \ Get jockey performance statistics broken down by course\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.get-jockey-course-analysis\n      with:\n        jockey_id: tools.jockey_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-trainers\n      description: Search for a trainer by name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.search-trainers\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trainer-results\n      description: Get historical training results for a trainer\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.get-trainer-results\n      with:\n        trainer_id: tools.trainer_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-owners\n      description: Search for a horse owner by name\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: racing.search-owners\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-sires\n      description: Search for a sire by name for breeding analysis\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.search-sires\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sire-class-analysis\n      description: Get sire offspring performance statistics by race class\n      hints:\n        readOnly: true\n        openWorld: true\n      call: racing.get-sire-class-analysis\n      with:\n        sire_id: tools.sire_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/the-racing-api/refs/heads/main/capabilities/horse-racing-analytics.yaml
tags:
- Horse Racing
- Sports
- Analytics
- Racecards
- Statistics
tools:
- description: Get today's or tomorrow's race cards with runners, odds, and form
  hints:
    openWorld: true
    readOnly: true
  name: list-racecards
- description: Get free-tier racecards for basic race information
  hints:
    openWorld: true
    readOnly: true
  name: get-free-racecards
- description: Get racecards for major featured races
  hints:
    openWorld: true
    readOnly: true
  name: get-big-race-cards
- description: Get historical race results filtered by date, region, course, or race type
  hints:
    openWorld: true
    readOnly: true
  name: list-results
- description: Get all race results from today
  hints:
    openWorld: true
    readOnly: true
  name: get-todays-results
- description: List all available racing courses with IDs and regions
  hints:
    openWorld: true
    readOnly: true
  name: list-courses
- description: List all racing regions with region codes
  hints:
    openWorld: true
    readOnly: true
  name: list-regions
- description: Search for a horse by name to find its ID for detailed form queries
  hints:
    openWorld: true
    readOnly: true
  name: search-horses
- description: Get full historical race results for a specific horse
  hints:
    openWorld: true
    readOnly: true
  name: get-horse-results
- description: Search for a jockey by name
  hints:
    openWorld: true
    readOnly: true
  name: search-jockeys
- description: Get historical riding results for a jockey
  hints:
    openWorld: true
    readOnly: true
  name: get-jockey-results
- description: Get jockey performance statistics broken down by course
  hints:
    openWorld: true
    readOnly: true
  name: get-jockey-course-analysis
- description: Search for a trainer by name
  hints:
    openWorld: true
    readOnly: true
  name: search-trainers
- description: Get historical training results for a trainer
  hints:
    openWorld: true
    readOnly: true
  name: get-trainer-results
- description: Search for a horse owner by name
  hints:
    openWorld: true
    readOnly: true
  name: search-owners
- description: Search for a sire by name for breeding analysis
  hints:
    openWorld: true
    readOnly: true
  name: search-sires
- description: Get sire offspring performance statistics by race class
  hints:
    openWorld: true
    readOnly: true
  name: get-sire-class-analysis
---

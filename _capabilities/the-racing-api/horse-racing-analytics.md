---
api_specs:
- filename: the-racing-api-openapi.yml
  format: yaml
  label: racing
  slug: racing
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/the-racing-api/refs/heads/main/openapi/the-racing-api-openapi.yml
categories: []
consumed_apis:
- racing
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
- get historical results for a specific horse
- search for a sire by name for breeding analysis
- today's and future race entry cards
- get free-tier racecards for basic race information
- search owners
- get racecards for today or tomorrow
- list results
- search for horses by name
- analytics
- get todays results
- get historical training results for a trainer
- get trainer results
- horse racing
- get historical race results filtered by date, region, course, or race type
- get all race results from today
- get horse results
- search jockeys
- historical race results
- search for trainers by name
- individual horse form and history
- get racecards for major featured races
- list all racing courses
- statistics
- search for a jockey by name
- get jockey performance statistics broken down by course
- horse search and form data
- search for a trainer by name
- get jockey results
- list regions
- search for jockeys by name
- sports
- racing courses and regions
- get big race cards
- list racecards
- betting
- get jockey course analysis
- trainer search and statistics
- list all available racing courses with ids and regions
- get sire class analysis
- get sire offspring performance statistics by race class
- search for a horse owner by name
- search sires
- list courses
- get free racecards
- get historical race results with filters
- get today's or tomorrow's race cards with runners, odds, and form
- get full historical race results for a specific horse
- get historical riding results for a jockey
- list all racing regions with region codes
- search trainers
- jockey search and statistics
- search horses
- search for a horse by name to find its id for detailed form queries
- racecards
slug: horse-racing-analytics
source_filename: horse-racing-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"The Racing API Horse Racing Analytics\"\n  description: \"Unified workflow for horse racing research, form analysis, and racecard review. Combines racecards, results, horse form, jockey and trainer statistics for racing analysts and application developers.\"\n  tags:\n    - Horse Racing\n    - Sports\n    - Analytics\n    - Racecards\n    - Statistics\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      RACING_API_USERNAME: RACING_API_USERNAME\n      RACING_API_PASSWORD: RACING_API_PASSWORD\n\ncapability:\n  consumes:\n    - import: racing\n      location: ./shared/the-racing-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: racing-analytics-api\n      description: \"Unified REST API for horse racing analytics, form research, and racecard review.\"\n      resources:\n        - path: /v1/racecards\n          name: racecards\n          description: \"Today's\
  \ and future race entry cards\"\n          operations:\n            - method: GET\n              name: list-racecards\n              description: \"Get racecards for today or tomorrow\"\n              call: \"racing.get-standard-racecards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/results\n          name: results\n          description: \"Historical race results\"\n          operations:\n            - method: GET\n              name: list-results\n              description: \"Get historical race results with filters\"\n              call: \"racing.get-results\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/courses\n          name: courses\n          description: \"Racing courses and regions\"\n          operations:\n            - method: GET\n              name: list-courses\n              description: \"List all racing courses\"\n \
  \             call: \"racing.get-courses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/horses\n          name: horses\n          description: \"Horse search and form data\"\n          operations:\n            - method: GET\n              name: search-horses\n              description: \"Search for horses by name\"\n              call: \"racing.search-horses\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/horses/{id}\n          name: horse-detail\n          description: \"Individual horse form and history\"\n          operations:\n            - method: GET\n              name: get-horse-results\n              description: \"Get historical results for a specific horse\"\n              call: \"racing.get-horse-results\"\n              with:\n                horse_id: \"rest.id\"\n \
  \             outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jockeys\n          name: jockeys\n          description: \"Jockey search and statistics\"\n          operations:\n            - method: GET\n              name: search-jockeys\n              description: \"Search for jockeys by name\"\n              call: \"racing.search-jockeys\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/trainers\n          name: trainers\n          description: \"Trainer search and statistics\"\n          operations:\n            - method: GET\n              name: search-trainers\n              description: \"Search for trainers by name\"\n              call: \"racing.search-trainers\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n      \
  \            mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: racing-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted horse racing research and form analysis.\"\n      tools:\n        - name: list-racecards\n          description: \"Get today's or tomorrow's race cards with runners, odds, and form\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.get-standard-racecards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-free-racecards\n          description: \"Get free-tier racecards for basic race information\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.get-free-racecards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-big-race-cards\n          description: \"Get racecards for major featured races\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.get-big-race-racecards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-results\n          description: \"Get historical race results filtered by date, region, course, or race type\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.get-results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-todays-results\n          description: \"Get all race results from today\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.get-todays-results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-courses\n          description: \"List all available racing courses with IDs and regions\"\n          hints:\n          \
  \  readOnly: true\n            openWorld: true\n          call: \"racing.get-courses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-regions\n          description: \"List all racing regions with region codes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.get-regions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-horses\n          description: \"Search for a horse by name to find its ID for detailed form queries\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.search-horses\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-horse-results\n          description: \"Get full historical race results for a specific horse\"\n          hints:\n  \
  \          readOnly: true\n            openWorld: true\n          call: \"racing.get-horse-results\"\n          with:\n            horse_id: \"tools.horse_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-jockeys\n          description: \"Search for a jockey by name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.search-jockeys\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-jockey-results\n          description: \"Get historical riding results for a jockey\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.get-jockey-results\"\n          with:\n            jockey_id: \"tools.jockey_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-jockey-course-analysis\n\
  \          description: \"Get jockey performance statistics broken down by course\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.get-jockey-course-analysis\"\n          with:\n            jockey_id: \"tools.jockey_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-trainers\n          description: \"Search for a trainer by name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.search-trainers\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-trainer-results\n          description: \"Get historical training results for a trainer\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.get-trainer-results\"\n          with:\n            trainer_id: \"tools.trainer_id\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-owners\n          description: \"Search for a horse owner by name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.search-owners\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-sires\n          description: \"Search for a sire by name for breeding analysis\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"racing.search-sires\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-sire-class-analysis\n          description: \"Get sire offspring performance statistics by race class\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"racing.get-sire-class-analysis\"\n          with:\n            sire_id: \"tools.sire_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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

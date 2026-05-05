---
categories: []
consumed_apis:
- strava
description: Unified capability for fitness tracking and athletic performance analysis using the Strava API. Designed for fitness app developers, coaches, and training platforms to access athlete data, workout history, performance metrics, segment leaderboards, and time-series physiological data. Combines athlete profile, activity, segment, and streaming APIs into a single workout intelligence workflow.
layout: capability
name: Strava Fitness Tracking
operations:
- description: Get the authenticated athlete's profile
  method: GET
  name: get-athlete
  path: /v1/athlete
- description: Get year-to-date and all-time activity totals
  method: GET
  name: get-stats
  path: /v1/athlete/stats
- description: Get the athlete's training zones
  method: GET
  name: get-zones
  path: /v1/athlete/zones
- description: List athlete's recent activities with date filtering
  method: GET
  name: list-activities
  path: /v1/activities
- description: Get detailed activity data
  method: GET
  name: get-activity
  path: /v1/activities/{id}
- description: Get time-series data streams for performance analysis
  method: GET
  name: get-activity-streams
  path: /v1/activities/{id}/streams
- description: Get lap split data for an activity
  method: GET
  name: get-laps
  path: /v1/activities/{id}/laps
- description: Get details about a specific segment
  method: GET
  name: get-segment
  path: /v1/segments/{id}
- description: Get leaderboard for a segment
  method: GET
  name: get-leaderboard
  path: /v1/segments/{id}/leaderboard
- description: List segments starred by the athlete
  method: GET
  name: list-starred-segments
  path: /v1/segments/starred
- description: List routes created by the athlete
  method: GET
  name: list-routes
  path: /v1/routes
- description: List athlete's club memberships
  method: GET
  name: list-clubs
  path: /v1/clubs
- description: Get details about a bike or shoe
  method: GET
  name: get-gear
  path: /v1/gear/{id}
personas: []
provider_name: Strava
provider_slug: strava
search_terms:
- get athlete stats
- get time-series data (gps track, heart rate, power, cadence, speed) for deep performance analysis
- workout activity list and creation
- athlete club memberships
- get the competitive leaderboard for a segment, optionally filtered by gender or following
- get athlete profile
- get the athlete's heart rate and power training zones
- get laps
- list activities
- get activity detail
- cycling
- get time-series data streams for performance analysis
- get the athlete's training zones
- running
- list starred segments
- get details about a bike or shoe
- get athlete zones
- get lap split data for an activity
- list athlete's club memberships
- get segment
- get lap split data to analyze pacing and consistency
- list the athlete's club memberships for social training context
- get athlete
- get stats
- get full details of a specific workout including performance metrics
- athlete activity statistics
- get gear
- strava segment details
- get the authenticated athlete's profile
- get leaderboard for a segment
- get segment details
- list the athlete's starred segments for quick access
- get year-to-date and all-time totals for rides, runs, and swims
- list athlete's workout activities, optionally filtered by date range
- list clubs
- get activity laps
- individual activity detail
- list athlete's recent activities with date filtering
- get segment leaderboard
- sports
- fitness tracking
- fitness
- get the authenticated athlete's profile including name, location, and gear
- list segments starred by the athlete
- activity data streams
- get leaderboard
- activity lap splits
- athlete's starred segments
- list routes
- get details about a specific segment
- segment competitive leaderboard
- athlete gear details
- athlete routes
- get gear details
- authenticated athlete profile and statistics
- get activity streams
- get zones
- list planned routes created by the athlete
- get detailed activity data
- list routes created by the athlete
- get usage and details for a specific bike or pair of shoes
- heart rate and power training zones
- get year-to-date and all-time activity totals
- get activity
- get details about a specific strava segment including grade and climb category
slug: fitness-tracking
source_filename: fitness-tracking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Strava Fitness Tracking\"\n  description: >-\n    Unified capability for fitness tracking and athletic performance analysis\n    using the Strava API. Designed for fitness app developers, coaches, and\n    training platforms to access athlete data, workout history, performance\n    metrics, segment leaderboards, and time-series physiological data.\n    Combines athlete profile, activity, segment, and streaming APIs into\n    a single workout intelligence workflow.\n  tags:\n    - Cycling\n    - Fitness\n    - Fitness Tracking\n    - Running\n    - Sports\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STRAVA_ACCESS_TOKEN: STRAVA_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: strava\n      location: ./shared/strava-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: strava-fitness-tracking-api\n      description: \"Unified REST API for Strava\
  \ fitness tracking and performance analysis.\"\n      resources:\n        - path: /v1/athlete\n          name: athlete-profile\n          description: \"Authenticated athlete profile and statistics\"\n          operations:\n            - method: GET\n              name: get-athlete\n              description: \"Get the authenticated athlete's profile\"\n              call: \"strava.get-logged-in-athlete\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/athlete/stats\n          name: athlete-stats\n          description: \"Athlete activity statistics\"\n          operations:\n            - method: GET\n              name: get-stats\n              description: \"Get year-to-date and all-time activity totals\"\n              call: \"strava.get-athlete-stats\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    \
  \    - path: /v1/athlete/zones\n          name: athlete-zones\n          description: \"Heart rate and power training zones\"\n          operations:\n            - method: GET\n              name: get-zones\n              description: \"Get the athlete's training zones\"\n              call: \"strava.get-logged-in-athlete-zones\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/activities\n          name: activities\n          description: \"Workout activity list and creation\"\n          operations:\n            - method: GET\n              name: list-activities\n              description: \"List athlete's recent activities with date filtering\"\n              call: \"strava.get-logged-in-athlete-activities\"\n              with:\n                before: \"rest.before\"\n                after: \"rest.after\"\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/activities/{id}\n          name: activity-detail\n          description: \"Individual activity detail\"\n          operations:\n            - method: GET\n              name: get-activity\n              description: \"Get detailed activity data\"\n              call: \"strava.get-activity-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/activities/{id}/streams\n          name: activity-streams\n          description: \"Activity data streams\"\n          operations:\n            - method: GET\n              name: get-activity-streams\n              description: \"Get time-series data streams for performance analysis\"\n              call: \"strava.get-activity-streams\"\n              with:\n                id: \"rest.id\"\n                keys: \"rest.keys\"\n       \
  \       outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/activities/{id}/laps\n          name: activity-laps\n          description: \"Activity lap splits\"\n          operations:\n            - method: GET\n              name: get-laps\n              description: \"Get lap split data for an activity\"\n              call: \"strava.get-laps-by-activity-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/segments/{id}\n          name: segment\n          description: \"Strava segment details\"\n          operations:\n            - method: GET\n              name: get-segment\n              description: \"Get details about a specific segment\"\n              call: \"strava.get-segment-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/segments/{id}/leaderboard\n          name: segment-leaderboard\n          description: \"Segment competitive leaderboard\"\n          operations:\n            - method: GET\n              name: get-leaderboard\n              description: \"Get leaderboard for a segment\"\n              call: \"strava.get-leaderboard-by-segment-id\"\n              with:\n                id: \"rest.id\"\n                gender: \"rest.gender\"\n                following: \"rest.following\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/segments/starred\n          name: starred-segments\n          description: \"Athlete's starred segments\"\n          operations:\n            - method: GET\n              name: list-starred-segments\n              description: \"List segments starred by the athlete\"\n              call: \"strava.get-logged-in-athlete-starred-segments\"\n      \
  \        outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/routes\n          name: routes\n          description: \"Athlete routes\"\n          operations:\n            - method: GET\n              name: list-routes\n              description: \"List routes created by the athlete\"\n              call: \"strava.get-routes-by-athlete-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clubs\n          name: clubs\n          description: \"Athlete club memberships\"\n          operations:\n            - method: GET\n              name: list-clubs\n              description: \"List athlete's club memberships\"\n              call: \"strava.get-logged-in-athlete-clubs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gear/{id}\n          name: gear\n          description: \"Athlete gear details\"\
  \n          operations:\n            - method: GET\n              name: get-gear\n              description: \"Get details about a bike or shoe\"\n              call: \"strava.get-gear-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: strava-fitness-tracking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted fitness coaching and training analysis.\"\n      tools:\n        - name: get-athlete-profile\n          description: \"Get the authenticated athlete's profile including name, location, and gear\"\n          hints:\n            readOnly: true\n          call: \"strava.get-logged-in-athlete\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-athlete-stats\n          description: \"Get year-to-date and all-time totals for rides, runs, and\
  \ swims\"\n          hints:\n            readOnly: true\n          call: \"strava.get-athlete-stats\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-athlete-zones\n          description: \"Get the athlete's heart rate and power training zones\"\n          hints:\n            readOnly: true\n          call: \"strava.get-logged-in-athlete-zones\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-activities\n          description: \"List athlete's workout activities, optionally filtered by date range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"strava.get-logged-in-athlete-activities\"\n          with:\n            before: \"tools.before\"\n            after: \"tools.after\"\n            page: \"tools.page\"\n            per_page: \"tools.per_page\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-activity-detail\n          description: \"Get full details of a specific workout including performance metrics\"\n          hints:\n            readOnly: true\n          call: \"strava.get-activity-by-id\"\n          with:\n            id: \"tools.id\"\n            include_all_efforts: \"tools.include_all_efforts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-activity-streams\n          description: \"Get time-series data (GPS track, heart rate, power, cadence, speed) for deep performance analysis\"\n          hints:\n            readOnly: true\n          call: \"strava.get-activity-streams\"\n          with:\n            id: \"tools.id\"\n            keys: \"tools.keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-activity-laps\n          description: \"Get lap split data to analyze\
  \ pacing and consistency\"\n          hints:\n            readOnly: true\n          call: \"strava.get-laps-by-activity-id\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-segment-details\n          description: \"Get details about a specific Strava segment including grade and climb category\"\n          hints:\n            readOnly: true\n          call: \"strava.get-segment-by-id\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-segment-leaderboard\n          description: \"Get the competitive leaderboard for a segment, optionally filtered by gender or following\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"strava.get-leaderboard-by-segment-id\"\n          with:\n            id: \"tools.id\"\n            gender: \"tools.gender\"\
  \n            following: \"tools.following\"\n            date_range: \"tools.date_range\"\n            per_page: \"tools.per_page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-starred-segments\n          description: \"List the athlete's starred segments for quick access\"\n          hints:\n            readOnly: true\n          call: \"strava.get-logged-in-athlete-starred-segments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-routes\n          description: \"List planned routes created by the athlete\"\n          hints:\n            readOnly: true\n          call: \"strava.get-routes-by-athlete-id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-clubs\n          description: \"List the athlete's club memberships for social training context\"\n          hints:\n            readOnly: true\n   \
  \       call: \"strava.get-logged-in-athlete-clubs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-gear-details\n          description: \"Get usage and details for a specific bike or pair of shoes\"\n          hints:\n            readOnly: true\n          call: \"strava.get-gear-by-id\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/strava/refs/heads/main/capabilities/fitness-tracking.yaml
tags:
- Cycling
- Fitness
- Fitness Tracking
- Running
- Sports
tools:
- description: Get the authenticated athlete's profile including name, location, and gear
  hints:
    readOnly: true
  name: get-athlete-profile
- description: Get year-to-date and all-time totals for rides, runs, and swims
  hints:
    readOnly: true
  name: get-athlete-stats
- description: Get the athlete's heart rate and power training zones
  hints:
    readOnly: true
  name: get-athlete-zones
- description: List athlete's workout activities, optionally filtered by date range
  hints:
    openWorld: true
    readOnly: true
  name: list-activities
- description: Get full details of a specific workout including performance metrics
  hints:
    readOnly: true
  name: get-activity-detail
- description: Get time-series data (GPS track, heart rate, power, cadence, speed) for deep performance analysis
  hints:
    readOnly: true
  name: get-activity-streams
- description: Get lap split data to analyze pacing and consistency
  hints:
    readOnly: true
  name: get-activity-laps
- description: Get details about a specific Strava segment including grade and climb category
  hints:
    readOnly: true
  name: get-segment-details
- description: Get the competitive leaderboard for a segment, optionally filtered by gender or following
  hints:
    openWorld: true
    readOnly: true
  name: get-segment-leaderboard
- description: List the athlete's starred segments for quick access
  hints:
    readOnly: true
  name: list-starred-segments
- description: List planned routes created by the athlete
  hints:
    readOnly: true
  name: list-routes
- description: List the athlete's club memberships for social training context
  hints:
    readOnly: true
  name: list-clubs
- description: Get usage and details for a specific bike or pair of shoes
  hints:
    readOnly: true
  name: get-gear-details
---

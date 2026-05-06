---
categories: []
consumed_apis: []
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
- get lap split data for an activity
- get usage and details for a specific bike or pair of shoes
- get gear details
- get details about a specific segment
- sports
- get gear
- get activity
- get segment details
- athlete routes
- get segment leaderboard
- list planned routes created by the athlete
- list routes created by the athlete
- list starred segments
- athlete activity statistics
- activity lap splits
- get time-series data streams for performance analysis
- get activity laps
- list the athlete's starred segments for quick access
- get laps
- get year-to-date and all-time activity totals
- get segment
- activity data streams
- segment competitive leaderboard
- athlete club memberships
- get the athlete's training zones
- get year-to-date and all-time totals for rides, runs, and swims
- get leaderboard
- list athlete's workout activities, optionally filtered by date range
- strava segment details
- list the athlete's club memberships for social training context
- get detailed activity data
- get leaderboard for a segment
- get athlete zones
- get the authenticated athlete's profile including name, location, and gear
- get full details of a specific workout including performance metrics
- get the competitive leaderboard for a segment, optionally filtered by gender or following
- get activity streams
- get details about a specific strava segment including grade and climb category
- heart rate and power training zones
- list athlete's club memberships
- get athlete stats
- list routes
- get the authenticated athlete's profile
- authenticated athlete profile and statistics
- workout activity list and creation
- individual activity detail
- fitness
- get the athlete's heart rate and power training zones
- get athlete profile
- athlete gear details
- cycling
- running
- list segments starred by the athlete
- list clubs
- get details about a bike or shoe
- fitness tracking
- list activities
- athlete's starred segments
- get activity detail
- list athlete's recent activities with date filtering
- get lap split data to analyze pacing and consistency
- get time-series data (gps track, heart rate, power, cadence, speed) for deep performance analysis
- get athlete
- get stats
- get zones
slug: fitness-tracking
source_filename: fitness-tracking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Strava Fitness Tracking\n  description: Unified capability for fitness tracking and athletic performance analysis using the Strava API. Designed for\n    fitness app developers, coaches, and training platforms to access athlete data, workout history, performance metrics,\n    segment leaderboards, and time-series physiological data. Combines athlete profile, activity, segment, and streaming APIs\n    into a single workout intelligence workflow.\n  tags:\n  - Cycling\n  - Fitness\n  - Fitness Tracking\n  - Running\n  - Sports\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STRAVA_ACCESS_TOKEN: STRAVA_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: strava\n    baseUri: https://www.strava.com/api/v3\n    description: Strava API v3\n    authentication:\n      type: bearer\n      token: '{{STRAVA_ACCESS_TOKEN}}'\n    resources:\n    - name: athlete\n      path: /athlete\n   \
  \   description: Authenticated athlete profile\n      operations:\n      - name: get-logged-in-athlete\n        method: GET\n        description: Get the authenticated athlete's profile\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: athlete-stats\n      path: /athletes/{id}/stats\n      description: Athlete statistics\n      operations:\n      - name: get-athlete-stats\n        method: GET\n        description: Get year-to-date and all-time activity statistics\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The athlete's identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: athlete-zones\n      path: /athlete/zones\n      description: Athlete heart rate and power zones\n      operations:\n\
  \      - name: get-logged-in-athlete-zones\n        method: GET\n        description: Get the athlete's heart rate and power zones\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: athlete-activities\n      path: /athlete/activities\n      description: Athlete activity list\n      operations:\n      - name: get-logged-in-athlete-activities\n        method: GET\n        description: List the authenticated athlete's activities\n        inputParameters:\n        - name: before\n          in: query\n          type: integer\n          required: false\n          description: Unix timestamp to filter activities before\n        - name: after\n          in: query\n          type: integer\n          required: false\n          description: Unix timestamp to filter activities after\n        - name: page\n          in: query\n          type: integer\n          required: false\n   \
  \       description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page (max 200)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activity\n      path: /activities/{id}\n      description: Individual activity operations\n      operations:\n      - name: get-activity-by-id\n        method: GET\n        description: Get a specific activity by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The activity identifier\n        - name: include_all_efforts\n          in: query\n          type: boolean\n          required: false\n          description: Include all segment efforts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ activity-streams\n      path: /activities/{id}/streams\n      description: Activity time-series data streams\n      operations:\n      - name: get-activity-streams\n        method: GET\n        description: Get time-series data streams for an activity\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The activity identifier\n        - name: keys\n          in: query\n          type: array\n          required: true\n          description: Stream types (time, latlng, distance, altitude, heartrate, cadence, watts, velocity_smooth, grade_smooth)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activity-laps\n      path: /activities/{id}/laps\n      description: Activity lap data\n      operations:\n      - name: get-laps-by-activity-id\n        method: GET\n        description: Get lap splits for an activity\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The activity identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: segment\n      path: /segments/{id}\n      description: Individual segment data\n      operations:\n      - name: get-segment-by-id\n        method: GET\n        description: Get a specific segment by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The segment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: segment-leaderboard\n      path: /segments/{id}/leaderboard\n      description: Segment leaderboard\n      operations:\n      - name: get-leaderboard-by-segment-id\n        method: GET\n\
  \        description: Get the leaderboard for a segment\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The segment identifier\n        - name: gender\n          in: query\n          type: string\n          required: false\n          description: Filter by gender (M or F)\n        - name: following\n          in: query\n          type: boolean\n          required: false\n          description: Limit to followed athletes\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: starred-segments\n      path: /segments/starred\n      description: Athlete's\
  \ starred segments\n      operations:\n      - name: get-logged-in-athlete-starred-segments\n        method: GET\n        description: List the authenticated athlete's starred segments\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: athlete-routes\n      path: /athlete/routes\n      description: Athlete routes\n      operations:\n      - name: get-routes-by-athlete-id\n        method: GET\n        description: List the athlete's routes\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name:\
  \ per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: athlete-clubs\n      path: /athlete/clubs\n      description: Athlete club memberships\n      operations:\n      - name: get-logged-in-athlete-clubs\n        method: GET\n        description: List the athlete's club memberships\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gear\n      path: /gear/{id}\n      description: Athlete gear details\n  \
  \    operations:\n      - name: get-gear-by-id\n        method: GET\n        description: Get an equipment item by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The gear identifier (e.g., b1234567)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: strava-fitness-tracking-api\n    description: Unified REST API for Strava fitness tracking and performance analysis.\n    resources:\n    - path: /v1/athlete\n      name: athlete-profile\n      description: Authenticated athlete profile and statistics\n      operations:\n      - method: GET\n        name: get-athlete\n        description: Get the authenticated athlete's profile\n        call: strava.get-logged-in-athlete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/athlete/stats\n\
  \      name: athlete-stats\n      description: Athlete activity statistics\n      operations:\n      - method: GET\n        name: get-stats\n        description: Get year-to-date and all-time activity totals\n        call: strava.get-athlete-stats\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/athlete/zones\n      name: athlete-zones\n      description: Heart rate and power training zones\n      operations:\n      - method: GET\n        name: get-zones\n        description: Get the athlete's training zones\n        call: strava.get-logged-in-athlete-zones\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/activities\n      name: activities\n      description: Workout activity list and creation\n      operations:\n      - method: GET\n        name: list-activities\n        description: List athlete's recent activities with date filtering\n        call: strava.get-logged-in-athlete-activities\n\
  \        with:\n          before: rest.before\n          after: rest.after\n          page: rest.page\n          per_page: rest.per_page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/activities/{id}\n      name: activity-detail\n      description: Individual activity detail\n      operations:\n      - method: GET\n        name: get-activity\n        description: Get detailed activity data\n        call: strava.get-activity-by-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/activities/{id}/streams\n      name: activity-streams\n      description: Activity data streams\n      operations:\n      - method: GET\n        name: get-activity-streams\n        description: Get time-series data streams for performance analysis\n        call: strava.get-activity-streams\n        with:\n          id: rest.id\n          keys: rest.keys\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /v1/activities/{id}/laps\n      name: activity-laps\n      description: Activity lap splits\n      operations:\n      - method: GET\n        name: get-laps\n        description: Get lap split data for an activity\n        call: strava.get-laps-by-activity-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/segments/{id}\n      name: segment\n      description: Strava segment details\n      operations:\n      - method: GET\n        name: get-segment\n        description: Get details about a specific segment\n        call: strava.get-segment-by-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/segments/{id}/leaderboard\n      name: segment-leaderboard\n      description: Segment competitive leaderboard\n      operations:\n      - method: GET\n        name: get-leaderboard\n    \
  \    description: Get leaderboard for a segment\n        call: strava.get-leaderboard-by-segment-id\n        with:\n          id: rest.id\n          gender: rest.gender\n          following: rest.following\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/segments/starred\n      name: starred-segments\n      description: Athlete's starred segments\n      operations:\n      - method: GET\n        name: list-starred-segments\n        description: List segments starred by the athlete\n        call: strava.get-logged-in-athlete-starred-segments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/routes\n      name: routes\n      description: Athlete routes\n      operations:\n      - method: GET\n        name: list-routes\n        description: List routes created by the athlete\n        call: strava.get-routes-by-athlete-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clubs\n\
  \      name: clubs\n      description: Athlete club memberships\n      operations:\n      - method: GET\n        name: list-clubs\n        description: List athlete's club memberships\n        call: strava.get-logged-in-athlete-clubs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gear/{id}\n      name: gear\n      description: Athlete gear details\n      operations:\n      - method: GET\n        name: get-gear\n        description: Get details about a bike or shoe\n        call: strava.get-gear-by-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: strava-fitness-tracking-mcp\n    transport: http\n    description: MCP server for AI-assisted fitness coaching and training analysis.\n    tools:\n    - name: get-athlete-profile\n      description: Get the authenticated athlete's profile including name, location, and gear\n      hints:\n \
  \       readOnly: true\n      call: strava.get-logged-in-athlete\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-athlete-stats\n      description: Get year-to-date and all-time totals for rides, runs, and swims\n      hints:\n        readOnly: true\n      call: strava.get-athlete-stats\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-athlete-zones\n      description: Get the athlete's heart rate and power training zones\n      hints:\n        readOnly: true\n      call: strava.get-logged-in-athlete-zones\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-activities\n      description: List athlete's workout activities, optionally filtered by date range\n      hints:\n        readOnly: true\n        openWorld: true\n      call: strava.get-logged-in-athlete-activities\n      with:\n        before: tools.before\n        after: tools.after\n       \
  \ page: tools.page\n        per_page: tools.per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-activity-detail\n      description: Get full details of a specific workout including performance metrics\n      hints:\n        readOnly: true\n      call: strava.get-activity-by-id\n      with:\n        id: tools.id\n        include_all_efforts: tools.include_all_efforts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-activity-streams\n      description: Get time-series data (GPS track, heart rate, power, cadence, speed) for deep performance analysis\n      hints:\n        readOnly: true\n      call: strava.get-activity-streams\n      with:\n        id: tools.id\n        keys: tools.keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-activity-laps\n      description: Get lap split data to analyze pacing and consistency\n      hints:\n        readOnly: true\n      call: strava.get-laps-by-activity-id\n\
  \      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-segment-details\n      description: Get details about a specific Strava segment including grade and climb category\n      hints:\n        readOnly: true\n      call: strava.get-segment-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-segment-leaderboard\n      description: Get the competitive leaderboard for a segment, optionally filtered by gender or following\n      hints:\n        readOnly: true\n        openWorld: true\n      call: strava.get-leaderboard-by-segment-id\n      with:\n        id: tools.id\n        gender: tools.gender\n        following: tools.following\n        date_range: tools.date_range\n        per_page: tools.per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-starred-segments\n      description: List the athlete's starred segments\
  \ for quick access\n      hints:\n        readOnly: true\n      call: strava.get-logged-in-athlete-starred-segments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-routes\n      description: List planned routes created by the athlete\n      hints:\n        readOnly: true\n      call: strava.get-routes-by-athlete-id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-clubs\n      description: List the athlete's club memberships for social training context\n      hints:\n        readOnly: true\n      call: strava.get-logged-in-athlete-clubs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-gear-details\n      description: Get usage and details for a specific bike or pair of shoes\n      hints:\n        readOnly: true\n      call: strava.get-gear-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

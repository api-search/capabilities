---
categories: []
consumed_apis: []
description: Comprehensive race event management capability for RunSignup. Enables race directors, timing companies, and integration partners to discover races, manage participant registrations, retrieve bib/chip assignments, submit and retrieve race results, manage divisions and teams, and access fundraising data. Covers the full lifecycle from race discovery through results publication.
layout: capability
name: RunSignup Race Event Management
operations:
- description: Search and list upcoming races
  method: GET
  name: get-races
  path: /v1/races
- description: Get full race information including events
  method: GET
  name: get-race
  path: /v1/races/{race_id}
- description: List registered participants
  method: GET
  name: get-participants
  path: /v1/races/{race_id}/participants
- description: Get bib number and chip assignments
  method: GET
  name: get-bib-chip
  path: /v1/races/{race_id}/bib-chip
- description: Get race results
  method: GET
  name: get-results
  path: /v1/races/{race_id}/results
- description: Submit race results
  method: POST
  name: post-results
  path: /v1/races/{race_id}/results
- description: Get race divisions
  method: GET
  name: get-divisions
  path: /v1/races/{race_id}/divisions
- description: Get registered teams
  method: GET
  name: get-teams
  path: /v1/races/{race_id}/teams
- description: Get race donations
  method: GET
  name: get-donations
  path: /v1/races/{race_id}/donations
personas: []
provider_name: RunSignup
provider_slug: runsignup
search_terms:
- get participants
- post results
- get donation and fundraising data for a race
- get donations
- timing
- list registered participants
- sports
- get divisions
- team registration management
- get race
- race registration
- get teams registered for a race event
- individual race details
- race results retrieval and submission
- search races
- get bib chip
- get comprehensive details about a specific race including all events, registration status, and settings
- get races
- get bib number and chip assignments
- bib and chip assignment data
- get race divisions
- submit race results
- participant registration management
- get race results
- get teams
- get race donations
- retrieve registered participants for a race, optionally filtered by event
- get bib number and rfid chip assignments for timing operations
- get registered teams
- event management
- get age and gender divisions configured for race results scoring
- get race details
- fitness
- race discovery and search
- get race participants
- running
- fundraising
- submit official race results with finish times and placements for participants
- search and discover upcoming races on runsignup by name, location, or state
- get bib chip assignments
- get race teams
- search and list upcoming races
- get results
- get full race information including events
- results
- runsignup
- retrieve official race results including finish times and placements
- fundraising and donation data
- age and gender division management
slug: race-event-management
source_filename: race-event-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: RunSignup Race Event Management\n  description: Comprehensive race event management capability for RunSignup. Enables race directors, timing companies, and\n    integration partners to discover races, manage participant registrations, retrieve bib/chip assignments, submit and retrieve\n    race results, manage divisions and teams, and access fundraising data. Covers the full lifecycle from race discovery through\n    results publication.\n  tags:\n  - RunSignup\n  - Race Registration\n  - Event Management\n  - Running\n  - Sports\n  - Timing\n  - Results\n  - Fundraising\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RUNSIGNUP_API_KEY: RUNSIGNUP_API_KEY\n    RUNSIGNUP_API_SECRET: RUNSIGNUP_API_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: runsignup\n    baseUri: https://runsignup.com/Rest\n    description: RunSignup REST API for race event management\n    authentication:\n\
  \      type: apikey\n      key: api_key\n      value: '{{env.RUNSIGNUP_API_KEY}}'\n      placement: query\n    resources:\n    - name: races\n      path: /races\n      description: Search and list races\n      operations:\n      - name: get-races\n        method: GET\n        description: List upcoming races\n        inputParameters:\n        - name: api_secret\n          in: query\n          type: string\n          required: true\n          description: API secret\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format (json/xml)\n        - name: search_term\n          in: query\n          type: string\n          required: false\n          description: Search by race name\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by state\n        - name: results_per_page\n          in: query\n          type: integer\n          required: false\n\
  \          description: Results per page (max 1000)\n        - name: events\n          in: query\n          type: string\n          required: false\n          description: Include events (T/F)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: race\n      path: /race/{race_id}\n      description: Get detailed race information\n      operations:\n      - name: get-race\n        method: GET\n        description: Get race details by ID\n        inputParameters:\n        - name: race_id\n          in: path\n          type: integer\n          required: true\n          description: Race ID\n        - name: api_secret\n          in: query\n          type: string\n          required: true\n          description: API secret\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: participants\n      path: /race/{race_id}/participants\n      description: Manage race participants\n      operations:\n      - name: get-participants\n        method: GET\n        description: Get registered participants for a race\n        inputParameters:\n        - name: race_id\n          in: path\n          type: integer\n          required: true\n          description: Race ID\n        - name: api_secret\n          in: query\n          type: string\n          required: true\n          description: API secret\n        - name: event_id\n          in: query\n          type: integer\n          required: false\n          description: Filter by event ID\n        - name: results_per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: bib-chip\n      path: /race/{race_id}/get-bib-chip\n      description: Get bib and chip assignments\n      operations:\n      - name: get-bib-chip\n        method: GET\n        description: Get bib number and chip assignments for a race event\n        inputParameters:\n        - name: race_id\n          in: path\n          type: integer\n          required: true\n          description: Race ID\n        - name: api_secret\n          in: query\n          type: string\n          required: true\n          description: API secret\n        - name: event_id\n          in: query\n          type: integer\n          required: false\n          description: Event ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results\n      path: /race/{race_id}/results/get-results\n      description: Retrieve race results\n      operations:\n      - name: get-results\n        method: GET\n\
  \        description: Get all results for a race\n        inputParameters:\n        - name: race_id\n          in: path\n          type: integer\n          required: true\n          description: Race ID\n        - name: api_secret\n          in: query\n          type: string\n          required: true\n          description: API secret\n        - name: event_id\n          in: query\n          type: integer\n          required: false\n          description: Filter by event ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-results\n      path: /race/{race_id}/results/full-results\n      description: Submit race results\n      operations:\n      - name: post-full-results\n        method: POST\n        description: Submit complete race results for an event\n        inputParameters:\n        - name: race_id\n          in: path\n          type: integer\n          required: true\n          description:\
  \ Race ID\n        body:\n          type: json\n          data:\n            api_key: '{{env.RUNSIGNUP_API_KEY}}'\n            api_secret: '{{env.RUNSIGNUP_API_SECRET}}'\n            event_id: '{{tools.event_id}}'\n            results: '{{tools.results}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: divisions\n      path: /race/{race_id}/divisions/divisions\n      description: Race age group divisions\n      operations:\n      - name: get-divisions\n        method: GET\n        description: Get race divisions\n        inputParameters:\n        - name: race_id\n          in: path\n          type: integer\n          required: true\n          description: Race ID\n        - name: api_secret\n          in: query\n          type: string\n          required: true\n          description: API secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: teams\n      path: /race/{race_id}/teams\n      description: Race team management\n      operations:\n      - name: get-teams\n        method: GET\n        description: Get teams registered for a race\n        inputParameters:\n        - name: race_id\n          in: path\n          type: integer\n          required: true\n          description: Race ID\n        - name: api_secret\n          in: query\n          type: string\n          required: true\n          description: API secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: donations\n      path: /race/{race_id}/donations/list\n      description: Race donation data\n      operations:\n      - name: get-donations\n        method: GET\n        description: Get donations for a race\n        inputParameters:\n        - name: race_id\n          in: path\n          type: integer\n          required: true\n    \
  \      description: Race ID\n        - name: api_secret\n          in: query\n          type: string\n          required: true\n          description: API secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: race-event-api\n    description: Unified REST API for RunSignup race event management.\n    resources:\n    - path: /v1/races\n      name: races\n      description: Race discovery and search\n      operations:\n      - method: GET\n        name: get-races\n        description: Search and list upcoming races\n        call: runsignup.get-races\n        with:\n          search_term: rest.search_term\n          state: rest.state\n          results_per_page: rest.results_per_page\n          events: rest.events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/races/{race_id}\n      name: race\n      description:\
  \ Individual race details\n      operations:\n      - method: GET\n        name: get-race\n        description: Get full race information including events\n        call: runsignup.get-race\n        with:\n          race_id: rest.race_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/races/{race_id}/participants\n      name: participants\n      description: Participant registration management\n      operations:\n      - method: GET\n        name: get-participants\n        description: List registered participants\n        call: runsignup.get-participants\n        with:\n          race_id: rest.race_id\n          event_id: rest.event_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/races/{race_id}/bib-chip\n      name: bib-chip\n      description: Bib and chip assignment data\n      operations:\n      - method: GET\n        name: get-bib-chip\n        description: Get bib number and chip assignments\n\
  \        call: runsignup.get-bib-chip\n        with:\n          race_id: rest.race_id\n          event_id: rest.event_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/races/{race_id}/results\n      name: results\n      description: Race results retrieval and submission\n      operations:\n      - method: GET\n        name: get-results\n        description: Get race results\n        call: runsignup.get-results\n        with:\n          race_id: rest.race_id\n          event_id: rest.event_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: post-results\n        description: Submit race results\n        call: runsignup.post-full-results\n        with:\n          race_id: rest.race_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/races/{race_id}/divisions\n      name: divisions\n      description: Age and gender division management\n     \
  \ operations:\n      - method: GET\n        name: get-divisions\n        description: Get race divisions\n        call: runsignup.get-divisions\n        with:\n          race_id: rest.race_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/races/{race_id}/teams\n      name: teams\n      description: Team registration management\n      operations:\n      - method: GET\n        name: get-teams\n        description: Get registered teams\n        call: runsignup.get-teams\n        with:\n          race_id: rest.race_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/races/{race_id}/donations\n      name: donations\n      description: Fundraising and donation data\n      operations:\n      - method: GET\n        name: get-donations\n        description: Get race donations\n        call: runsignup.get-donations\n        with:\n          race_id: rest.race_id\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: race-event-mcp\n    transport: http\n    description: MCP server for AI-assisted race event management and results processing.\n    tools:\n    - name: search-races\n      description: Search and discover upcoming races on RunSignup by name, location, or state\n      hints:\n        readOnly: true\n        openWorld: true\n      call: runsignup.get-races\n      with:\n        search_term: tools.search_term\n        state: tools.state\n        results_per_page: tools.results_per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-race-details\n      description: Get comprehensive details about a specific race including all events, registration status, and settings\n      hints:\n        readOnly: true\n        openWorld: true\n      call: runsignup.get-race\n      with:\n        race_id: tools.race_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-race-participants\n      description: Retrieve registered participants for a race, optionally filtered by event\n      hints:\n        readOnly: true\n        openWorld: false\n      call: runsignup.get-participants\n      with:\n        race_id: tools.race_id\n        event_id: tools.event_id\n        results_per_page: tools.results_per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bib-chip-assignments\n      description: Get bib number and RFID chip assignments for timing operations\n      hints:\n        readOnly: true\n        openWorld: false\n      call: runsignup.get-bib-chip\n      with:\n        race_id: tools.race_id\n        event_id: tools.event_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-race-results\n      description: Retrieve official race results including finish times and placements\n      hints:\n        readOnly: true\n        openWorld: true\n      call: runsignup.get-results\n\
  \      with:\n        race_id: tools.race_id\n        event_id: tools.event_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-race-results\n      description: Submit official race results with finish times and placements for participants\n      hints:\n        readOnly: false\n        openWorld: false\n      call: runsignup.post-full-results\n      with:\n        race_id: tools.race_id\n        event_id: tools.event_id\n        results: tools.results\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-race-divisions\n      description: Get age and gender divisions configured for race results scoring\n      hints:\n        readOnly: true\n        openWorld: true\n      call: runsignup.get-divisions\n      with:\n        race_id: tools.race_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-race-teams\n      description: Get teams registered for a race event\n      hints:\n    \
  \    readOnly: true\n        openWorld: true\n      call: runsignup.get-teams\n      with:\n        race_id: tools.race_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-race-donations\n      description: Get donation and fundraising data for a race\n      hints:\n        readOnly: true\n        openWorld: false\n      call: runsignup.get-donations\n      with:\n        race_id: tools.race_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/runsignup/refs/heads/main/capabilities/race-event-management.yaml
tags:
- RunSignup
- Race Registration
- Event Management
- Running
- Sports
- Timing
- Results
- Fundraising
tools:
- description: Search and discover upcoming races on RunSignup by name, location, or state
  hints:
    openWorld: true
    readOnly: true
  name: search-races
- description: Get comprehensive details about a specific race including all events, registration status, and settings
  hints:
    openWorld: true
    readOnly: true
  name: get-race-details
- description: Retrieve registered participants for a race, optionally filtered by event
  hints:
    openWorld: false
    readOnly: true
  name: get-race-participants
- description: Get bib number and RFID chip assignments for timing operations
  hints:
    openWorld: false
    readOnly: true
  name: get-bib-chip-assignments
- description: Retrieve official race results including finish times and placements
  hints:
    openWorld: true
    readOnly: true
  name: get-race-results
- description: Submit official race results with finish times and placements for participants
  hints:
    openWorld: false
    readOnly: false
  name: submit-race-results
- description: Get age and gender divisions configured for race results scoring
  hints:
    openWorld: true
    readOnly: true
  name: get-race-divisions
- description: Get teams registered for a race event
  hints:
    openWorld: true
    readOnly: true
  name: get-race-teams
- description: Get donation and fundraising data for a race
  hints:
    openWorld: false
    readOnly: true
  name: get-race-donations
---

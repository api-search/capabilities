---
categories: []
consumed_apis: []
description: Unified capability for space situational awareness (SSA) operations, combining orbital element tracking, satellite catalog queries, conjunction monitoring, and reentry prediction. Supports satellite operators, aerospace researchers, and space traffic management teams.
layout: capability
name: US Space Command Space Situational Awareness
operations:
- description: Search tracked space objects by name, NORAD ID, or country
  method: GET
  name: search-satellites
  path: /v1/satellites
- description: Search the satellite catalog
  method: GET
  name: search-catalog
  path: /v1/catalog
- description: List conjunction data messages by collision probability
  method: GET
  name: list-conjunctions
  path: /v1/conjunctions
- description: List space objects that have reentered the atmosphere
  method: GET
  name: list-reentries
  path: /v1/reentries
- description: Get object counts by country and type
  method: GET
  name: get-catalog-stats
  path: /v1/catalog/stats
personas: []
provider_name: US Space Command
provider_slug: us-space-comman
search_terms:
- space situational awareness
- get catalog stats
- collision warnings and conjunction data
- satellite catalog metadata
- get active conjunction data messages (cdms) — collision warnings for close approaches between tracked space objects.
- get satellite decay and reentry predictions for space objects
- search catalog
- search debris objects
- search tracked space objects by name, norad id, or country
- get conjunction warnings
- space objects with current orbital elements
- look up satellite catalog metadata for a specific norad catalog id
- get space catalog statistics
- satellite decay and reentry data
- orbital data
- get a summary count of all tracked space objects (payloads, rocket bodies, debris, unknown) organized by country of origin.
- list reentries
- list conjunctions
- get satellite catalog entry
- list space objects that have reentered the atmosphere
- collision avoidance
- list conjunction data messages by collision probability
- satellite tracking
- federal government
- search satellites
- search for space debris objects tracked by usspacecom
- get object counts by country and type
- space
- search for tracked space objects by name, norad catalog id, country code, or orbital epoch. returns current orbital elements including tle data.
- get reentry predictions
- search the satellite catalog
- space object catalog statistics
- open data
slug: space-situational-awareness
source_filename: space-situational-awareness.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: US Space Command Space Situational Awareness\n  description: Unified capability for space situational awareness (SSA) operations, combining orbital element tracking, satellite\n    catalog queries, conjunction monitoring, and reentry prediction. Supports satellite operators, aerospace researchers,\n    and space traffic management teams.\n  tags:\n  - Space Situational Awareness\n  - Orbital Data\n  - Satellite Tracking\n  - Federal Government\n  - Collision Avoidance\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPACE_TRACK_USERNAME: SPACE_TRACK_USERNAME\n    SPACE_TRACK_PASSWORD: SPACE_TRACK_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: space-track\n    baseUri: https://www.space-track.org\n    description: Space-Track.org REST API for space situational awareness data.\n    authentication:\n      type: basic\n      username: '{{SPACE_TRACK_USERNAME}}'\n      password:\
  \ '{{SPACE_TRACK_PASSWORD}}'\n    resources:\n    - name: general-perturbations\n      path: /basicspacedata/query/class/gp/format/json\n      description: Current orbital element sets\n      operations:\n      - name: list-current-gp\n        method: GET\n        description: Get current orbital elements for tracked space objects\n        inputParameters:\n        - name: NORAD_CAT_ID\n          in: query\n          type: string\n          required: false\n          description: NORAD catalog number\n        - name: OBJECT_NAME\n          in: query\n          type: string\n          required: false\n          description: Object name (supports ~~ wildcard)\n        - name: EPOCH\n          in: query\n          type: string\n          required: false\n          description: Epoch filter (e.g., >now-30)\n        - name: DECAY_DATE\n          in: query\n          type: string\n          required: false\n          description: Decay date filter (null-val for active)\n        - name: COUNTRY_CODE\n\
  \          in: query\n          type: string\n          required: false\n          description: Country code filter\n        - name: orderby\n          in: query\n          type: string\n          required: false\n          description: Sort order\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: satellite-catalog\n      path: /basicspacedata/query/class/satcat/format/json\n      description: Satellite catalog metadata\n      operations:\n      - name: list-satcat\n        method: GET\n        description: Query satellite catalog\n        inputParameters:\n        - name: NORAD_CAT_ID\n          in: query\n          type: string\n          required: false\n          description: NORAD catalog number\n        - name: OBJECT_TYPE\n          in: query\n          type: string\n\
  \          required: false\n          description: Object type (PAYLOAD, ROCKET BODY, DEBRIS, UNKNOWN)\n        - name: COUNTRY_CODE\n          in: query\n          type: string\n          required: false\n          description: Country code\n        - name: DECAY_DATE\n          in: query\n          type: string\n          required: false\n          description: Decay date (null-val for active)\n        - name: orderby\n          in: query\n          type: string\n          required: false\n          description: Sort order\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: conjunction-data\n      path: /basicspacedata/query/class/cdm_public/format/json\n      description: Conjunction data messages (collision warnings)\n      operations:\n      - name: list-conjunctions\n\
  \        method: GET\n        description: List conjunction data messages by probability of collision\n        inputParameters:\n        - name: SAT_1_ID\n          in: query\n          type: string\n          required: false\n          description: Primary object NORAD ID\n        - name: SAT_2_ID\n          in: query\n          type: string\n          required: false\n          description: Secondary object NORAD ID\n        - name: PC\n          in: query\n          type: string\n          required: false\n          description: Collision probability filter\n        - name: orderby\n          in: query\n          type: string\n          required: false\n          description: Sort order (e.g., PC desc)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: decay-data\n \
  \     path: /basicspacedata/query/class/decay/format/json\n      description: Satellite decay and reentry data\n      operations:\n      - name: list-decays\n        method: GET\n        description: List satellite decay and reentry records\n        inputParameters:\n        - name: NORAD_CAT_ID\n          in: query\n          type: string\n          required: false\n          description: NORAD catalog number\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: boxscore\n      path: /basicspacedata/query/class/boxscore/format/json\n      description: Space object counts by country\n      operations:\n      - name: get-boxscore\n        method: GET\n        description: Get space object counts by country and type\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ssa-api\n    description: Unified REST API for space situational awareness data.\n    resources:\n    - path: /v1/satellites\n      name: satellites\n      description: Space objects with current orbital elements\n      operations:\n      - method: GET\n        name: search-satellites\n        description: Search tracked space objects by name, NORAD ID, or country\n        call: space-track.list-current-gp\n        with:\n          NORAD_CAT_ID: rest.norad_cat_id\n          OBJECT_NAME: rest.object_name\n          COUNTRY_CODE: rest.country_code\n          EPOCH: rest.epoch\n          limit: rest.limit\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/catalog\n      name: catalog\n      description: Satellite catalog metadata\n      operations:\n      - method: GET\n        name: search-catalog\n        description: Search\
  \ the satellite catalog\n        call: space-track.list-satcat\n        with:\n          NORAD_CAT_ID: rest.norad_cat_id\n          OBJECT_TYPE: rest.object_type\n          COUNTRY_CODE: rest.country_code\n          DECAY_DATE: rest.decay_date\n          limit: rest.limit\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/conjunctions\n      name: conjunctions\n      description: Collision warnings and conjunction data\n      operations:\n      - method: GET\n        name: list-conjunctions\n        description: List conjunction data messages by collision probability\n        call: space-track.list-conjunctions\n        with:\n          SAT_1_ID: rest.sat_1_id\n          PC: rest.pc_threshold\n          orderby: PC desc\n          limit: rest.limit\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/reentries\n      name: reentries\n      description: Satellite decay and reentry data\n      operations:\n     \
  \ - method: GET\n        name: list-reentries\n        description: List space objects that have reentered the atmosphere\n        call: space-track.list-decays\n        with:\n          NORAD_CAT_ID: rest.norad_cat_id\n          limit: rest.limit\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/catalog/stats\n      name: catalog-stats\n      description: Space object catalog statistics\n      operations:\n      - method: GET\n        name: get-catalog-stats\n        description: Get object counts by country and type\n        call: space-track.get-boxscore\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ssa-mcp\n    transport: http\n    description: MCP server for AI-assisted space situational awareness.\n    tools:\n    - name: search-satellites\n      description: Search for tracked space objects by name, NORAD catalog ID, country code, or orbital epoch. Returns current\n\
  \        orbital elements including TLE data.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: space-track.list-current-gp\n      with:\n        NORAD_CAT_ID: tools.norad_cat_id\n        OBJECT_NAME: tools.object_name\n        COUNTRY_CODE: tools.country_code\n        EPOCH: tools.epoch\n        DECAY_DATE: null-val\n        limit: tools.limit\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-satellite-catalog-entry\n      description: Look up satellite catalog metadata for a specific NORAD catalog ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: space-track.list-satcat\n      with:\n        NORAD_CAT_ID: tools.norad_cat_id\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: search-debris-objects\n      description: Search for space debris objects tracked by USSPACECOM\n      hints:\n        readOnly: true\n        openWorld: true\n      call: space-track.list-satcat\n\
  \      with:\n        OBJECT_TYPE: DEBRIS\n        COUNTRY_CODE: tools.country_code\n        DECAY_DATE: null-val\n        limit: tools.limit\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-conjunction-warnings\n      description: Get active conjunction data messages (CDMs) — collision warnings for close approaches between tracked space\n        objects.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: space-track.list-conjunctions\n      with:\n        SAT_1_ID: tools.norad_cat_id\n        PC: tools.min_probability\n        orderby: PC desc\n        limit: tools.limit\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-reentry-predictions\n      description: Get satellite decay and reentry predictions for space objects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: space-track.list-decays\n      with:\n        NORAD_CAT_ID: tools.norad_cat_id\n        limit: tools.limit\n\
  \      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-space-catalog-statistics\n      description: Get a summary count of all tracked space objects (payloads, rocket bodies, debris, unknown) organized by\n        country of origin.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: space-track.get-boxscore\n      outputParameters:\n      - type: array\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-space-comman/refs/heads/main/capabilities/space-situational-awareness.yaml
tags:
- Space Situational Awareness
- Orbital Data
- Satellite Tracking
- Federal Government
- Collision Avoidance
tools:
- description: Search for tracked space objects by name, NORAD catalog ID, country code, or orbital epoch. Returns current orbital elements including TLE data.
  hints:
    openWorld: true
    readOnly: true
  name: search-satellites
- description: Look up satellite catalog metadata for a specific NORAD catalog ID
  hints:
    openWorld: false
    readOnly: true
  name: get-satellite-catalog-entry
- description: Search for space debris objects tracked by USSPACECOM
  hints:
    openWorld: true
    readOnly: true
  name: search-debris-objects
- description: Get active conjunction data messages (CDMs) — collision warnings for close approaches between tracked space objects.
  hints:
    openWorld: true
    readOnly: true
  name: get-conjunction-warnings
- description: Get satellite decay and reentry predictions for space objects
  hints:
    openWorld: true
    readOnly: true
  name: get-reentry-predictions
- description: Get a summary count of all tracked space objects (payloads, rocket bodies, debris, unknown) organized by country of origin.
  hints:
    openWorld: false
    readOnly: true
  name: get-space-catalog-statistics
---

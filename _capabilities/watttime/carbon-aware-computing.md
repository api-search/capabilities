---
categories: []
consumed_apis: []
description: Workflow capability combining WattTime's real-time, forecast, and historical emissions data to enable carbon-aware scheduling, sustainability reporting, and clean energy procurement decisions. Used by software engineers, platform teams, and sustainability analysts to reduce carbon footprint of compute workloads and measure emissions reductions.
layout: capability
name: WattTime Carbon-Aware Computing
operations:
- description: Obtain a WattTime API access token.
  method: GET
  name: login
  path: /v1/auth/login
- description: Look up the grid region for geographic coordinates.
  method: GET
  name: get-region-from-location
  path: /v1/grid/region
- description: Get all accessible grid regions and available model versions.
  method: GET
  name: get-my-access
  path: /v1/grid/regions
- description: Get real-time and forecast emissions for a grid region.
  method: GET
  name: get-forecast
  path: /v1/emissions/realtime
- description: Get historical emissions data (up to 32-day window).
  method: GET
  name: get-historical-data
  path: /v1/emissions/historical
- description: Get historical forecast data for algorithm validation.
  method: GET
  name: get-forecast-historical
  path: /v1/emissions/forecast-history
- description: Get download URL for historical emissions dataset.
  method: GET
  name: download-historical-data
  path: /v1/emissions/download
- description: Get GeoJSON boundaries for grid regions.
  method: GET
  name: get-grid-maps
  path: /v1/grid/maps
personas: []
provider_name: WattTime
provider_slug: watttime
search_terms:
- sustainability
- retrieve previously generated forecast data for a historical period. use for back-testing carbon-aware scheduling algorithms.
- download emissions dataset
- get the current real-time marginal emissions forecast for a grid region, updated every 5 minutes. use for deciding whether now is a good time to run a workload.
- get historical marginal emissions data for a grid region over a time window (max 32 days). use for reporting past emissions impact.
- carbon-aware computing
- get my access
- clean energy
- carbon
- authenticate with the watttime api.
- obtain a watttime api access token.
- real-time emissions data and short-term forecast.
- get forecast history
- find grid region
- get a download url for multi-year historical emissions data as a csv file.
- list accessible grid regions and models.
- get geojson boundaries for grid regions.
- historical emissions data for analysis and reporting.
- get grid maps
- historically generated forecasts for back-testing.
- download historical data
- authenticate with the watttime api to obtain an access token for subsequent calls.
- get region from location
- identify the grid region for a location.
- list all grid regions accessible under the current watttime subscription, with model versions.
- login
- identify the electric grid balancing authority for a geographic location by latitude and longitude.
- climate
- list accessible regions
- electricity grid
- get geojson boundaries for all accessible grid regions for map visualization.
- authenticate
- get all accessible grid regions and available model versions.
- get realtime emissions
- energy
- emissions
- get forecast
- look up the grid region for geographic coordinates.
- get forecast historical
- get historical forecast data for algorithm validation.
- watttime
- get historical emissions data (up to 32-day window).
- geojson grid region boundaries for visualization.
- download multi-year historical emissions csv data.
- get real-time and forecast emissions for a grid region.
- get download url for historical emissions dataset.
- get historical data
- get historical emissions
slug: carbon-aware-computing
source_filename: carbon-aware-computing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WattTime Carbon-Aware Computing\n  description: Workflow capability combining WattTime's real-time, forecast, and historical emissions data to enable carbon-aware\n    scheduling, sustainability reporting, and clean energy procurement decisions. Used by software engineers, platform teams,\n    and sustainability analysts to reduce carbon footprint of compute workloads and measure emissions reductions.\n  tags:\n  - Carbon-Aware Computing\n  - Emissions\n  - Sustainability\n  - Energy\n  - WattTime\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WATTTIME_USERNAME: WATTTIME_USERNAME\n    WATTTIME_PASSWORD: WATTTIME_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: watttime\n    baseUri: https://api.watttime.org/v3\n    description: WattTime Data API v3 for marginal emissions and grid data.\n    authentication:\n      type: bearer\n      token: '{{WATTTIME_TOKEN}}'\n    resources:\n\
  \    - name: authentication\n      path: /login\n      description: Obtain JWT bearer token via HTTP Basic Auth.\n      operations:\n      - name: login\n        method: GET\n        description: Authenticate and obtain a JWT access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: token\n          type: string\n          value: $.token\n    - name: account\n      path: /my-access\n      description: Account access information and available grid regions.\n      operations:\n      - name: get-my-access\n        method: GET\n        description: Get accessible grid regions and model metadata.\n        inputParameters:\n        - name: signal_type\n          in: query\n          type: string\n          required: false\n          description: Filter by signal type (co2_moer, co2_aoer, health_damage).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: grid-regions\n     \
  \ path: /region-from-loc\n      description: Identify the grid region for a geographic location.\n      operations:\n      - name: get-region-from-location\n        method: GET\n        description: Get the grid balancing authority for lat/lon coordinates.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: signal_type\n          in: query\n          type: string\n          required: false\n          description: Signal type to check region for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emissions-data\n      path: /data\n      description: Historical emissions data for a grid region.\n      operations:\n\
  \      - name: get-historical-data\n        method: GET\n        description: Get historical emissions data (up to 32-day window).\n        inputParameters:\n        - name: region\n          in: query\n          type: string\n          required: true\n          description: Grid region identifier.\n        - name: signal_type\n          in: query\n          type: string\n          required: true\n          description: Emissions signal type.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start datetime (ISO 8601 UTC).\n        - name: end\n          in: query\n          type: string\n          required: true\n          description: End datetime (ISO 8601 UTC).\n        - name: model\n          in: query\n          type: string\n          required: false\n          description: Model version date.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: forecasts\n      path: /forecast\n      description: Real-time and forecast emissions data.\n      operations:\n      - name: get-forecast\n        method: GET\n        description: Get current emissions forecast (updated every 5 minutes).\n        inputParameters:\n        - name: region\n          in: query\n          type: string\n          required: true\n          description: Grid region identifier.\n        - name: signal_type\n          in: query\n          type: string\n          required: true\n          description: Emissions signal type.\n        - name: horizon_hours\n          in: query\n          type: integer\n          required: false\n          description: Forecast horizon in hours (max 72).\n        - name: model\n          in: query\n          type: string\n          required: false\n          description: Model version date.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: get-forecast-historical\n        method: GET\n        description: Get historically generated forecast data for back-testing.\n        inputParameters:\n        - name: region\n          in: query\n          type: string\n          required: true\n          description: Grid region identifier.\n        - name: signal_type\n          in: query\n          type: string\n          required: true\n          description: Emissions signal type.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start of historical forecast window.\n        - name: end\n          in: query\n          type: string\n          required: true\n          description: End of historical forecast window.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historical-download\n      path: /historical\n      description: Download multi-year historical\
  \ emissions CSV files.\n      operations:\n      - name: download-historical-data\n        method: GET\n        description: Get download URL for multi-year historical emissions CSV.\n        inputParameters:\n        - name: region\n          in: query\n          type: string\n          required: true\n          description: Grid region identifier.\n        - name: signal_type\n          in: query\n          type: string\n          required: true\n          description: Emissions signal type.\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start date (YYYY-MM-DD).\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End date (YYYY-MM-DD).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: maps\n      path: /maps\n      description: GeoJSON grid region boundary maps.\n\
  \      operations:\n      - name: get-grid-maps\n        method: GET\n        description: Get GeoJSON boundaries for accessible grid regions.\n        inputParameters:\n        - name: signal_type\n          in: query\n          type: string\n          required: false\n          description: Filter by signal type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: carbon-aware-api\n    description: Unified REST API for carbon-aware computing workflows.\n    resources:\n    - path: /v1/auth/login\n      name: authentication\n      description: Authenticate with the WattTime API.\n      operations:\n      - method: GET\n        name: login\n        description: Obtain a WattTime API access token.\n        call: watttime.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/grid/region\n      name: grid-region\n\
  \      description: Identify the grid region for a location.\n      operations:\n      - method: GET\n        name: get-region-from-location\n        description: Look up the grid region for geographic coordinates.\n        call: watttime.get-region-from-location\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/grid/regions\n      name: grid-regions\n      description: List accessible grid regions and models.\n      operations:\n      - method: GET\n        name: get-my-access\n        description: Get all accessible grid regions and available model versions.\n        call: watttime.get-my-access\n        with:\n          signal_type: rest.signal_type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/emissions/realtime\n      name: realtime-emissions\n      description: Real-time emissions data and short-term forecast.\n\
  \      operations:\n      - method: GET\n        name: get-forecast\n        description: Get real-time and forecast emissions for a grid region.\n        call: watttime.get-forecast\n        with:\n          region: rest.region\n          signal_type: rest.signal_type\n          horizon_hours: rest.horizon_hours\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/emissions/historical\n      name: historical-emissions\n      description: Historical emissions data for analysis and reporting.\n      operations:\n      - method: GET\n        name: get-historical-data\n        description: Get historical emissions data (up to 32-day window).\n        call: watttime.get-historical-data\n        with:\n          region: rest.region\n          signal_type: rest.signal_type\n          start: rest.start\n          end: rest.end\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/emissions/forecast-history\n      name:\
  \ forecast-history\n      description: Historically generated forecasts for back-testing.\n      operations:\n      - method: GET\n        name: get-forecast-historical\n        description: Get historical forecast data for algorithm validation.\n        call: watttime.get-forecast-historical\n        with:\n          region: rest.region\n          signal_type: rest.signal_type\n          start: rest.start\n          end: rest.end\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/emissions/download\n      name: emissions-download\n      description: Download multi-year historical emissions CSV data.\n      operations:\n      - method: GET\n        name: download-historical-data\n        description: Get download URL for historical emissions dataset.\n        call: watttime.download-historical-data\n        with:\n          region: rest.region\n          signal_type: rest.signal_type\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/grid/maps\n      name: grid-maps\n      description: GeoJSON grid region boundaries for visualization.\n      operations:\n      - method: GET\n        name: get-grid-maps\n        description: Get GeoJSON boundaries for grid regions.\n        call: watttime.get-grid-maps\n        with:\n          signal_type: rest.signal_type\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: carbon-aware-mcp\n    transport: http\n    description: MCP server for AI-assisted carbon-aware computing and sustainability analysis.\n    tools:\n    - name: authenticate\n      description: Authenticate with the WattTime API to obtain an access token for subsequent calls.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: watttime.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-grid-region\n      description: Identify the electric grid balancing authority\
  \ for a geographic location by latitude and longitude.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: watttime.get-region-from-location\n      with:\n        latitude: tools.latitude\n        longitude: tools.longitude\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accessible-regions\n      description: List all grid regions accessible under the current WattTime subscription, with model versions.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: watttime.get-my-access\n      with:\n        signal_type: tools.signal_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-realtime-emissions\n      description: Get the current real-time marginal emissions forecast for a grid region, updated every 5 minutes. Use for\n        deciding whether NOW is a good time to run a workload.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: watttime.get-forecast\n\
  \      with:\n        region: tools.region\n        signal_type: tools.signal_type\n        horizon_hours: tools.horizon_hours\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-historical-emissions\n      description: Get historical marginal emissions data for a grid region over a time window (max 32 days). Use for reporting\n        past emissions impact.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: watttime.get-historical-data\n      with:\n        region: tools.region\n        signal_type: tools.signal_type\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-forecast-history\n      description: Retrieve previously generated forecast data for a historical period. Use for back-testing carbon-aware\n        scheduling algorithms.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: watttime.get-forecast-historical\n\
  \      with:\n        region: tools.region\n        signal_type: tools.signal_type\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: download-emissions-dataset\n      description: Get a download URL for multi-year historical emissions data as a CSV file.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: watttime.download-historical-data\n      with:\n        region: tools.region\n        signal_type: tools.signal_type\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-grid-maps\n      description: Get GeoJSON boundaries for all accessible grid regions for map visualization.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: watttime.get-grid-maps\n      with:\n        signal_type: tools.signal_type\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/watttime/refs/heads/main/capabilities/carbon-aware-computing.yaml
tags:
- Carbon-Aware Computing
- Emissions
- Sustainability
- Energy
- WattTime
tools:
- description: Authenticate with the WattTime API to obtain an access token for subsequent calls.
  hints:
    openWorld: false
    readOnly: false
  name: authenticate
- description: Identify the electric grid balancing authority for a geographic location by latitude and longitude.
  hints:
    openWorld: true
    readOnly: true
  name: find-grid-region
- description: List all grid regions accessible under the current WattTime subscription, with model versions.
  hints:
    openWorld: false
    readOnly: true
  name: list-accessible-regions
- description: Get the current real-time marginal emissions forecast for a grid region, updated every 5 minutes. Use for deciding whether NOW is a good time to run a workload.
  hints:
    openWorld: true
    readOnly: true
  name: get-realtime-emissions
- description: Get historical marginal emissions data for a grid region over a time window (max 32 days). Use for reporting past emissions impact.
  hints:
    openWorld: false
    readOnly: true
  name: get-historical-emissions
- description: Retrieve previously generated forecast data for a historical period. Use for back-testing carbon-aware scheduling algorithms.
  hints:
    openWorld: false
    readOnly: true
  name: get-forecast-history
- description: Get a download URL for multi-year historical emissions data as a CSV file.
  hints:
    openWorld: false
    readOnly: true
  name: download-emissions-dataset
- description: Get GeoJSON boundaries for all accessible grid regions for map visualization.
  hints:
    openWorld: true
    readOnly: true
  name: get-grid-maps
---

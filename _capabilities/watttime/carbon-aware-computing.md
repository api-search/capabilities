---
categories: []
consumed_apis:
- watttime
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
- look up the grid region for geographic coordinates.
- get realtime emissions
- get real-time and forecast emissions for a grid region.
- get my access
- identify the electric grid balancing authority for a geographic location by latitude and longitude.
- authenticate with the watttime api to obtain an access token for subsequent calls.
- historical emissions data for analysis and reporting.
- get region from location
- get historical forecast data for algorithm validation.
- identify the grid region for a location.
- clean energy
- download emissions dataset
- real-time emissions data and short-term forecast.
- get geojson boundaries for all accessible grid regions for map visualization.
- download multi-year historical emissions csv data.
- get historical emissions data (up to 32-day window).
- emissions
- get historical emissions
- get grid maps
- authenticate with the watttime api.
- get geojson boundaries for grid regions.
- get a download url for multi-year historical emissions data as a csv file.
- get the current real-time marginal emissions forecast for a grid region, updated every 5 minutes. use for deciding whether now is a good time to run a workload.
- retrieve previously generated forecast data for a historical period. use for back-testing carbon-aware scheduling algorithms.
- login
- list accessible regions
- get forecast
- geojson grid region boundaries for visualization.
- climate
- get all accessible grid regions and available model versions.
- get historical data
- watttime
- get forecast history
- historically generated forecasts for back-testing.
- electricity grid
- get download url for historical emissions dataset.
- obtain a watttime api access token.
- sustainability
- energy
- carbon-aware computing
- carbon
- download historical data
- get historical marginal emissions data for a grid region over a time window (max 32 days). use for reporting past emissions impact.
- list accessible grid regions and models.
- get forecast historical
- find grid region
- list all grid regions accessible under the current watttime subscription, with model versions.
- authenticate
slug: carbon-aware-computing
source_filename: carbon-aware-computing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WattTime Carbon-Aware Computing\"\n  description: >-\n    Workflow capability combining WattTime's real-time, forecast, and historical\n    emissions data to enable carbon-aware scheduling, sustainability reporting,\n    and clean energy procurement decisions. Used by software engineers, platform\n    teams, and sustainability analysts to reduce carbon footprint of compute\n    workloads and measure emissions reductions.\n  tags:\n    - Carbon-Aware Computing\n    - Emissions\n    - Sustainability\n    - Energy\n    - WattTime\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WATTTIME_USERNAME: WATTTIME_USERNAME\n      WATTTIME_PASSWORD: WATTTIME_PASSWORD\n\ncapability:\n  consumes:\n    - import: watttime\n      location: ./shared/watttime-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: carbon-aware-api\n      description: \"Unified REST API for\
  \ carbon-aware computing workflows.\"\n      resources:\n        - path: /v1/auth/login\n          name: authentication\n          description: \"Authenticate with the WattTime API.\"\n          operations:\n            - method: GET\n              name: login\n              description: \"Obtain a WattTime API access token.\"\n              call: \"watttime.login\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/grid/region\n          name: grid-region\n          description: \"Identify the grid region for a location.\"\n          operations:\n            - method: GET\n              name: get-region-from-location\n              description: \"Look up the grid region for geographic coordinates.\"\n              call: \"watttime.get-region-from-location\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n              outputParameters:\n           \
  \     - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/grid/regions\n          name: grid-regions\n          description: \"List accessible grid regions and models.\"\n          operations:\n            - method: GET\n              name: get-my-access\n              description: \"Get all accessible grid regions and available model versions.\"\n              call: \"watttime.get-my-access\"\n              with:\n                signal_type: \"rest.signal_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/emissions/realtime\n          name: realtime-emissions\n          description: \"Real-time emissions data and short-term forecast.\"\n          operations:\n            - method: GET\n              name: get-forecast\n              description: \"Get real-time and forecast emissions for a grid region.\"\n              call: \"watttime.get-forecast\"\n              with:\n            \
  \    region: \"rest.region\"\n                signal_type: \"rest.signal_type\"\n                horizon_hours: \"rest.horizon_hours\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/emissions/historical\n          name: historical-emissions\n          description: \"Historical emissions data for analysis and reporting.\"\n          operations:\n            - method: GET\n              name: get-historical-data\n              description: \"Get historical emissions data (up to 32-day window).\"\n              call: \"watttime.get-historical-data\"\n              with:\n                region: \"rest.region\"\n                signal_type: \"rest.signal_type\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/emissions/forecast-history\n          name: forecast-history\n\
  \          description: \"Historically generated forecasts for back-testing.\"\n          operations:\n            - method: GET\n              name: get-forecast-historical\n              description: \"Get historical forecast data for algorithm validation.\"\n              call: \"watttime.get-forecast-historical\"\n              with:\n                region: \"rest.region\"\n                signal_type: \"rest.signal_type\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/emissions/download\n          name: emissions-download\n          description: \"Download multi-year historical emissions CSV data.\"\n          operations:\n            - method: GET\n              name: download-historical-data\n              description: \"Get download URL for historical emissions dataset.\"\n              call: \"watttime.download-historical-data\"\
  \n              with:\n                region: \"rest.region\"\n                signal_type: \"rest.signal_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/grid/maps\n          name: grid-maps\n          description: \"GeoJSON grid region boundaries for visualization.\"\n          operations:\n            - method: GET\n              name: get-grid-maps\n              description: \"Get GeoJSON boundaries for grid regions.\"\n              call: \"watttime.get-grid-maps\"\n              with:\n                signal_type: \"rest.signal_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: carbon-aware-mcp\n      transport: http\n      description: \"MCP server for AI-assisted carbon-aware computing and sustainability analysis.\"\n      tools:\n        - name: authenticate\n          description: \"Authenticate\
  \ with the WattTime API to obtain an access token for subsequent calls.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"watttime.login\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-grid-region\n          description: \"Identify the electric grid balancing authority for a geographic location by latitude and longitude.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"watttime.get-region-from-location\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-accessible-regions\n          description: \"List all grid regions accessible under the current WattTime subscription, with model versions.\"\n          hints:\n            readOnly: true\n            openWorld: false\n\
  \          call: \"watttime.get-my-access\"\n          with:\n            signal_type: \"tools.signal_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-realtime-emissions\n          description: \"Get the current real-time marginal emissions forecast for a grid region, updated every 5 minutes. Use for deciding whether NOW is a good time to run a workload.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"watttime.get-forecast\"\n          with:\n            region: \"tools.region\"\n            signal_type: \"tools.signal_type\"\n            horizon_hours: \"tools.horizon_hours\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-historical-emissions\n          description: \"Get historical marginal emissions data for a grid region over a time window (max 32 days). Use for reporting past emissions impact.\"\n     \
  \     hints:\n            readOnly: true\n            openWorld: false\n          call: \"watttime.get-historical-data\"\n          with:\n            region: \"tools.region\"\n            signal_type: \"tools.signal_type\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-forecast-history\n          description: \"Retrieve previously generated forecast data for a historical period. Use for back-testing carbon-aware scheduling algorithms.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"watttime.get-forecast-historical\"\n          with:\n            region: \"tools.region\"\n            signal_type: \"tools.signal_type\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: download-emissions-dataset\n\
  \          description: \"Get a download URL for multi-year historical emissions data as a CSV file.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"watttime.download-historical-data\"\n          with:\n            region: \"tools.region\"\n            signal_type: \"tools.signal_type\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-grid-maps\n          description: \"Get GeoJSON boundaries for all accessible grid regions for map visualization.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"watttime.get-grid-maps\"\n          with:\n            signal_type: \"tools.signal_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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

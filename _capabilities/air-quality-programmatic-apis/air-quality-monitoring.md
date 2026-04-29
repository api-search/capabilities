---
categories:
- monitoring
consumed_apis:
- aqicn
description: Unified workflow for querying real-time air quality data, monitoring station health, and spatial air quality analysis. Used by environmental monitoring applications and public health systems.
layout: capability
name: Air Quality Monitoring Workflow
operations:
- description: Get current AQI for a city
  method: GET
  name: get-aqi-by-city
  path: /v1/air-quality/city/{city}
- description: Get AQI for coordinates
  method: GET
  name: get-aqi-by-coordinates
  path: /v1/air-quality/coordinates
- description: Search stations by keyword
  method: GET
  name: search-stations
  path: /v1/stations/search
personas: []
provider_name: Air Quality Programmatic APIs
provider_slug: air-quality-programmatic-apis
search_terms:
- get aqi for coordinates
- Environmental Analyst
- environment
- app developer integrating air quality data into mobile or web applications
- search stations by keyword
- search for air quality monitoring stations by city or station name
- monitoring
- get aqi by city
- search monitoring stations
- search air quality stations
- government data
- Developer
- open data
- air quality by city name
- get aqi by coordinates
- query real-time aqi and search monitoring stations
- researcher or analyst studying air quality trends and patterns
- search stations
- epa
- air quality by coordinates
- air quality
- get real-time aqi for a geographic location using latitude and longitude
- get current aqi for a city
- real-time data
- public health
- iot
- get real-time air quality index (aqi) and pollutant data for a city
slug: air-quality-monitoring
source_filename: air-quality-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Air Quality Monitoring Workflow\"\n  description: \"Unified workflow for querying real-time air quality data, monitoring station health, and spatial air quality analysis. Used by environmental monitoring applications and public health systems.\"\n  tags:\n    - Air Quality\n    - Environment\n    - Public Health\n    - Open Data\n    - Monitoring\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AQICN_API_TOKEN: AQICN_API_TOKEN\n\ncapability:\n  consumes:\n    - import: aqicn\n      location: ./shared/aqicn-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: air-quality-monitoring-api\n      description: \"Unified REST API for air quality data retrieval and monitoring.\"\n      resources:\n        - path: /v1/air-quality/city/{city}\n          name: aqi-by-city\n          description: \"Air quality by city name\"\n          operations:\n            -\
  \ method: GET\n              name: get-aqi-by-city\n              description: \"Get current AQI for a city\"\n              call: \"aqicn.get-aqi-by-city\"\n              with:\n                city: \"rest.city\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/air-quality/coordinates\n          name: aqi-by-coordinates\n          description: \"Air quality by coordinates\"\n          operations:\n            - method: GET\n              name: get-aqi-by-coordinates\n              description: \"Get AQI for coordinates\"\n              call: \"aqicn.get-aqi-by-coordinates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stations/search\n          name: station-search\n          description: \"Search monitoring stations\"\n          operations:\n            - method: GET\n              name: search-stations\n              description: \"Search\
  \ stations by keyword\"\n              call: \"aqicn.search-stations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: air-quality-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted air quality data retrieval and environmental analysis.\"\n      tools:\n        - name: get-aqi-by-city\n          description: \"Get real-time air quality index (AQI) and pollutant data for a city\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aqicn.get-aqi-by-city\"\n          with:\n            city: \"tools.city\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-aqi-by-coordinates\n          description: \"Get real-time AQI for a geographic location using latitude and longitude\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"aqicn.get-aqi-by-coordinates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-air-quality-stations\n          description: \"Search for air quality monitoring stations by city or station name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aqicn.search-stations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/air-quality-programmatic-apis/refs/heads/main/capabilities/air-quality-monitoring.yaml
tags:
- Air Quality
- Environment
- Public Health
- Open Data
- Monitoring
tools:
- description: Get real-time air quality index (AQI) and pollutant data for a city
  hints:
    openWorld: true
    readOnly: true
  name: get-aqi-by-city
- description: Get real-time AQI for a geographic location using latitude and longitude
  hints:
    openWorld: true
    readOnly: true
  name: get-aqi-by-coordinates
- description: Search for air quality monitoring stations by city or station name
  hints:
    openWorld: true
    readOnly: true
  name: search-air-quality-stations
---

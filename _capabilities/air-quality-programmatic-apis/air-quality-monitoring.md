---
categories:
- monitoring
consumed_apis: []
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
- get real-time aqi for a geographic location using latitude and longitude
- query real-time aqi and search monitoring stations
- get current aqi for a city
- Developer
- search air quality stations
- search monitoring stations
- get real-time air quality index (aqi) and pollutant data for a city
- search for air quality monitoring stations by city or station name
- iot
- search stations by keyword
- environment
- monitoring
- public health
- epa
- air quality
- get aqi for coordinates
- search stations
- app developer integrating air quality data into mobile or web applications
- air quality by coordinates
- government data
- Environmental Analyst
- researcher or analyst studying air quality trends and patterns
- real-time data
- air quality by city name
- get aqi by coordinates
- get aqi by city
- open data
slug: air-quality-monitoring
source_filename: air-quality-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Air Quality Monitoring Workflow\n  description: Unified workflow for querying real-time air quality data, monitoring station health, and spatial air quality\n    analysis. Used by environmental monitoring applications and public health systems.\n  tags:\n  - Air Quality\n  - Environment\n  - Public Health\n  - Open Data\n  - Monitoring\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AQICN_API_TOKEN: AQICN_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: aqicn\n    baseUri: https://api.waqi.info\n    description: AQICN real-time air quality JSON API\n    authentication:\n      type: apikey\n      key: token\n      value: '{{AQICN_API_TOKEN}}'\n      placement: query\n    resources:\n    - name: stations-by-city\n      path: /feed/{city}/\n      description: Get air quality by city name\n      operations:\n      - name: get-aqi-by-city\n        method: GET\n        description:\
  \ Get real-time AQI for a city\n        inputParameters:\n        - name: city\n          in: path\n          type: string\n          required: true\n          description: City name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stations-by-geo\n      path: /feed/geo:{lat};{lng}/\n      description: Get air quality by coordinates\n      operations:\n      - name: get-aqi-by-coordinates\n        method: GET\n        description: Get real-time AQI for geographic coordinates\n        inputParameters:\n        - name: lat\n          in: path\n          type: number\n          required: true\n          description: Latitude\n        - name: lng\n          in: path\n          type: number\n          required: true\n          description: Longitude\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: station-search\n\
  \      path: /search/\n      description: Search for stations\n      operations:\n      - name: search-stations\n        method: GET\n        description: Search monitoring stations by keyword\n        inputParameters:\n        - name: keyword\n          in: query\n          type: string\n          required: true\n          description: Search keyword\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stations-in-bounds\n      path: /map/bounds/\n      description: Get stations in map bounds\n      operations:\n      - name: get-stations-in-bounds\n        method: GET\n        description: Get all stations within a geographic bounding box\n        inputParameters:\n        - name: latlng\n          in: query\n          type: string\n          required: true\n          description: Bounding box coordinates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: air-quality-monitoring-api\n    description: Unified REST API for air quality data retrieval and monitoring.\n    resources:\n    - path: /v1/air-quality/city/{city}\n      name: aqi-by-city\n      description: Air quality by city name\n      operations:\n      - method: GET\n        name: get-aqi-by-city\n        description: Get current AQI for a city\n        call: aqicn.get-aqi-by-city\n        with:\n          city: rest.city\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/air-quality/coordinates\n      name: aqi-by-coordinates\n      description: Air quality by coordinates\n      operations:\n      - method: GET\n        name: get-aqi-by-coordinates\n        description: Get AQI for coordinates\n        call: aqicn.get-aqi-by-coordinates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stations/search\n    \
  \  name: station-search\n      description: Search monitoring stations\n      operations:\n      - method: GET\n        name: search-stations\n        description: Search stations by keyword\n        call: aqicn.search-stations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: air-quality-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted air quality data retrieval and environmental analysis.\n    tools:\n    - name: get-aqi-by-city\n      description: Get real-time air quality index (AQI) and pollutant data for a city\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aqicn.get-aqi-by-city\n      with:\n        city: tools.city\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-aqi-by-coordinates\n      description: Get real-time AQI for a geographic location using latitude and longitude\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: aqicn.get-aqi-by-coordinates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-air-quality-stations\n      description: Search for air quality monitoring stations by city or station name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aqicn.search-stations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

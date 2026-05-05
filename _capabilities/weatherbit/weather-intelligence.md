---
categories: []
consumed_apis:
- weatherbit
description: Unified weather intelligence workflow combining current conditions, forecasts, historical data, alerts, and air quality. Used by developers, businesses, and researchers to access global weather data.
layout: capability
name: Weatherbit Weather Intelligence
operations:
- description: Get current weather for a location
  method: GET
  name: get-current-weather
  path: /v1/current
- description: Get severe weather alerts for a location
  method: GET
  name: get-alerts
  path: /v1/alerts
- description: Get daily weather forecast
  method: GET
  name: get-daily-forecast
  path: /v1/forecasts/daily
- description: Get hourly weather forecast
  method: GET
  name: get-hourly-forecast
  path: /v1/forecasts/hourly
- description: Get historical daily observations
  method: GET
  name: get-history-daily
  path: /v1/history/daily
- description: Get current air quality conditions
  method: GET
  name: get-current-airquality
  path: /v1/air-quality/current
- description: Get hourly air quality forecast
  method: GET
  name: get-airquality-forecast
  path: /v1/air-quality/forecast
- description: Get agricultural weather forecast
  method: GET
  name: get-agweather-forecast
  path: /v1/agricultural-weather
- description: Get climate normals for a location
  method: GET
  name: get-normals
  path: /v1/climate-normals
personas: []
provider_name: Weatherbit
provider_slug: weatherbit
search_terms:
- get air quality forecast
- hourly weather forecasts
- get daily forecast
- get 240-hour hourly weather forecast
- get current airquality
- get climate normals
- get energy forecast
- get alerts
- get agricultural weather forecast
- get 16-day daily weather forecast
- historical weather observations
- get agweather forecast
- get current air quality including pollutants and aqi
- get hourly air quality forecast
- get historical daily weather observations
- daily weather forecasts
- agricultural weather data
- get severe weather alerts for a location
- forecasting
- air quality forecasts
- historical climate normals
- get agricultural weather forecast for farming applications
- alerts
- get history daily
- agricultural
- get historical climate normals and averages
- get current air quality conditions
- get historical daily observations
- get current air quality
- current weather conditions
- severe weather alerts
- get energy weather forecast with degree days
- get agricultural weather
- get severe alerts
- get normals
- get current weather
- get hourly weather forecast
- air quality
- get hourly forecast
- get historical weather
- get airquality forecast
- get 72-hour air quality forecast
- get current weather conditions for any location
- agricultural weather
- historical data
- get current weather for a location
- current air quality
- get climate normals for a location
- weather
- get daily weather forecast
slug: weather-intelligence
source_filename: weather-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Weatherbit Weather Intelligence\"\n  description: \"Unified weather intelligence workflow combining current conditions, forecasts, historical data, alerts, and air quality. Used by developers, businesses, and researchers to access global weather data.\"\n  tags:\n    - Weather\n    - Forecasting\n    - Historical Data\n    - Air Quality\n    - Alerts\n    - Agricultural\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEATHERBIT_API_KEY: WEATHERBIT_API_KEY\n\ncapability:\n  consumes:\n    - import: weatherbit\n      location: ./shared/weatherbit-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: weather-intelligence-api\n      description: \"Unified REST API for weather intelligence using Weatherbit data.\"\n      resources:\n        - path: /v1/current\n          name: current-conditions\n          description: \"Current weather conditions\"\n    \
  \      operations:\n            - method: GET\n              name: get-current-weather\n              description: \"Get current weather for a location\"\n              call: \"weatherbit.get-current-weather\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alerts\n          name: alerts\n          description: \"Severe weather alerts\"\n          operations:\n            - method: GET\n              name: get-alerts\n              description: \"Get severe weather alerts for a location\"\n              call: \"weatherbit.get-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/forecasts/daily\n          name: daily-forecast\n          description: \"Daily weather forecasts\"\n          operations:\n            - method: GET\n              name: get-daily-forecast\n              description: \"Get daily weather forecast\"\n              call:\
  \ \"weatherbit.get-daily-forecast\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/forecasts/hourly\n          name: hourly-forecast\n          description: \"Hourly weather forecasts\"\n          operations:\n            - method: GET\n              name: get-hourly-forecast\n              description: \"Get hourly weather forecast\"\n              call: \"weatherbit.get-hourly-forecast\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/history/daily\n          name: historical-weather\n          description: \"Historical weather observations\"\n          operations:\n            - method: GET\n              name: get-history-daily\n              description: \"Get historical daily observations\"\n              call: \"weatherbit.get-history-daily\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/air-quality/current\n          name: air-quality\n          description: \"Current air quality\"\n          operations:\n            - method: GET\n              name: get-current-airquality\n              description: \"Get current air quality conditions\"\n              call: \"weatherbit.get-current-airquality\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/air-quality/forecast\n          name: air-quality-forecast\n          description: \"Air quality forecasts\"\n          operations:\n            - method: GET\n              name: get-airquality-forecast\n              description: \"Get hourly air quality forecast\"\n              call: \"weatherbit.get-airquality-forecast\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/agricultural-weather\n          name: agweather\n          description: \"Agricultural\
  \ weather data\"\n          operations:\n            - method: GET\n              name: get-agweather-forecast\n              description: \"Get agricultural weather forecast\"\n              call: \"weatherbit.get-agweather-forecast\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/climate-normals\n          name: climate-normals\n          description: \"Historical climate normals\"\n          operations:\n            - method: GET\n              name: get-normals\n              description: \"Get climate normals for a location\"\n              call: \"weatherbit.get-normals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: weather-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted weather intelligence using Weatherbit data.\"\n      tools:\n        - name: get-current-weather\n\
  \          description: \"Get current weather conditions for any location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weatherbit.get-current-weather\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-severe-alerts\n          description: \"Get severe weather alerts for a location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weatherbit.get-alerts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-daily-forecast\n          description: \"Get 16-day daily weather forecast\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weatherbit.get-daily-forecast\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-hourly-forecast\n          description: \"Get 240-hour hourly weather\
  \ forecast\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weatherbit.get-hourly-forecast\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-historical-weather\n          description: \"Get historical daily weather observations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weatherbit.get-history-daily\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-current-air-quality\n          description: \"Get current air quality including pollutants and AQI\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weatherbit.get-current-airquality\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-air-quality-forecast\n          description: \"Get 72-hour air quality forecast\"\n    \
  \      hints:\n            readOnly: true\n            openWorld: true\n          call: \"weatherbit.get-airquality-forecast\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-agricultural-weather\n          description: \"Get agricultural weather forecast for farming applications\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weatherbit.get-agweather-forecast\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-climate-normals\n          description: \"Get historical climate normals and averages\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weatherbit.get-normals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-energy-forecast\n          description: \"Get energy weather forecast with degree days\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"weatherbit.get-energy-forecast\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/weatherbit/refs/heads/main/capabilities/weather-intelligence.yaml
tags:
- Weather
- Forecasting
- Historical Data
- Air Quality
- Alerts
- Agricultural
tools:
- description: Get current weather conditions for any location
  hints:
    openWorld: true
    readOnly: true
  name: get-current-weather
- description: Get severe weather alerts for a location
  hints:
    openWorld: true
    readOnly: true
  name: get-severe-alerts
- description: Get 16-day daily weather forecast
  hints:
    openWorld: true
    readOnly: true
  name: get-daily-forecast
- description: Get 240-hour hourly weather forecast
  hints:
    openWorld: true
    readOnly: true
  name: get-hourly-forecast
- description: Get historical daily weather observations
  hints:
    openWorld: true
    readOnly: true
  name: get-historical-weather
- description: Get current air quality including pollutants and AQI
  hints:
    openWorld: true
    readOnly: true
  name: get-current-air-quality
- description: Get 72-hour air quality forecast
  hints:
    openWorld: true
    readOnly: true
  name: get-air-quality-forecast
- description: Get agricultural weather forecast for farming applications
  hints:
    openWorld: true
    readOnly: true
  name: get-agricultural-weather
- description: Get historical climate normals and averages
  hints:
    openWorld: true
    readOnly: true
  name: get-climate-normals
- description: Get energy weather forecast with degree days
  hints:
    openWorld: true
    readOnly: true
  name: get-energy-forecast
---

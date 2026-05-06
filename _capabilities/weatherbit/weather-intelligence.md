---
categories: []
consumed_apis: []
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
- get alerts
- get daily weather forecast
- get agricultural weather forecast for farming applications
- get climate normals
- historical data
- alerts
- get energy forecast
- current weather conditions
- get energy weather forecast with degree days
- get historical daily weather observations
- get current weather
- weather
- air quality forecasts
- get current airquality
- get daily forecast
- agricultural weather data
- get 240-hour hourly weather forecast
- get severe weather alerts for a location
- get history daily
- get normals
- historical climate normals
- get current air quality including pollutants and aqi
- forecasting
- air quality
- get current air quality conditions
- get current weather for a location
- historical weather observations
- agricultural weather
- daily weather forecasts
- get hourly weather forecast
- get current weather conditions for any location
- get climate normals for a location
- get severe alerts
- get historical weather
- get hourly forecast
- get airquality forecast
- get agricultural weather forecast
- get current air quality
- get historical climate normals and averages
- get hourly air quality forecast
- get historical daily observations
- agricultural
- get agweather forecast
- get 72-hour air quality forecast
- current air quality
- severe weather alerts
- get 16-day daily weather forecast
- get agricultural weather
- get air quality forecast
- hourly weather forecasts
slug: weather-intelligence
source_filename: weather-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Weatherbit Weather Intelligence\n  description: Unified weather intelligence workflow combining current conditions, forecasts, historical data, alerts, and\n    air quality. Used by developers, businesses, and researchers to access global weather data.\n  tags:\n  - Weather\n  - Forecasting\n  - Historical Data\n  - Air Quality\n  - Alerts\n  - Agricultural\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WEATHERBIT_API_KEY: WEATHERBIT_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: weatherbit\n    baseUri: https://api.weatherbit.io/v2.0\n    description: Weatherbit weather data API covering current conditions, forecasts, historical observations, air quality,\n      and agricultural weather.\n    authentication:\n      type: apikey\n      key: key\n      value: '{{WEATHERBIT_API_KEY}}'\n      placement: query\n    resources:\n    - name: current-weather\n      path: /current\n\
  \      description: Current weather observations\n      operations:\n      - name: get-current-weather\n        method: GET\n        description: Returns current weather observations\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Longitude\n        - name: city\n          in: query\n          type: string\n          required: false\n          description: City name\n        - name: city_id\n          in: query\n          type: integer\n          required: false\n          description: City ID\n        - name: postal_code\n          in: query\n          type: string\n          required: false\n          description: Postal code\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: Country code\n       \
  \ - name: units\n          in: query\n          type: string\n          required: false\n          description: Units (M=metric, S=scientific, I=imperial)\n        - name: lang\n          in: query\n          type: string\n          required: false\n          description: Language code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts\n      path: /alerts\n      description: Severe weather alerts\n      operations:\n      - name: get-alerts\n        method: GET\n        description: Returns severe weather alerts\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: forecast-daily\n      path: /forecast/daily\n      description: Daily weather forecasts\n      operations:\n      - name: get-daily-forecast\n        method: GET\n        description: Returns a daily weather forecast\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Longitude\n        - name: city\n          in: query\n          type: string\n          required: false\n          description: City name\n        - name: days\n          in: query\n          type: integer\n          required: false\n          description: Number of forecast days (max 16)\n        - name: units\n          in: query\n          type: string\n          required: false\n          description: Units (M/S/I)\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: forecast-hourly\n      path: /forecast/hourly\n      description: Hourly weather forecasts\n      operations:\n      - name: get-hourly-forecast\n        method: GET\n        description: Returns an hourly weather forecast\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Longitude\n        - name: hours\n          in: query\n          type: integer\n          required: false\n          description: Number of hours (max 240)\n        - name: units\n          in: query\n          type: string\n          required: false\n          description: Units\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: history-daily\n\
  \      path: /history/daily\n      description: Historical daily weather observations\n      operations:\n      - name: get-history-daily\n        method: GET\n        description: Returns historical daily weather observations\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Longitude\n        - name: start_date\n          in: query\n          type: string\n          required: true\n          description: Start date (YYYY-MM-DD)\n        - name: end_date\n          in: query\n          type: string\n          required: true\n          description: End date (YYYY-MM-DD)\n        - name: units\n          in: query\n          type: string\n          required: false\n          description: Units\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: air-quality-current\n      path: /current/airquality\n      description: Current air quality conditions\n      operations:\n      - name: get-current-airquality\n        method: GET\n        description: Returns current air quality conditions\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-airquality\n      path: /forecast/airquality\n      description: Air quality forecasts\n      operations:\n      - name: get-airquality-forecast\n        method: GET\n        description: Returns 72-hour hourly air quality forecast\n        inputParameters:\n        - name:\
  \ lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-agweather\n      path: /forecast/agweather\n      description: Agricultural weather forecasts\n      operations:\n      - name: get-agweather-forecast\n        method: GET\n        description: Returns agricultural weather forecast\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: normals\n      path: /normals\n      description: Historical climate normals\n      operations:\n      - name: get-normals\n        method: GET\n        description: Returns historical climate normals (averages)\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        - name: start_day\n          in: query\n          type: string\n          required: true\n          description: Start day (MM-DD)\n        - name: end_day\n          in: query\n          type: string\n          required: true\n          description: End day (MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: weather-intelligence-api\n\
  \    description: Unified REST API for weather intelligence using Weatherbit data.\n    resources:\n    - path: /v1/current\n      name: current-conditions\n      description: Current weather conditions\n      operations:\n      - method: GET\n        name: get-current-weather\n        description: Get current weather for a location\n        call: weatherbit.get-current-weather\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts\n      name: alerts\n      description: Severe weather alerts\n      operations:\n      - method: GET\n        name: get-alerts\n        description: Get severe weather alerts for a location\n        call: weatherbit.get-alerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/forecasts/daily\n      name: daily-forecast\n      description: Daily weather forecasts\n      operations:\n      - method: GET\n        name: get-daily-forecast\n        description: Get daily weather\
  \ forecast\n        call: weatherbit.get-daily-forecast\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/forecasts/hourly\n      name: hourly-forecast\n      description: Hourly weather forecasts\n      operations:\n      - method: GET\n        name: get-hourly-forecast\n        description: Get hourly weather forecast\n        call: weatherbit.get-hourly-forecast\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/history/daily\n      name: historical-weather\n      description: Historical weather observations\n      operations:\n      - method: GET\n        name: get-history-daily\n        description: Get historical daily observations\n        call: weatherbit.get-history-daily\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/air-quality/current\n      name: air-quality\n      description: Current air quality\n      operations:\n      - method: GET\n        name:\
  \ get-current-airquality\n        description: Get current air quality conditions\n        call: weatherbit.get-current-airquality\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/air-quality/forecast\n      name: air-quality-forecast\n      description: Air quality forecasts\n      operations:\n      - method: GET\n        name: get-airquality-forecast\n        description: Get hourly air quality forecast\n        call: weatherbit.get-airquality-forecast\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/agricultural-weather\n      name: agweather\n      description: Agricultural weather data\n      operations:\n      - method: GET\n        name: get-agweather-forecast\n        description: Get agricultural weather forecast\n        call: weatherbit.get-agweather-forecast\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/climate-normals\n      name: climate-normals\n\
  \      description: Historical climate normals\n      operations:\n      - method: GET\n        name: get-normals\n        description: Get climate normals for a location\n        call: weatherbit.get-normals\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: weather-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted weather intelligence using Weatherbit data.\n    tools:\n    - name: get-current-weather\n      description: Get current weather conditions for any location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weatherbit.get-current-weather\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-severe-alerts\n      description: Get severe weather alerts for a location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weatherbit.get-alerts\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-daily-forecast\n      description: Get 16-day daily weather forecast\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weatherbit.get-daily-forecast\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hourly-forecast\n      description: Get 240-hour hourly weather forecast\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weatherbit.get-hourly-forecast\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-historical-weather\n      description: Get historical daily weather observations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weatherbit.get-history-daily\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-current-air-quality\n      description: Get current air quality including pollutants and AQI\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weatherbit.get-current-airquality\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-air-quality-forecast\n      description: Get 72-hour air quality forecast\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weatherbit.get-airquality-forecast\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-agricultural-weather\n      description: Get agricultural weather forecast for farming applications\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weatherbit.get-agweather-forecast\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-climate-normals\n      description: Get historical climate normals and averages\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weatherbit.get-normals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-energy-forecast\n      description: Get energy weather forecast with degree days\n   \
  \   hints:\n        readOnly: true\n        openWorld: true\n      call: weatherbit.get-energy-forecast\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

---
categories: []
consumed_apis:
- accuweather
description: Unified workflow combining AccuWeather's location, conditions, forecasts, air quality, and storm tracking APIs into a single capability for weather-aware applications. Used by developers, IoT platforms, travel apps, and emergency management systems.
layout: capability
name: AccuWeather Weather Intelligence
operations:
- description: Search for weather locations by text query
  method: GET
  name: search-locations
  path: /v1/locations
- description: Get current weather conditions
  method: GET
  name: get-current-weather
  path: /v1/weather/current/{locationKey}
- description: Get hourly weather forecast
  method: GET
  name: get-hourly-forecast
  path: /v1/weather/forecast/hourly/{locationKey}
- description: Get daily weather forecast
  method: GET
  name: get-daily-forecast
  path: /v1/weather/forecast/daily/{locationKey}
- description: Get MinuteCast precipitation forecast
  method: GET
  name: get-minutecast
  path: /v1/weather/minutecast/{locationKey}
- description: Get current air quality
  method: GET
  name: get-air-quality
  path: /v1/air-quality/{locationKey}
- description: Get all active global storms
  method: GET
  name: get-active-storms
  path: /v1/storms/active/{locationKey}
personas: []
provider_name: AccuWeather
provider_slug: accuweather
search_terms:
- daily weather forecast
- get minutecast
- meteorology
- Emergency Management
- storm tracking
- search locations
- get current weather conditions
- iot system using weather data for device automation
- emergency response team tracking storms and severe weather
- minute-by-minute precipitation forecast
- air quality
- search for weather locations
- get hourly air quality
- Mobile App
- storms
- get air quality
- hourly weather forecast
- geographic location search and resolution
- get hourly weather forecast
- get daily weather forecast
- get storm details
- short and long-range weather prediction
- forecasts
- Developer
- get detailed tracking data for a specific tropical storm
- get current weather conditions for a location key
- get hourly weather forecast for the next 12-120 hours
- consumer weather app presenting conditions and forecasts
- get current weather
- unified weather data workflow for location search, conditions, forecasts, air quality, and storm tracking
- aqi and pollutant measurement data
- active and historical tropical cyclone monitoring
- accuweather
- get minutecast precipitation forecast
- IoT Platform
- weather
- location services
- air quality data
- get daily forecast
- get hourly air quality forecast
- get all active global storms
- get hourly forecast
- search for weather locations by partial name or query text
- current and historical weather observation data
- current weather conditions for a location
- get current air quality
- get 1, 5, 7, 10, or 15 day weather forecast
- get accuweather minutecast minute-by-minute precipitation forecast
- software developer building weather-aware applications
- get active storms
- get current air quality index and pollutant data
- get all currently active tropical storms globally
- active tropical storm tracking
- search for weather locations by text query
slug: weather-intelligence
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: AccuWeather Weather Intelligence\n  description: >-\n    Unified workflow combining AccuWeather's location, conditions, forecasts, air quality, and storm\n    tracking APIs into a single capability for weather-aware applications. Used by developers, IoT\n    platforms, travel apps, and emergency management systems.\n  tags:\n    - AccuWeather\n    - Weather\n    - Forecasts\n    - Air Quality\n    - Storm Tracking\n    - Location Services\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ACCUWEATHER_API_KEY: ACCUWEATHER_API_KEY\n\ncapability:\n  consumes:\n    - import: accuweather\n      location: ./shared/accuweather-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: weather-intelligence-api\n      description: Unified REST API for AccuWeather weather intelligence workflows.\n      resources:\n        - path: /v1/locations\n          name: locations\n\
  \          description: Search for weather locations\n          operations:\n            - method: GET\n              name: search-locations\n              description: Search for weather locations by text query\n              call: \"accuweather.autocomplete-locations\"\n              with:\n                Query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/weather/current/{locationKey}\n          name: current-conditions\n          description: Current weather conditions for a location\n          operations:\n            - method: GET\n              name: get-current-weather\n              description: Get current weather conditions\n              call: \"accuweather.get-current-conditions\"\n              with:\n                locationKey: \"rest.locationKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/weather/forecast/hourly/{locationKey}\n\
  \          name: hourly-forecast\n          description: Hourly weather forecast\n          operations:\n            - method: GET\n              name: get-hourly-forecast\n              description: Get hourly weather forecast\n              call: \"accuweather.get-hourly-forecast\"\n              with:\n                locationKey: \"rest.locationKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/weather/forecast/daily/{locationKey}\n          name: daily-forecast\n          description: Daily weather forecast\n          operations:\n            - method: GET\n              name: get-daily-forecast\n              description: Get daily weather forecast\n              call: \"accuweather.get-daily-forecast\"\n              with:\n                locationKey: \"rest.locationKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/weather/minutecast/{locationKey}\n\
  \          name: minutecast\n          description: Minute-by-minute precipitation forecast\n          operations:\n            - method: GET\n              name: get-minutecast\n              description: Get MinuteCast precipitation forecast\n              call: \"accuweather.get-minutecast\"\n              with:\n                locationKey: \"rest.locationKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/air-quality/{locationKey}\n          name: air-quality\n          description: Air quality data\n          operations:\n            - method: GET\n              name: get-air-quality\n              description: Get current air quality\n              call: \"accuweather.get-air-quality\"\n              with:\n                locationKey: \"rest.locationKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/storms/active/{locationKey}\n\
  \          name: active-storms\n          description: Active tropical storm tracking\n          operations:\n            - method: GET\n              name: get-active-storms\n              description: Get all active global storms\n              call: \"accuweather.get-active-storms\"\n              with:\n                locationKey: \"rest.locationKey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: weather-intelligence-mcp\n      transport: http\n      description: MCP server for AI-assisted weather intelligence and forecasting workflows.\n      tools:\n        - name: search-locations\n          description: Search for weather locations by partial name or query text\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"accuweather.autocomplete-locations\"\n          with:\n            Query: \"tools.query\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-current-weather\n          description: Get current weather conditions for a location key\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"accuweather.get-current-conditions\"\n          with:\n            locationKey: \"tools.locationKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-hourly-forecast\n          description: Get hourly weather forecast for the next 12-120 hours\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"accuweather.get-hourly-forecast\"\n          with:\n            locationKey: \"tools.locationKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-daily-forecast\n          description: Get 1, 5, 7, 10, or 15 day weather forecast\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"accuweather.get-daily-forecast\"\n          with:\n            locationKey: \"tools.locationKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-minutecast\n          description: Get AccuWeather MinuteCast minute-by-minute precipitation forecast\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"accuweather.get-minutecast\"\n          with:\n            locationKey: \"tools.locationKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-air-quality\n          description: Get current air quality index and pollutant data\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"accuweather.get-air-quality\"\n          with:\n            locationKey: \"tools.locationKey\"\n          outputParameters:\n            - type: object\n             \
  \ mapping: \"$.\"\n        - name: get-hourly-air-quality\n          description: Get hourly air quality forecast\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"accuweather.get-hourly-air-quality\"\n          with:\n            locationKey: \"tools.locationKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-active-storms\n          description: Get all currently active tropical storms globally\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"accuweather.get-active-storms\"\n          with:\n            locationKey: \"tools.locationKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-storm-details\n          description: Get detailed tracking data for a specific tropical storm\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"accuweather.get-storm-details\"\
  \n          with:\n            year: \"tools.year\"\n            basinId: \"tools.basinId\"\n            depressionNumber: \"tools.depressionNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/accuweather/refs/heads/main/capabilities/weather-intelligence.yaml
tags:
- AccuWeather
- Weather
- Forecasts
- Air Quality
- Storm Tracking
- Location Services
tools:
- description: Search for weather locations by partial name or query text
  hints:
    openWorld: true
    readOnly: true
  name: search-locations
- description: Get current weather conditions for a location key
  hints:
    openWorld: true
    readOnly: true
  name: get-current-weather
- description: Get hourly weather forecast for the next 12-120 hours
  hints:
    openWorld: true
    readOnly: true
  name: get-hourly-forecast
- description: Get 1, 5, 7, 10, or 15 day weather forecast
  hints:
    openWorld: true
    readOnly: true
  name: get-daily-forecast
- description: Get AccuWeather MinuteCast minute-by-minute precipitation forecast
  hints:
    openWorld: true
    readOnly: true
  name: get-minutecast
- description: Get current air quality index and pollutant data
  hints:
    openWorld: true
    readOnly: true
  name: get-air-quality
- description: Get hourly air quality forecast
  hints:
    openWorld: true
    readOnly: true
  name: get-hourly-air-quality
- description: Get all currently active tropical storms globally
  hints:
    openWorld: true
    readOnly: true
  name: get-active-storms
- description: Get detailed tracking data for a specific tropical storm
  hints:
    openWorld: true
    readOnly: true
  name: get-storm-details
---

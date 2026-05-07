---
categories: []
consumed_apis: []
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
- active tropical storm tracking
- Mobile App
- get minutecast precipitation forecast
- IoT Platform
- search locations
- iot system using weather data for device automation
- accuweather
- hourly weather forecast
- active and historical tropical cyclone monitoring
- consumer weather app presenting conditions and forecasts
- get minutecast
- minute-by-minute precipitation forecast
- get hourly air quality forecast
- get 1, 5, 7, 10, or 15 day weather forecast
- get daily weather forecast
- current weather conditions for a location
- search for weather locations by text query
- get all active global storms
- search for weather locations
- get detailed tracking data for a specific tropical storm
- location services
- unified weather data workflow for location search, conditions, forecasts, air quality, and storm tracking
- current and historical weather observation data
- get hourly weather forecast
- get daily forecast
- get air quality
- air quality data
- aqi and pollutant measurement data
- air quality
- get current weather conditions for a location key
- storms
- short and long-range weather prediction
- get current air quality
- emergency response team tracking storms and severe weather
- get current air quality index and pollutant data
- get hourly weather forecast for the next 12-120 hours
- geographic location search and resolution
- Developer
- get current weather
- get storm details
- get current weather conditions
- forecasts
- get accuweather minutecast minute-by-minute precipitation forecast
- get active storms
- software developer building weather-aware applications
- weather
- get hourly forecast
- meteorology
- get hourly air quality
- get all currently active tropical storms globally
- storm tracking
- Emergency Management
- search for weather locations by partial name or query text
slug: weather-intelligence
source_filename: weather-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AccuWeather Weather Intelligence\n  description: Unified workflow combining AccuWeather's location, conditions, forecasts, air quality, and storm tracking APIs\n    into a single capability for weather-aware applications. Used by developers, IoT platforms, travel apps, and emergency\n    management systems.\n  tags:\n  - AccuWeather\n  - Weather\n  - Forecasts\n  - Air Quality\n  - Storm Tracking\n  - Location Services\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ACCUWEATHER_API_KEY: ACCUWEATHER_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: accuweather\n    baseUri: https://dataservice.accuweather.com\n    description: AccuWeather One Platform API for weather data and location services.\n    authentication:\n      type: apikey\n      key: apikey\n      value: '{{ACCUWEATHER_API_KEY}}'\n      placement: query\n    resources:\n    - name: locations\n      path: /api\n    \
  \  description: Location search and autocomplete\n      operations:\n      - name: autocomplete-locations\n        method: GET\n        description: AccuWeather Retrieves a List of Locations Matching the Specified Query\n        inputParameters:\n        - name: Query\n          in: query\n          type: string\n          required: true\n          description: Partial query text for location search\n        - name: Locale\n          in: query\n          type: string\n          required: false\n          description: ISO 639-2 and ISO 3166-1 code for the locale\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resolve-location\n        method: GET\n        description: AccuWeather Takes in a Location as a Query Parameter and Returns Location Key\n        inputParameters:\n        - name: locationKey\n          in: query\n          type: string\n          required: true\n          description: Location\
  \ key to resolve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: current-conditions\n      path: /api/current\n      description: Current weather conditions by location\n      operations:\n      - name: get-current-conditions\n        method: GET\n        description: AccuWeather Retrieves the Latest Weather Conditions for a Location\n        inputParameters:\n        - name: locationKey\n          in: path\n          type: string\n          required: true\n          description: AccuWeather location key\n        - name: MeasurementDisplay\n          in: query\n          type: string\n          required: false\n          description: Imperial or Metric measurement display\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecasts\n      path: /api\n      description: Hourly, daily, and minute-by-minute forecasts\n\
  \      operations:\n      - name: get-hourly-forecast\n        method: GET\n        description: AccuWeather Retrieves the Latest Hourly Forecast for a Location\n        inputParameters:\n        - name: locationKey\n          in: path\n          type: string\n          required: true\n          description: AccuWeather location key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-daily-forecast\n        method: GET\n        description: AccuWeather Retrieves the Latest Daily Forecast for a Location\n        inputParameters:\n        - name: locationKey\n          in: path\n          type: string\n          required: true\n          description: AccuWeather location key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-minutecast\n        method: GET\n        description: AccuWeather Retrieves the\
  \ Latest Minute by Minute Forecast for a Location\n        inputParameters:\n        - name: locationKey\n          in: path\n          type: string\n          required: true\n          description: AccuWeather location key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: air-quality\n      path: /api/airQuality\n      description: Air quality and hourly AQI data\n      operations:\n      - name: get-air-quality\n        method: GET\n        description: AccuWeather Retrieves the Current Air Quality for a Given Location\n        inputParameters:\n        - name: locationKey\n          in: path\n          type: string\n          required: true\n          description: AccuWeather location key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-hourly-air-quality\n        method: GET\n        description: AccuWeather\
  \ Retrieves the Hourly Air Quality Forecast for a Given Location\n        inputParameters:\n        - name: locationKey\n          in: path\n          type: string\n          required: true\n          description: AccuWeather location key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: storms\n      path: /api\n      description: Tropical storms and active storm tracking\n      operations:\n      - name: get-active-storms\n        method: GET\n        description: AccuWeather Retrieves All Active Global Storms\n        inputParameters:\n        - name: locationKey\n          in: path\n          type: string\n          required: true\n          description: Location key for storm context\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-storm-details\n        method: GET\n        description: AccuWeather\
  \ Retrieves Data About a Specific Storm\n        inputParameters:\n        - name: year\n          in: path\n          type: integer\n          required: true\n          description: Year of the storm\n        - name: basinId\n          in: path\n          type: string\n          required: true\n          description: Basin identifier\n        - name: depressionNumber\n          in: path\n          type: integer\n          required: true\n          description: Depression number of the storm\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: weather-intelligence-api\n    description: Unified REST API for AccuWeather weather intelligence workflows.\n    resources:\n    - path: /v1/locations\n      name: locations\n      description: Search for weather locations\n      operations:\n      - method: GET\n        name: search-locations\n        description:\
  \ Search for weather locations by text query\n        call: accuweather.autocomplete-locations\n        with:\n          Query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/weather/current/{locationKey}\n      name: current-conditions\n      description: Current weather conditions for a location\n      operations:\n      - method: GET\n        name: get-current-weather\n        description: Get current weather conditions\n        call: accuweather.get-current-conditions\n        with:\n          locationKey: rest.locationKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/weather/forecast/hourly/{locationKey}\n      name: hourly-forecast\n      description: Hourly weather forecast\n      operations:\n      - method: GET\n        name: get-hourly-forecast\n        description: Get hourly weather forecast\n        call: accuweather.get-hourly-forecast\n        with:\n          locationKey:\
  \ rest.locationKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/weather/forecast/daily/{locationKey}\n      name: daily-forecast\n      description: Daily weather forecast\n      operations:\n      - method: GET\n        name: get-daily-forecast\n        description: Get daily weather forecast\n        call: accuweather.get-daily-forecast\n        with:\n          locationKey: rest.locationKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/weather/minutecast/{locationKey}\n      name: minutecast\n      description: Minute-by-minute precipitation forecast\n      operations:\n      - method: GET\n        name: get-minutecast\n        description: Get MinuteCast precipitation forecast\n        call: accuweather.get-minutecast\n        with:\n          locationKey: rest.locationKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/air-quality/{locationKey}\n  \
  \    name: air-quality\n      description: Air quality data\n      operations:\n      - method: GET\n        name: get-air-quality\n        description: Get current air quality\n        call: accuweather.get-air-quality\n        with:\n          locationKey: rest.locationKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/storms/active/{locationKey}\n      name: active-storms\n      description: Active tropical storm tracking\n      operations:\n      - method: GET\n        name: get-active-storms\n        description: Get all active global storms\n        call: accuweather.get-active-storms\n        with:\n          locationKey: rest.locationKey\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: weather-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted weather intelligence and forecasting workflows.\n    tools:\n    - name: search-locations\n\
  \      description: Search for weather locations by partial name or query text\n      hints:\n        readOnly: true\n        openWorld: true\n      call: accuweather.autocomplete-locations\n      with:\n        Query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-current-weather\n      description: Get current weather conditions for a location key\n      hints:\n        readOnly: true\n        openWorld: true\n      call: accuweather.get-current-conditions\n      with:\n        locationKey: tools.locationKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hourly-forecast\n      description: Get hourly weather forecast for the next 12-120 hours\n      hints:\n        readOnly: true\n        openWorld: true\n      call: accuweather.get-hourly-forecast\n      with:\n        locationKey: tools.locationKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-daily-forecast\n\
  \      description: Get 1, 5, 7, 10, or 15 day weather forecast\n      hints:\n        readOnly: true\n        openWorld: true\n      call: accuweather.get-daily-forecast\n      with:\n        locationKey: tools.locationKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-minutecast\n      description: Get AccuWeather MinuteCast minute-by-minute precipitation forecast\n      hints:\n        readOnly: true\n        openWorld: true\n      call: accuweather.get-minutecast\n      with:\n        locationKey: tools.locationKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-air-quality\n      description: Get current air quality index and pollutant data\n      hints:\n        readOnly: true\n        openWorld: true\n      call: accuweather.get-air-quality\n      with:\n        locationKey: tools.locationKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hourly-air-quality\n      description:\
  \ Get hourly air quality forecast\n      hints:\n        readOnly: true\n        openWorld: true\n      call: accuweather.get-hourly-air-quality\n      with:\n        locationKey: tools.locationKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-active-storms\n      description: Get all currently active tropical storms globally\n      hints:\n        readOnly: true\n        openWorld: true\n      call: accuweather.get-active-storms\n      with:\n        locationKey: tools.locationKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-storm-details\n      description: Get detailed tracking data for a specific tropical storm\n      hints:\n        readOnly: true\n        openWorld: true\n      call: accuweather.get-storm-details\n      with:\n        year: tools.year\n        basinId: tools.basinId\n        depressionNumber: tools.depressionNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

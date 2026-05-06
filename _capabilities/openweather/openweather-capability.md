---
categories: []
consumed_apis: []
description: Programmatic access to the OpenWeather One Call API for current, minute, hourly, and daily forecasts plus government weather alerts, and the OpenWeather Air Pollution API for current, forecast, and historical air quality data including the Air Quality Index and pollutant concentrations.
layout: capability
name: OpenWeather One Call and Air Pollution API
operations:
- description: Current and forecast weather data for a coordinate
  method: GET
  name: getonecall
  path: /onecall
- description: Historical weather data for a coordinate and timestamp
  method: GET
  name: getonecalltimemachine
  path: /onecall/timemachine
- description: Current air pollution data for a coordinate
  method: GET
  name: getcurrentairpollution
  path: /air_pollution
- description: Hourly air pollution forecast for a coordinate
  method: GET
  name: getairpollutionforecast
  path: /air_pollution/forecast
- description: Historical air pollution data for a coordinate
  method: GET
  name: getairpollutionhistory
  path: /air_pollution/history
personas: []
provider_name: OpenWeather
provider_slug: openweather
search_terms:
- weather
- current and forecast weather data for a coordinate
- current air pollution data for a coordinate
- hourly air pollution forecast for a coordinate
- climate
- api
- openweather
- getairpollutionhistory
- getonecall
- forecasting
- historical weather data for a coordinate and timestamp
- getairpollutionforecast
- historical air pollution data for a coordinate
- getonecalltimemachine
- air quality
- getcurrentairpollution
- air pollution
slug: openweather-capability
source_filename: openweather-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenWeather One Call and Air Pollution API\n  description: Programmatic access to the OpenWeather One Call API for current, minute, hourly, and daily forecasts plus government\n    weather alerts, and the OpenWeather Air Pollution API for current, forecast, and historical air quality data including\n    the Air Quality Index and pollutant concentrations.\n  tags:\n  - Openweather\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openweather\n    baseUri: https://api.openweathermap.org/data/3.0\n    description: OpenWeather One Call and Air Pollution API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: appid\n      value: '{{OPENWEATHER_TOKEN}}'\n    resources:\n    - name: onecall\n      path: /onecall\n      operations:\n      - name: getonecall\n        method: GET\n        description: Current and forecast weather data for a coordinate\n\
  \        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees, range -90 to 90.\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees, range -180 to 180.\n        - name: exclude\n          in: query\n          type: string\n          description: Comma-separated list of forecast blocks to omit from the response. Allowed values are current, minutely,\n            hourly, daily, and alerts.\n        - name: units\n          in: query\n          type: string\n          description: Units of measurement. One of standard, metric, or imperial. Default is standard (Kelvin, m/s).\n        - name: lang\n          in: query\n          type: string\n          description: ISO language code for localized response text.\n        - name: appid\n          in: query\n          type: string\n          required:\
  \ true\n          description: OpenWeather API key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: onecall-timemachine\n      path: /onecall/timemachine\n      operations:\n      - name: getonecalltimemachine\n        method: GET\n        description: Historical weather data for a coordinate and timestamp\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: dt\n          in: query\n          type: integer\n          required: true\n          description: Unix UTC timestamp for the requested historical reading.\n        - name: units\n          in: query\n          type: string\n        - name: lang\n          in: query\n\
  \          type: string\n        - name: appid\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: air-pollution\n      path: /air_pollution\n      operations:\n      - name: getcurrentairpollution\n        method: GET\n        description: Current air pollution data for a coordinate\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n        - name: lon\n          in: query\n          type: number\n          required: true\n        - name: appid\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: air-pollution-forecast\n      path: /air_pollution/forecast\n      operations:\n      - name: getairpollutionforecast\n\
  \        method: GET\n        description: Hourly air pollution forecast for a coordinate\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n        - name: lon\n          in: query\n          type: number\n          required: true\n        - name: appid\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: air-pollution-history\n      path: /air_pollution/history\n      operations:\n      - name: getairpollutionhistory\n        method: GET\n        description: Historical air pollution data for a coordinate\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n        - name: lon\n          in: query\n          type: number\n          required: true\n        - name: start\n          in: query\n     \
  \     type: integer\n          required: true\n          description: Unix UTC start timestamp.\n        - name: end\n          in: query\n          type: integer\n          required: true\n          description: Unix UTC end timestamp.\n        - name: appid\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: openweather-rest\n    description: REST adapter for OpenWeather One Call and Air Pollution API.\n    resources:\n    - path: /onecall\n      name: getonecall\n      operations:\n      - method: GET\n        name: getonecall\n        description: Current and forecast weather data for a coordinate\n        call: openweather.getonecall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /onecall/timemachine\n      name: getonecalltimemachine\n  \
  \    operations:\n      - method: GET\n        name: getonecalltimemachine\n        description: Historical weather data for a coordinate and timestamp\n        call: openweather.getonecalltimemachine\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /air_pollution\n      name: getcurrentairpollution\n      operations:\n      - method: GET\n        name: getcurrentairpollution\n        description: Current air pollution data for a coordinate\n        call: openweather.getcurrentairpollution\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /air_pollution/forecast\n      name: getairpollutionforecast\n      operations:\n      - method: GET\n        name: getairpollutionforecast\n        description: Hourly air pollution forecast for a coordinate\n        call: openweather.getairpollutionforecast\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /air_pollution/history\n      name:\
  \ getairpollutionhistory\n      operations:\n      - method: GET\n        name: getairpollutionhistory\n        description: Historical air pollution data for a coordinate\n        call: openweather.getairpollutionhistory\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: openweather-mcp\n    transport: http\n    description: MCP adapter for OpenWeather One Call and Air Pollution API for AI agent use.\n    tools:\n    - name: getonecall\n      description: Current and forecast weather data for a coordinate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openweather.getonecall\n      with:\n        lat: tools.lat\n        lon: tools.lon\n        exclude: tools.exclude\n        units: tools.units\n        lang: tools.lang\n        appid: tools.appid\n      inputParameters:\n      - name: lat\n        type: number\n        description: Latitude in decimal degrees,\
  \ range -90 to 90.\n        required: true\n      - name: lon\n        type: number\n        description: Longitude in decimal degrees, range -180 to 180.\n        required: true\n      - name: exclude\n        type: string\n        description: Comma-separated list of forecast blocks to omit from the response. Allowed values are current, minutely,\n          hourly, daily, and alerts.\n      - name: units\n        type: string\n        description: Units of measurement. One of standard, metric, or imperial. Default is standard (Kelvin, m/s).\n      - name: lang\n        type: string\n        description: ISO language code for localized response text.\n      - name: appid\n        type: string\n        description: OpenWeather API key.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getonecalltimemachine\n      description: Historical weather data for a coordinate and timestamp\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: openweather.getonecalltimemachine\n      with:\n        lat: tools.lat\n        lon: tools.lon\n        dt: tools.dt\n        units: tools.units\n        lang: tools.lang\n        appid: tools.appid\n      inputParameters:\n      - name: lat\n        type: number\n        description: Latitude in decimal degrees.\n        required: true\n      - name: lon\n        type: number\n        description: Longitude in decimal degrees.\n        required: true\n      - name: dt\n        type: integer\n        description: Unix UTC timestamp for the requested historical reading.\n        required: true\n      - name: units\n        type: string\n        description: units\n      - name: lang\n        type: string\n        description: lang\n      - name: appid\n        type: string\n        description: appid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcurrentairpollution\n      description:\
  \ Current air pollution data for a coordinate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openweather.getcurrentairpollution\n      with:\n        lat: tools.lat\n        lon: tools.lon\n        appid: tools.appid\n      inputParameters:\n      - name: lat\n        type: number\n        description: lat\n        required: true\n      - name: lon\n        type: number\n        description: lon\n        required: true\n      - name: appid\n        type: string\n        description: appid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getairpollutionforecast\n      description: Hourly air pollution forecast for a coordinate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openweather.getairpollutionforecast\n      with:\n        lat: tools.lat\n        lon: tools.lon\n        appid: tools.appid\n      inputParameters:\n\
  \      - name: lat\n        type: number\n        description: lat\n        required: true\n      - name: lon\n        type: number\n        description: lon\n        required: true\n      - name: appid\n        type: string\n        description: appid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getairpollutionhistory\n      description: Historical air pollution data for a coordinate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openweather.getairpollutionhistory\n      with:\n        lat: tools.lat\n        lon: tools.lon\n        start: tools.start\n        end: tools.end\n        appid: tools.appid\n      inputParameters:\n      - name: lat\n        type: number\n        description: lat\n        required: true\n      - name: lon\n        type: number\n        description: lon\n        required: true\n      - name: start\n        type: integer\n        description:\
  \ Unix UTC start timestamp.\n        required: true\n      - name: end\n        type: integer\n        description: Unix UTC end timestamp.\n        required: true\n      - name: appid\n        type: string\n        description: appid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OPENWEATHER_TOKEN: OPENWEATHER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openweather/refs/heads/main/capabilities/openweather-capability.yaml
tags:
- Openweather
- API
tools:
- description: Current and forecast weather data for a coordinate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getonecall
- description: Historical weather data for a coordinate and timestamp
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getonecalltimemachine
- description: Current air pollution data for a coordinate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentairpollution
- description: Hourly air pollution forecast for a coordinate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getairpollutionforecast
- description: Historical air pollution data for a coordinate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getairpollutionhistory
---

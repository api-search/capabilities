---
categories: []
consumed_apis: []
description: Unified weather monitoring workflow combining alerts, forecasts, observations, radar, and aviation weather. Used by emergency managers, developers, and weather enthusiasts to access NWS open data.
layout: capability
name: Weather.gov Weather Monitoring
operations:
- description: List all weather alerts
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: List currently active weather alerts
  method: GET
  name: list-active-alerts
  path: /v1/alerts/active
- description: Get count of active alerts
  method: GET
  name: get-alert-count
  path: /v1/alerts/active/count
- description: Get forecast for a grid point
  method: GET
  name: get-forecast
  path: /v1/forecasts
- description: Get hourly forecast for a grid point
  method: GET
  name: get-hourly-forecast
  path: /v1/forecasts/hourly
- description: Get metadata for a lat/lon point
  method: GET
  name: get-point
  path: /v1/points/{point}
- description: List observation stations
  method: GET
  name: list-stations
  path: /v1/stations
- description: Get latest observation for a station
  method: GET
  name: get-latest-observation
  path: /v1/stations/{stationId}/observations/latest
- description: List radar stations
  method: GET
  name: list-radar-stations
  path: /v1/radar-stations
- description: List NWS forecast zones
  method: GET
  name: list-zones
  path: /v1/zones
- description: List NWS text products
  method: GET
  name: list-products
  path: /v1/products
- description: List SIGMET/AIRMET advisories
  method: GET
  name: list-sigmets
  path: /v1/aviation/sigmets
personas: []
provider_name: Weather.gov
provider_slug: weather-gov
search_terms:
- list sigmet/airmet advisories
- get weather forecast for a grid point
- list nws forecast zones, optionally filtered by area or type
- alerts
- united states
- get text products
- query nws text weather products
- location metadata lookup
- list currently active weather alerts
- weather
- list nws text products
- active weather alerts
- get metadata for a lat/lon point
- government
- get alert count
- get office info
- list currently active nws weather alerts
- list active alerts
- list radar stations
- get the latest weather observation from a station
- weather alerts and warnings
- get office headlines
- monitoring
- list sigmet/airmet aviation weather advisories
- nws text products
- forecasting
- list all weather alerts
- list observation stations
- get alerts by zone
- list nws radar stations
- latest station observation
- get latest observation
- count of active alerts
- list stations
- get count of active alerts
- list nws weather observation stations
- weather forecasts by grid point
- get historical observations from a weather station
- list nws forecast zones
- list sigmets
- get zone forecast
- get point
- aviation weather advisories
- get point metadata
- get hourly forecast
- get forecast
- get forecast for a grid point
- get active alerts for a specific state or marine area
- get hourly weather forecast for a grid point
- get hourly forecast for a grid point
- get news headlines from a nws forecast office
- list observations
- get forecast metadata for a latitude/longitude location
- list weather alerts from the national weather service
- get active alerts for a specific nws zone
- get latest observation for a station
- list products
- nws forecast zones
- radar stations
- open data
- get information about a nws forecast office
- list alerts
- get alerts by area
- list zones
- hourly weather forecasts
- observation stations
- get the forecast for a nws forecast zone
slug: weather-monitoring
source_filename: weather-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Weather.gov Weather Monitoring\n  description: Unified weather monitoring workflow combining alerts, forecasts, observations, radar, and aviation weather.\n    Used by emergency managers, developers, and weather enthusiasts to access NWS open data.\n  tags:\n  - Weather\n  - Government\n  - Monitoring\n  - Alerts\n  - Forecasting\n  - United States\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WEATHER_GOV_USER_AGENT: WEATHER_GOV_USER_AGENT\ncapability:\n  consumes:\n  - type: http\n    namespace: weather-gov\n    baseUri: https://api.weather.gov\n    description: National Weather Service REST API providing open weather data for the United States.\n    authentication:\n      type: apikey\n      key: User-Agent\n      value: '{{WEATHER_GOV_USER_AGENT}}'\n      placement: header\n    resources:\n    - name: alerts\n      path: /alerts\n      description: Weather alerts and warnings issued by NWS\n\
  \      operations:\n      - name: alerts-query\n        method: GET\n        description: Returns all alerts\n        inputParameters:\n        - name: active\n          in: query\n          type: boolean\n          required: false\n          description: List only active alerts\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start time for alerts\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End time for alerts\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Alert status filter\n        - name: message_type\n          in: query\n          type: string\n          required: false\n          description: Alert message type filter\n        - name: area\n          in: query\n          type: string\n          required: false\n          description: State or marine area code\n    \
  \    - name: region\n          in: query\n          type: string\n          required: false\n          description: Marine region code\n        - name: zone\n          in: query\n          type: string\n          required: false\n          description: Zone ID filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: alerts-active\n        method: GET\n        description: Returns all currently active alerts\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Alert status\n        - name: message_type\n          in: query\n          type: string\n          required: false\n          description: Message type\n        - name: event\n          in: query\n          type: string\n          required: false\n          description: Event type\n        - name: area\n          in: query\n          type: string\n\
  \          required: false\n          description: Area code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: alerts-active-count\n        method: GET\n        description: Returns info on the number of active alerts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: alerts-active-zone\n        method: GET\n        description: Returns active alerts for the given NWS public zone or county\n        inputParameters:\n        - name: zoneId\n          in: path\n          type: string\n          required: true\n          description: NWS zone ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: alerts-active-area\n        method: GET\n        description: Returns active alerts for the given area\n        inputParameters:\n\
  \        - name: area\n          in: path\n          type: string\n          required: true\n          description: State or marine area code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: alerts-types\n        method: GET\n        description: Returns a list of alert types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: alerts-single\n        method: GET\n        description: Returns a specific alert\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Alert ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecasts\n      path: /gridpoints\n      description: Gridpoint forecast data\n      operations:\n      - name: gridpoint\n\
  \        method: GET\n        description: Returns raw numerical forecast data for a 2.5km grid area\n        inputParameters:\n        - name: wfo\n          in: path\n          type: string\n          required: true\n          description: Weather Forecast Office ID\n        - name: x\n          in: path\n          type: integer\n          required: true\n          description: Forecast grid X coordinate\n        - name: y\n          in: path\n          type: integer\n          required: true\n          description: Forecast grid Y coordinate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: gridpoint-forecast\n        method: GET\n        description: Returns a textual forecast for a 2.5km grid area\n        inputParameters:\n        - name: wfo\n          in: path\n          type: string\n          required: true\n          description: Weather Forecast Office ID\n        - name: x\n       \
  \   in: path\n          type: integer\n          required: true\n          description: Forecast grid X coordinate\n        - name: y\n          in: path\n          type: integer\n          required: true\n          description: Forecast grid Y coordinate\n        - name: units\n          in: query\n          type: string\n          required: false\n          description: Units (us or si)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: gridpoint-forecast-hourly\n        method: GET\n        description: Returns a textual hourly forecast for a 2.5km grid area\n        inputParameters:\n        - name: wfo\n          in: path\n          type: string\n          required: true\n          description: Weather Forecast Office ID\n        - name: x\n          in: path\n          type: integer\n          required: true\n          description: Forecast grid X coordinate\n        - name: y\n          in:\
  \ path\n          type: integer\n          required: true\n          description: Forecast grid Y coordinate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: gridpoint-stations\n        method: GET\n        description: Returns a list of observation stations usable for a given grid area\n        inputParameters:\n        - name: wfo\n          in: path\n          type: string\n          required: true\n          description: Weather Forecast Office ID\n        - name: x\n          in: path\n          type: integer\n          required: true\n          description: Grid X coordinate\n        - name: y\n          in: path\n          type: integer\n          required: true\n          description: Grid Y coordinate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: points\n      path: /points\n      description:\
  \ Location metadata and lookup\n      operations:\n      - name: point\n        method: GET\n        description: Returns metadata about a given latitude/longitude point\n        inputParameters:\n        - name: point\n          in: path\n          type: string\n          required: true\n          description: Latitude,Longitude coordinates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: point-stations\n        method: GET\n        description: Returns a list of observation stations for a given point\n        inputParameters:\n        - name: point\n          in: path\n          type: string\n          required: true\n          description: Latitude,Longitude coordinates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stations\n      path: /stations\n      description: Observation stations and their readings\n\
  \      operations:\n      - name: obs-stations\n        method: GET\n        description: Returns a list of observation stations\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: State code filter\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: obs-station\n        method: GET\n        description: Returns metadata about a given observation station\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n          description: Observation station ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: station-observation-list\n\
  \        method: GET\n        description: Returns a list of observations for a given station\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n          description: Observation station ID\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start time\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End time\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Result limit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: station-observation-latest\n        method: GET\n        description: Returns the latest observation for a station\n        inputParameters:\n        - name: stationId\n          in: path\n          type:\
  \ string\n          required: true\n          description: Observation station ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: zones\n      path: /zones\n      description: NWS forecast zones\n      operations:\n      - name: zone-list\n        method: GET\n        description: Returns a list of zones\n        inputParameters:\n        - name: area\n          in: query\n          type: string\n          required: false\n          description: State or territory code\n        - name: region\n          in: query\n          type: string\n          required: false\n          description: Marine region\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Zone type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: zone\n        method: GET\n  \
  \      description: Returns metadata about a given zone\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n          description: Zone type\n        - name: zoneId\n          in: path\n          type: string\n          required: true\n          description: Zone ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: zone-forecast\n        method: GET\n        description: Returns the current zone forecast for a given zone\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n          description: Zone type\n        - name: zoneId\n          in: path\n          type: string\n          required: true\n          description: Zone ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ radar\n      path: /radar\n      description: Radar stations and data\n      operations:\n      - name: radar-stations\n        method: GET\n        description: Returns a list of radar stations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: radar-station\n        method: GET\n        description: Returns metadata about a given radar station\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n          description: Radar station ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: aviation\n      path: /aviation\n      description: Aviation weather products\n      operations:\n      - name: sigmet-query\n        method: GET\n        description: Returns a list of SIGMET/AIRMETs\n        inputParameters:\n        - name: date\n    \
  \      in: query\n          type: string\n          required: false\n          description: Date filter\n        - name: atsu\n          in: query\n          type: string\n          required: false\n          description: ATSU filter\n        - name: sequence\n          in: query\n          type: string\n          required: false\n          description: Sequence filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cwsu\n        method: GET\n        description: Returns metadata about a Center Weather Service Unit\n        inputParameters:\n        - name: cwsuId\n          in: path\n          type: string\n          required: true\n          description: CWSU identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      description: Text weather products\n      operations:\n\
  \      - name: products-query\n        method: GET\n        description: Returns a list of text products\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Product type\n        - name: location\n          in: query\n          type: string\n          required: false\n          description: Location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: product\n        method: GET\n        description: Returns a specific text product\n        inputParameters:\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: Product ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offices\n      path: /offices\n      description: NWS forecast offices\n      operations:\n\
  \      - name: office\n        method: GET\n        description: Returns metadata about a NWS forecast office\n        inputParameters:\n        - name: officeId\n          in: path\n          type: string\n          required: true\n          description: NWS office ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: office-headlines\n        method: GET\n        description: Returns a list of news headlines for a given NWS office\n        inputParameters:\n        - name: officeId\n          in: path\n          type: string\n          required: true\n          description: NWS office ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: weather-monitoring-api\n    description: Unified REST API for weather monitoring using NWS open data.\n    resources:\n    -\
  \ path: /v1/alerts\n      name: alerts\n      description: Weather alerts and warnings\n      operations:\n      - method: GET\n        name: list-alerts\n        description: List all weather alerts\n        call: weather-gov.alerts-query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts/active\n      name: active-alerts\n      description: Active weather alerts\n      operations:\n      - method: GET\n        name: list-active-alerts\n        description: List currently active weather alerts\n        call: weather-gov.alerts-active\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts/active/count\n      name: alert-count\n      description: Count of active alerts\n      operations:\n      - method: GET\n        name: get-alert-count\n        description: Get count of active alerts\n        call: weather-gov.alerts-active-count\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/forecasts\n      name: forecasts\n      description: Weather forecasts by grid point\n      operations:\n      - method: GET\n        name: get-forecast\n        description: Get forecast for a grid point\n        call: weather-gov.gridpoint-forecast\n        with:\n          wfo: rest.wfo\n          x: rest.x\n          y: rest.y\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/forecasts/hourly\n      name: hourly-forecasts\n      description: Hourly weather forecasts\n      operations:\n      - method: GET\n        name: get-hourly-forecast\n        description: Get hourly forecast for a grid point\n        call: weather-gov.gridpoint-forecast-hourly\n        with:\n          wfo: rest.wfo\n          x: rest.x\n          y: rest.y\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/points/{point}\n      name: points\n      description: Location metadata lookup\n      operations:\n \
  \     - method: GET\n        name: get-point\n        description: Get metadata for a lat/lon point\n        call: weather-gov.point\n        with:\n          point: rest.point\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stations\n      name: stations\n      description: Observation stations\n      operations:\n      - method: GET\n        name: list-stations\n        description: List observation stations\n        call: weather-gov.obs-stations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stations/{stationId}/observations/latest\n      name: latest-observation\n      description: Latest station observation\n      operations:\n      - method: GET\n        name: get-latest-observation\n        description: Get latest observation for a station\n        call: weather-gov.station-observation-latest\n        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/radar-stations\n      name: radar-stations\n      description: Radar stations\n      operations:\n      - method: GET\n        name: list-radar-stations\n        description: List radar stations\n        call: weather-gov.radar-stations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/zones\n      name: zones\n      description: NWS forecast zones\n      operations:\n      - method: GET\n        name: list-zones\n        description: List NWS forecast zones\n        call: weather-gov.zone-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: products\n      description: NWS text products\n      operations:\n      - method: GET\n        name: list-products\n        description: List NWS text products\n        call: weather-gov.products-query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/aviation/sigmets\n\
  \      name: sigmets\n      description: Aviation weather advisories\n      operations:\n      - method: GET\n        name: list-sigmets\n        description: List SIGMET/AIRMET advisories\n        call: weather-gov.sigmet-query\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: weather-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted weather monitoring using NWS open data.\n    tools:\n    - name: list-alerts\n      description: List weather alerts from the National Weather Service\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.alerts-query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-active-alerts\n      description: List currently active NWS weather alerts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.alerts-active\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-alerts-by-area\n      description: Get active alerts for a specific state or marine area\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.alerts-active-area\n      with:\n        area: tools.area\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alerts-by-zone\n      description: Get active alerts for a specific NWS zone\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.alerts-active-zone\n      with:\n        zoneId: tools.zoneId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-point-metadata\n      description: Get forecast metadata for a latitude/longitude location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.point\n      with:\n        point: tools.point\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-forecast\n      description:\
  \ Get weather forecast for a grid point\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.gridpoint-forecast\n      with:\n        wfo: tools.wfo\n        x: tools.x\n        y: tools.y\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hourly-forecast\n      description: Get hourly weather forecast for a grid point\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.gridpoint-forecast-hourly\n      with:\n        wfo: tools.wfo\n        x: tools.x\n        y: tools.y\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stations\n      description: List NWS weather observation stations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.obs-stations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-latest-observation\n      description: Get the latest weather observation from a\
  \ station\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.station-observation-latest\n      with:\n        stationId: tools.stationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-observations\n      description: Get historical observations from a weather station\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.station-observation-list\n      with:\n        stationId: tools.stationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-radar-stations\n      description: List NWS radar stations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.radar-stations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-zone-forecast\n      description: Get the forecast for a NWS forecast zone\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.zone-forecast\n\
  \      with:\n        type: tools.type\n        zoneId: tools.zoneId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-zones\n      description: List NWS forecast zones, optionally filtered by area or type\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.zone-list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-text-products\n      description: Query NWS text weather products\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.products-query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sigmets\n      description: List SIGMET/AIRMET aviation weather advisories\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.sigmet-query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-office-info\n      description: Get information about a NWS\
  \ forecast office\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.office\n      with:\n        officeId: tools.officeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-office-headlines\n      description: Get news headlines from a NWS forecast office\n      hints:\n        readOnly: true\n        openWorld: true\n      call: weather-gov.office-headlines\n      with:\n        officeId: tools.officeId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/weather-gov/refs/heads/main/capabilities/weather-monitoring.yaml
tags:
- Weather
- Government
- Monitoring
- Alerts
- Forecasting
- United States
tools:
- description: List weather alerts from the National Weather Service
  hints:
    openWorld: true
    readOnly: true
  name: list-alerts
- description: List currently active NWS weather alerts
  hints:
    openWorld: true
    readOnly: true
  name: list-active-alerts
- description: Get active alerts for a specific state or marine area
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-by-area
- description: Get active alerts for a specific NWS zone
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-by-zone
- description: Get forecast metadata for a latitude/longitude location
  hints:
    openWorld: true
    readOnly: true
  name: get-point-metadata
- description: Get weather forecast for a grid point
  hints:
    openWorld: true
    readOnly: true
  name: get-forecast
- description: Get hourly weather forecast for a grid point
  hints:
    openWorld: true
    readOnly: true
  name: get-hourly-forecast
- description: List NWS weather observation stations
  hints:
    openWorld: true
    readOnly: true
  name: list-stations
- description: Get the latest weather observation from a station
  hints:
    openWorld: true
    readOnly: true
  name: get-latest-observation
- description: Get historical observations from a weather station
  hints:
    openWorld: true
    readOnly: true
  name: list-observations
- description: List NWS radar stations
  hints:
    openWorld: true
    readOnly: true
  name: list-radar-stations
- description: Get the forecast for a NWS forecast zone
  hints:
    openWorld: true
    readOnly: true
  name: get-zone-forecast
- description: List NWS forecast zones, optionally filtered by area or type
  hints:
    openWorld: true
    readOnly: true
  name: list-zones
- description: Query NWS text weather products
  hints:
    openWorld: true
    readOnly: true
  name: get-text-products
- description: List SIGMET/AIRMET aviation weather advisories
  hints:
    openWorld: true
    readOnly: true
  name: list-sigmets
- description: Get information about a NWS forecast office
  hints:
    openWorld: true
    readOnly: true
  name: get-office-info
- description: Get news headlines from a NWS forecast office
  hints:
    openWorld: true
    readOnly: true
  name: get-office-headlines
---

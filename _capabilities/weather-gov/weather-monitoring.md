---
categories: []
consumed_apis:
- weather-gov
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
- list currently active nws weather alerts
- get alerts by area
- list nws radar stations
- open data
- latest station observation
- monitoring
- list sigmet/airmet advisories
- get the forecast for a nws forecast zone
- get office info
- list observations
- active weather alerts
- united states
- get forecast for a grid point
- list active alerts
- location metadata lookup
- get count of active alerts
- get point
- alerts
- list radar stations
- weather forecasts by grid point
- get the latest weather observation from a station
- hourly weather forecasts
- get historical observations from a weather station
- get office headlines
- government
- list observation stations
- get hourly forecast for a grid point
- list sigmets
- get active alerts for a specific nws zone
- get latest observation
- get point metadata
- list alerts
- get information about a nws forecast office
- list nws forecast zones, optionally filtered by area or type
- get hourly weather forecast for a grid point
- get latest observation for a station
- list nws forecast zones
- weather alerts and warnings
- nws forecast zones
- aviation weather advisories
- get text products
- list sigmet/airmet aviation weather advisories
- nws text products
- list nws text products
- list stations
- get metadata for a lat/lon point
- get active alerts for a specific state or marine area
- get alert count
- list currently active weather alerts
- get alerts by zone
- get forecast metadata for a latitude/longitude location
- get forecast
- count of active alerts
- list weather alerts from the national weather service
- list products
- observation stations
- forecasting
- list all weather alerts
- list nws weather observation stations
- get zone forecast
- query nws text weather products
- list zones
- get news headlines from a nws forecast office
- get weather forecast for a grid point
- weather
- get hourly forecast
- radar stations
slug: weather-monitoring
source_filename: weather-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Weather.gov Weather Monitoring\"\n  description: \"Unified weather monitoring workflow combining alerts, forecasts, observations, radar, and aviation weather. Used by emergency managers, developers, and weather enthusiasts to access NWS open data.\"\n  tags:\n    - Weather\n    - Government\n    - Monitoring\n    - Alerts\n    - Forecasting\n    - United States\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEATHER_GOV_USER_AGENT: WEATHER_GOV_USER_AGENT\n\ncapability:\n  consumes:\n    - import: weather-gov\n      location: ./shared/weather-gov-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: weather-monitoring-api\n      description: \"Unified REST API for weather monitoring using NWS open data.\"\n      resources:\n        - path: /v1/alerts\n          name: alerts\n          description: \"Weather alerts and warnings\"\n          operations:\n\
  \            - method: GET\n              name: list-alerts\n              description: \"List all weather alerts\"\n              call: \"weather-gov.alerts-query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alerts/active\n          name: active-alerts\n          description: \"Active weather alerts\"\n          operations:\n            - method: GET\n              name: list-active-alerts\n              description: \"List currently active weather alerts\"\n              call: \"weather-gov.alerts-active\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alerts/active/count\n          name: alert-count\n          description: \"Count of active alerts\"\n          operations:\n            - method: GET\n              name: get-alert-count\n              description: \"Get count of active alerts\"\n              call: \"weather-gov.alerts-active-count\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/forecasts\n          name: forecasts\n          description: \"Weather forecasts by grid point\"\n          operations:\n            - method: GET\n              name: get-forecast\n              description: \"Get forecast for a grid point\"\n              call: \"weather-gov.gridpoint-forecast\"\n              with:\n                wfo: \"rest.wfo\"\n                x: \"rest.x\"\n                y: \"rest.y\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/forecasts/hourly\n          name: hourly-forecasts\n          description: \"Hourly weather forecasts\"\n          operations:\n            - method: GET\n              name: get-hourly-forecast\n              description: \"Get hourly forecast for a grid point\"\n              call: \"weather-gov.gridpoint-forecast-hourly\"\n           \
  \   with:\n                wfo: \"rest.wfo\"\n                x: \"rest.x\"\n                y: \"rest.y\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/points/{point}\n          name: points\n          description: \"Location metadata lookup\"\n          operations:\n            - method: GET\n              name: get-point\n              description: \"Get metadata for a lat/lon point\"\n              call: \"weather-gov.point\"\n              with:\n                point: \"rest.point\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stations\n          name: stations\n          description: \"Observation stations\"\n          operations:\n            - method: GET\n              name: list-stations\n              description: \"List observation stations\"\n              call: \"weather-gov.obs-stations\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stations/{stationId}/observations/latest\n          name: latest-observation\n          description: \"Latest station observation\"\n          operations:\n            - method: GET\n              name: get-latest-observation\n              description: \"Get latest observation for a station\"\n              call: \"weather-gov.station-observation-latest\"\n              with:\n                stationId: \"rest.stationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/radar-stations\n          name: radar-stations\n          description: \"Radar stations\"\n          operations:\n            - method: GET\n              name: list-radar-stations\n              description: \"List radar stations\"\n              call: \"weather-gov.radar-stations\"\n              outputParameters:\n                - type: object\n            \
  \      mapping: \"$.\"\n        - path: /v1/zones\n          name: zones\n          description: \"NWS forecast zones\"\n          operations:\n            - method: GET\n              name: list-zones\n              description: \"List NWS forecast zones\"\n              call: \"weather-gov.zone-list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products\n          name: products\n          description: \"NWS text products\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"List NWS text products\"\n              call: \"weather-gov.products-query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/aviation/sigmets\n          name: sigmets\n          description: \"Aviation weather advisories\"\n          operations:\n            - method: GET\n              name: list-sigmets\n\
  \              description: \"List SIGMET/AIRMET advisories\"\n              call: \"weather-gov.sigmet-query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: weather-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted weather monitoring using NWS open data.\"\n      tools:\n        - name: list-alerts\n          description: \"List weather alerts from the National Weather Service\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.alerts-query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-active-alerts\n          description: \"List currently active NWS weather alerts\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.alerts-active\"\n          outputParameters:\n    \
  \        - type: object\n              mapping: \"$.\"\n        - name: get-alerts-by-area\n          description: \"Get active alerts for a specific state or marine area\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.alerts-active-area\"\n          with:\n            area: \"tools.area\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-alerts-by-zone\n          description: \"Get active alerts for a specific NWS zone\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.alerts-active-zone\"\n          with:\n            zoneId: \"tools.zoneId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-point-metadata\n          description: \"Get forecast metadata for a latitude/longitude location\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"weather-gov.point\"\n          with:\n            point: \"tools.point\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-forecast\n          description: \"Get weather forecast for a grid point\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.gridpoint-forecast\"\n          with:\n            wfo: \"tools.wfo\"\n            x: \"tools.x\"\n            y: \"tools.y\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-hourly-forecast\n          description: \"Get hourly weather forecast for a grid point\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.gridpoint-forecast-hourly\"\n          with:\n            wfo: \"tools.wfo\"\n            x: \"tools.x\"\n            y: \"tools.y\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: list-stations\n          description: \"List NWS weather observation stations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.obs-stations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-latest-observation\n          description: \"Get the latest weather observation from a station\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.station-observation-latest\"\n          with:\n            stationId: \"tools.stationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-observations\n          description: \"Get historical observations from a weather station\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.station-observation-list\"\n   \
  \       with:\n            stationId: \"tools.stationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-radar-stations\n          description: \"List NWS radar stations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.radar-stations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-zone-forecast\n          description: \"Get the forecast for a NWS forecast zone\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.zone-forecast\"\n          with:\n            type: \"tools.type\"\n            zoneId: \"tools.zoneId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-zones\n          description: \"List NWS forecast zones, optionally filtered by area or type\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"weather-gov.zone-list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-text-products\n          description: \"Query NWS text weather products\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.products-query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sigmets\n          description: \"List SIGMET/AIRMET aviation weather advisories\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.sigmet-query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-office-info\n          description: \"Get information about a NWS forecast office\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.office\"\
  \n          with:\n            officeId: \"tools.officeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-office-headlines\n          description: \"Get news headlines from a NWS forecast office\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"weather-gov.office-headlines\"\n          with:\n            officeId: \"tools.officeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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

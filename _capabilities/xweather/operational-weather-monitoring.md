---
categories: []
consumed_apis: []
description: Continuously monitor a portfolio of operational sites for weather risk by combining Xweather conditions, forecasts, and severe-weather alerts. Designed for an Operations Manager who needs to make go/no-go and contingency decisions across many locations.
layout: capability
name: Operational Weather Monitoring
operations: []
personas: []
provider_name: Xweather
provider_slug: xweather
search_terms:
- get forecast for a site.
- get_site_conditions
- get current conditions for a site.
- data
- observations
- operations manager
- lightning
- get severe weather alerts for a site.
- alerts
- get_site_alerts
- company
- maritime
- severe weather
- get_site_forecast
- weather
- air quality
- forecasts
slug: operational-weather-monitoring
source_filename: operational-weather-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Operational Weather Monitoring\n  description: Continuously monitor a portfolio of operational sites for weather risk by combining Xweather conditions, forecasts,\n    and severe-weather alerts. Designed for an Operations Manager who needs to make go/no-go and contingency decisions across\n    many locations.\n  tags:\n  - Operations Manager\n  - Weather\n  - Forecasts\n  - Severe Weather\n  - Alerts\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    XWEATHER_CLIENT_ID: XWEATHER_CLIENT_ID\n    XWEATHER_CLIENT_SECRET: XWEATHER_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: xweather-weather-api\n    baseUri: https://data.api.xweather.com\n    description: Xweather Weather API base endpoint.\n    authentication:\n      type: query\n      parameters:\n      - name: client_id\n        value: '{{env.XWEATHER_CLIENT_ID}}'\n      - name: client_secret\n        value: '{{env.XWEATHER_CLIENT_SECRET}}'\n\
  \    resources:\n    - name: conditions\n      path: /conditions\n      description: Current and historical surface weather conditions.\n      operations:\n      - name: get-conditions\n        method: GET\n        path: /conditions/{location}\n        description: Get current weather conditions for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n          description: Location identifier (ZIP, city/state, lat/long, place, station).\n        - name: fields\n          in: query\n          type: string\n          required: false\n        - name: filter\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n    - name: forecasts\n      path: /forecasts\n      description: Hourly and daily weather forecasts.\n      operations:\n      - name: get-forecasts\n    \
  \    method: GET\n        path: /forecasts/{location}\n        description: Get forecast records for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n    - name: alerts\n      path: /alerts\n      description: Severe weather alerts and warnings.\n      operations:\n      - name: get-alerts\n        method: GET\n        path: /alerts/{location}\n        description: Get active severe weather alerts for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n    - name: lightning\n\
  \      path: /lightning\n      description: Lightning strike events and threat nowcasts.\n      operations:\n      - name: get-lightning\n        method: GET\n        path: /lightning/{location}\n        description: Get recent lightning strike events near a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: from\n          in: query\n          type: string\n          required: false\n        - name: to\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n      - name: get-lightning-threats\n        method: GET\n        path: /lightning/threats/{location}\n        description: Get lightning threat nowcast for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n  \
  \      outputRawFormat: json\n    - name: air-quality\n      path: /airquality\n      description: Air quality index and pollutant data.\n      operations:\n      - name: get-air-quality\n        method: GET\n        path: /airquality/{location}\n        description: Get current air quality and primary pollutant for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n    - name: observations\n      path: /observations\n      description: Reports from individual surface weather stations.\n      operations:\n      - name: get-observations\n        method: GET\n        path: /observations/{location}\n        description: Get the most recent observation from a station near the location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n \
  \         required: false\n        outputRawFormat: json\n    - name: fires\n      path: /fires\n      description: Active wildfire incidents.\n      operations:\n      - name: get-wildfires\n        method: GET\n        path: /fires/{location}\n        description: Get active wildfires near a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n    - name: tropical\n      path: /tropicalcyclones\n      description: Tropical cyclone tracks and intensities.\n      operations:\n      - name: list-tropical-cyclones\n        method: GET\n        path: /tropicalcyclones\n        description: List currently active tropical cyclones globally.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n\
  \    - name: maritime\n      path: /maritime\n      description: Marine and ocean weather conditions.\n      operations:\n      - name: get-maritime-conditions\n        method: GET\n        path: /maritime/{location}\n        description: Get marine weather conditions (waves, swell, SST) for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n  exposes:\n  - type: http\n    namespace: weather-monitoring\n    paths:\n    - path: /sites/{location}/conditions\n      method: GET\n      summary: Get Site Conditions\n      description: Get current conditions for a monitored site.\n      calls:\n      - capability: xweather-weather-api.conditions.get-conditions\n        parameters:\n          location: '{location}'\n    - path: /sites/{location}/forecast\n      method: GET\n      summary: Get Site Forecast\n      description: Get the forecast for a monitored site.\n      calls:\n\
  \      - capability: xweather-weather-api.forecasts.get-forecasts\n        parameters:\n          location: '{location}'\n    - path: /sites/{location}/alerts\n      method: GET\n      summary: Get Site Alerts\n      description: Get active severe weather alerts for a monitored site.\n      calls:\n      - capability: xweather-weather-api.alerts.get-alerts\n        parameters:\n          location: '{location}'\n  - type: mcp\n    namespace: weather-monitoring\n    tools:\n    - name: get_site_conditions\n      description: Get current conditions for a site.\n      calls:\n      - capability: xweather-weather-api.conditions.get-conditions\n    - name: get_site_forecast\n      description: Get forecast for a site.\n      calls:\n      - capability: xweather-weather-api.forecasts.get-forecasts\n    - name: get_site_alerts\n      description: Get severe weather alerts for a site.\n      calls:\n      - capability: xweather-weather-api.alerts.get-alerts\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/xweather/refs/heads/main/capabilities/operational-weather-monitoring.yaml
tags:
- Operations Manager
- Weather
- Forecasts
- Severe Weather
- Alerts
tools:
- description: Get current conditions for a site.
  hints: {}
  name: get_site_conditions
- description: Get forecast for a site.
  hints: {}
  name: get_site_forecast
- description: Get severe weather alerts for a site.
  hints: {}
  name: get_site_alerts
---

---
api_specs:
- filename: xweather-weather-api-openapi.yml
  format: yaml
  label: xweather-weather-api
  slug: xweather-weather-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/xweather/refs/heads/main/openapi/xweather-weather-api-openapi.yml
categories: []
consumed_apis:
- xweather-weather-api
description: Continuously monitor a portfolio of operational sites for weather risk by combining Xweather conditions, forecasts, and severe-weather alerts. Designed for an Operations Manager who needs to make go/no-go and contingency decisions across many locations.
layout: capability
name: Operational Weather Monitoring
operations: []
personas: []
provider_name: Xweather
provider_slug: xweather
search_terms:
- alerts
- observations
- company
- get_site_alerts
- air quality
- data
- operations manager
- get_site_forecast
- get forecast for a site.
- maritime
- weather
- get severe weather alerts for a site.
- forecasts
- get current conditions for a site.
- get_site_conditions
- lightning
- severe weather
slug: operational-weather-monitoring
source_filename: operational-weather-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Operational Weather Monitoring\"\n  description: >-\n    Continuously monitor a portfolio of operational sites for weather risk by combining\n    Xweather conditions, forecasts, and severe-weather alerts. Designed for an Operations\n    Manager who needs to make go/no-go and contingency decisions across many locations.\n  tags:\n    - Operations Manager\n    - Weather\n    - Forecasts\n    - Severe Weather\n    - Alerts\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      XWEATHER_CLIENT_ID: XWEATHER_CLIENT_ID\n      XWEATHER_CLIENT_SECRET: XWEATHER_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: xweather-weather-api\n      location: ./shared/xweather-weather-api.yaml\n\n  exposes:\n    - type: http\n      namespace: weather-monitoring\n      paths:\n        - path: /sites/{location}/conditions\n          method: GET\n          summary: Get Site Conditions\n          description:\
  \ Get current conditions for a monitored site.\n          calls:\n            - capability: xweather-weather-api.conditions.get-conditions\n              parameters:\n                location: \"{location}\"\n\n        - path: /sites/{location}/forecast\n          method: GET\n          summary: Get Site Forecast\n          description: Get the forecast for a monitored site.\n          calls:\n            - capability: xweather-weather-api.forecasts.get-forecasts\n              parameters:\n                location: \"{location}\"\n\n        - path: /sites/{location}/alerts\n          method: GET\n          summary: Get Site Alerts\n          description: Get active severe weather alerts for a monitored site.\n          calls:\n            - capability: xweather-weather-api.alerts.get-alerts\n              parameters:\n                location: \"{location}\"\n\n    - type: mcp\n      namespace: weather-monitoring\n      tools:\n        - name: get_site_conditions\n          description:\
  \ Get current conditions for a site.\n          calls:\n            - capability: xweather-weather-api.conditions.get-conditions\n        - name: get_site_forecast\n          description: Get forecast for a site.\n          calls:\n            - capability: xweather-weather-api.forecasts.get-forecasts\n        - name: get_site_alerts\n          description: Get severe weather alerts for a site.\n          calls:\n            - capability: xweather-weather-api.alerts.get-alerts\n"
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

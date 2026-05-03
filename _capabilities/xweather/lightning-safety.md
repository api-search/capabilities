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
description: Drive automated stop-work and all-clear decisions for outdoor operations using Xweather lightning strike events and lightning threat nowcasts. Designed for a Safety Officer responsible for outdoor worker and public safety.
layout: capability
name: Lightning Safety Automation
operations: []
personas: []
provider_name: Xweather
provider_slug: xweather
search_terms:
- operations
- observations
- company
- get_threat_nowcast
- get_recent_strikes
- list recent lightning strikes near a site.
- air quality
- data
- maritime
- get the lightning threat nowcast for a site.
- weather
- forecasts
- safety officer
- lightning
- severe weather
slug: lightning-safety
source_filename: lightning-safety.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Lightning Safety Automation\"\n  description: >-\n    Drive automated stop-work and all-clear decisions for outdoor operations using\n    Xweather lightning strike events and lightning threat nowcasts. Designed for a\n    Safety Officer responsible for outdoor worker and public safety.\n  tags:\n    - Safety Officer\n    - Lightning\n    - Severe Weather\n    - Operations\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      XWEATHER_CLIENT_ID: XWEATHER_CLIENT_ID\n      XWEATHER_CLIENT_SECRET: XWEATHER_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: xweather-weather-api\n      location: ./shared/xweather-weather-api.yaml\n\n  exposes:\n    - type: http\n      namespace: lightning-safety\n      paths:\n        - path: /sites/{location}/lightning/strikes\n          method: GET\n          summary: Get Recent Lightning Strikes\n          description: Recent cloud-to-ground strikes\
  \ near a monitored site.\n          calls:\n            - capability: xweather-weather-api.lightning.get-lightning\n              parameters:\n                location: \"{location}\"\n\n        - path: /sites/{location}/lightning/threat\n          method: GET\n          summary: Get Lightning Threat Nowcast\n          description: Probabilistic short-term lightning threat for a site.\n          calls:\n            - capability: xweather-weather-api.lightning.get-lightning-threats\n              parameters:\n                location: \"{location}\"\n\n    - type: mcp\n      namespace: lightning-safety\n      tools:\n        - name: get_recent_strikes\n          description: List recent lightning strikes near a site.\n          calls:\n            - capability: xweather-weather-api.lightning.get-lightning\n        - name: get_threat_nowcast\n          description: Get the lightning threat nowcast for a site.\n          calls:\n            - capability: xweather-weather-api.lightning.get-lightning-threats\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/xweather/refs/heads/main/capabilities/lightning-safety.yaml
tags:
- Safety Officer
- Lightning
- Severe Weather
- Operations
tools:
- description: List recent lightning strikes near a site.
  hints: {}
  name: get_recent_strikes
- description: Get the lightning threat nowcast for a site.
  hints: {}
  name: get_threat_nowcast
---

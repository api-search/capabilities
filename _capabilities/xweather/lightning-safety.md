---
categories: []
consumed_apis: []
description: Drive automated stop-work and all-clear decisions for outdoor operations using Xweather lightning strike events and lightning threat nowcasts. Designed for a Safety Officer responsible for outdoor worker and public safety.
layout: capability
name: Lightning Safety Automation
operations: []
personas: []
provider_name: Xweather
provider_slug: xweather
search_terms:
- lightning
- operations
- forecasts
- maritime
- list recent lightning strikes near a site.
- data
- get the lightning threat nowcast for a site.
- observations
- safety officer
- weather
- get_threat_nowcast
- company
- get_recent_strikes
- severe weather
- air quality
slug: lightning-safety
source_filename: lightning-safety.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Lightning Safety Automation\n  description: Drive automated stop-work and all-clear decisions for outdoor operations using Xweather lightning strike events\n    and lightning threat nowcasts. Designed for a Safety Officer responsible for outdoor worker and public safety.\n  tags:\n  - Safety Officer\n  - Lightning\n  - Severe Weather\n  - Operations\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    XWEATHER_CLIENT_ID: XWEATHER_CLIENT_ID\n    XWEATHER_CLIENT_SECRET: XWEATHER_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: xweather-weather-api\n    baseUri: https://data.api.xweather.com\n    description: Xweather Weather API base endpoint.\n    authentication:\n      type: query\n      parameters:\n      - name: client_id\n        value: '{{env.XWEATHER_CLIENT_ID}}'\n      - name: client_secret\n        value: '{{env.XWEATHER_CLIENT_SECRET}}'\n    resources:\n    - name: conditions\n\
  \      path: /conditions\n      description: Current and historical surface weather conditions.\n      operations:\n      - name: get-conditions\n        method: GET\n        path: /conditions/{location}\n        description: Get current weather conditions for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n          description: Location identifier (ZIP, city/state, lat/long, place, station).\n        - name: fields\n          in: query\n          type: string\n          required: false\n        - name: filter\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n    - name: forecasts\n      path: /forecasts\n      description: Hourly and daily weather forecasts.\n      operations:\n      - name: get-forecasts\n        method: GET\n        path: /forecasts/{location}\n\
  \        description: Get forecast records for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n    - name: alerts\n      path: /alerts\n      description: Severe weather alerts and warnings.\n      operations:\n      - name: get-alerts\n        method: GET\n        path: /alerts/{location}\n        description: Get active severe weather alerts for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n    - name: lightning\n      path: /lightning\n      description: Lightning strike\
  \ events and threat nowcasts.\n      operations:\n      - name: get-lightning\n        method: GET\n        path: /lightning/{location}\n        description: Get recent lightning strike events near a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: from\n          in: query\n          type: string\n          required: false\n        - name: to\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n      - name: get-lightning-threats\n        method: GET\n        path: /lightning/threats/{location}\n        description: Get lightning threat nowcast for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n    - name: air-quality\n     \
  \ path: /airquality\n      description: Air quality index and pollutant data.\n      operations:\n      - name: get-air-quality\n        method: GET\n        path: /airquality/{location}\n        description: Get current air quality and primary pollutant for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n    - name: observations\n      path: /observations\n      description: Reports from individual surface weather stations.\n      operations:\n      - name: get-observations\n        method: GET\n        path: /observations/{location}\n        description: Get the most recent observation from a station near the location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n  \
  \  - name: fires\n      path: /fires\n      description: Active wildfire incidents.\n      operations:\n      - name: get-wildfires\n        method: GET\n        path: /fires/{location}\n        description: Get active wildfires near a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n    - name: tropical\n      path: /tropicalcyclones\n      description: Tropical cyclone tracks and intensities.\n      operations:\n      - name: list-tropical-cyclones\n        method: GET\n        path: /tropicalcyclones\n        description: List currently active tropical cyclones globally.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n    - name: maritime\n      path: /maritime\n      description:\
  \ Marine and ocean weather conditions.\n      operations:\n      - name: get-maritime-conditions\n        method: GET\n        path: /maritime/{location}\n        description: Get marine weather conditions (waves, swell, SST) for a location.\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n  exposes:\n  - type: http\n    namespace: lightning-safety\n    paths:\n    - path: /sites/{location}/lightning/strikes\n      method: GET\n      summary: Get Recent Lightning Strikes\n      description: Recent cloud-to-ground strikes near a monitored site.\n      calls:\n      - capability: xweather-weather-api.lightning.get-lightning\n        parameters:\n          location: '{location}'\n    - path: /sites/{location}/lightning/threat\n      method: GET\n      summary: Get Lightning Threat Nowcast\n      description: Probabilistic short-term lightning threat for a site.\n      calls:\n      - capability:\
  \ xweather-weather-api.lightning.get-lightning-threats\n        parameters:\n          location: '{location}'\n  - type: mcp\n    namespace: lightning-safety\n    tools:\n    - name: get_recent_strikes\n      description: List recent lightning strikes near a site.\n      calls:\n      - capability: xweather-weather-api.lightning.get-lightning\n    - name: get_threat_nowcast\n      description: Get the lightning threat nowcast for a site.\n      calls:\n      - capability: xweather-weather-api.lightning.get-lightning-threats\n"
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

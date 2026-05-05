---
api_specs:
- filename: stormglass-openapi.yml
  format: yaml
  label: stormglass
  slug: stormglass
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/stormglass/refs/heads/main/openapi/stormglass-openapi.yml
categories: []
consumed_apis:
- stormglass
description: Unified capability for accessing global marine and weather data from Stormglass. Combines weather forecasts, marine conditions, tidal data, astronomical events, solar radiation, biological oceanographic measurements, and elevation data for any coordinate on Earth. Used by maritime operators, renewable energy developers, outdoor activity platforms, and environmental monitoring applications.
layout: capability
name: Stormglass Marine and Weather Intelligence
operations:
- description: Get hourly weather forecast for a coordinate
  method: GET
  name: get-weather
  path: /v1/weather
- description: Get marine environment data including waves and currents
  method: GET
  name: get-marine
  path: /v1/marine
- description: Get high and low tide events
  method: GET
  name: get-tide-extremes
  path: /v1/tides
- description: Get hourly sea level relative to datum
  method: GET
  name: get-sea-level
  path: /v1/sea-level
- description: List all available tide stations
  method: GET
  name: list-tide-stations
  path: /v1/tide-stations
- description: Get sunrise, sunset, and moon data
  method: GET
  name: get-astronomy
  path: /v1/astronomy
- description: Get UV index and solar radiation data
  method: GET
  name: get-solar
  path: /v1/solar
- description: Get chlorophyll, oxygen, and nutrient data
  method: GET
  name: get-bio
  path: /v1/bio
- description: Get land elevation or ocean depth
  method: GET
  name: get-elevation
  path: /v1/elevation
personas: []
provider_name: Stormglass
provider_slug: stormglass
search_terms:
- list all available tide monitoring stations globally
- get high and low tide events
- marine environment conditions
- get solar radiation
- astronomy
- get chlorophyll, oxygen, and nutrient data
- 'get astronomical data for any location: sunrise, sunset, moonrise, moonset, moon phase, civil/nautical/astronomical dawn and dusk.'
- get land elevation or ocean depth
- tidal forecast data
- tide monitoring stations
- get biological and oceanographic data for marine research. returns chlorophyll, dissolved oxygen, salinity, ph, nutrients, and phytoplankton data.
- retrieve hourly atmospheric weather forecast for any global coordinate. returns temperature, wind, humidity, pressure, cloud cover, and precipitation.
- wind
- list tide stations
- solar radiation data
- forecasting
- get hourly sea level relative to datum
- ocean
- get predicted high tide and low tide events for a coastal location. returns tide timestamps, heights, and tide type (high/low).
- bio
- get weather
- get marine
- solar
- retrieve marine environment data for any ocean coordinate. returns wave height, wave direction, swell, water temperature, and currents.
- biological oceanographic data
- astronomical event data
- get bio ocean data
- get solar
- list all available tide stations
- get hourly sea level height for coastal planning and navigation
- topographic and bathymetric elevation data
- marine
- elevation
- get bio
- get land elevation or ocean depth (bathymetry) for any coordinate. positive values indicate land elevation; negative values indicate ocean depth in meters.
- climate
- tides
- get elevation
- get sea level
- get hourly weather forecast for a coordinate
- retrieve solar radiation data including uv index and downward short-wave radiation flux for any location. useful for solar energy assessment and uv exposure planning.
- get weather forecast
- get marine environment data including waves and currents
- get tide extremes
- atmospheric weather forecast data
- get uv index and solar radiation data
- hourly sea level data
- get astronomy
- get marine conditions
- weather
- get sunrise, sunset, and moon data
slug: marine-weather
source_filename: marine-weather.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Stormglass Marine and Weather Intelligence\"\n  description: >-\n    Unified capability for accessing global marine and weather data from Stormglass.\n    Combines weather forecasts, marine conditions, tidal data, astronomical events,\n    solar radiation, biological oceanographic measurements, and elevation data for\n    any coordinate on Earth. Used by maritime operators, renewable energy developers,\n    outdoor activity platforms, and environmental monitoring applications.\n  tags:\n    - Astronomy\n    - Bio\n    - Elevation\n    - Forecasting\n    - Marine\n    - Solar\n    - Tides\n    - Weather\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STORMGLASS_API_KEY: STORMGLASS_API_KEY\n\ncapability:\n  consumes:\n    - import: stormglass\n      location: ./shared/stormglass.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: marine-weather-api\n    \
  \  description: \"Unified REST API for marine and weather intelligence.\"\n      resources:\n        - path: /v1/weather\n          name: weather\n          description: \"Atmospheric weather forecast data\"\n          operations:\n            - method: GET\n              name: get-weather\n              description: \"Get hourly weather forecast for a coordinate\"\n              call: \"stormglass.get-weather-point\"\n              with:\n                lat: \"rest.lat\"\n                lng: \"rest.lng\"\n                params: \"rest.params\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/marine\n          name: marine\n          description: \"Marine environment conditions\"\n          operations:\n            - method: GET\n              name: get-marine\n              description: \"Get marine environment data including waves and\
  \ currents\"\n              call: \"stormglass.get-marine-point\"\n              with:\n                lat: \"rest.lat\"\n                lng: \"rest.lng\"\n                params: \"rest.params\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tides\n          name: tides\n          description: \"Tidal forecast data\"\n          operations:\n            - method: GET\n              name: get-tide-extremes\n              description: \"Get high and low tide events\"\n              call: \"stormglass.get-tide-extremes\"\n              with:\n                lat: \"rest.lat\"\n                lng: \"rest.lng\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sea-level\n          name: sea-level\n          description: \"Hourly sea level data\"\n          operations:\n\
  \            - method: GET\n              name: get-sea-level\n              description: \"Get hourly sea level relative to datum\"\n              call: \"stormglass.get-tide-sea-level\"\n              with:\n                lat: \"rest.lat\"\n                lng: \"rest.lng\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tide-stations\n          name: tide-stations\n          description: \"Tide monitoring stations\"\n          operations:\n            - method: GET\n              name: list-tide-stations\n              description: \"List all available tide stations\"\n              call: \"stormglass.get-tide-stations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/astronomy\n          name: astronomy\n          description: \"Astronomical event data\"\n          operations:\n            - method: GET\n              name: get-astronomy\n\
  \              description: \"Get sunrise, sunset, and moon data\"\n              call: \"stormglass.get-astronomy-point\"\n              with:\n                lat: \"rest.lat\"\n                lng: \"rest.lng\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/solar\n          name: solar\n          description: \"Solar radiation data\"\n          operations:\n            - method: GET\n              name: get-solar\n              description: \"Get UV index and solar radiation data\"\n              call: \"stormglass.get-solar-point\"\n              with:\n                lat: \"rest.lat\"\n                lng: \"rest.lng\"\n                params: \"rest.params\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bio\n          name: bio\n          description: \"Biological\
  \ oceanographic data\"\n          operations:\n            - method: GET\n              name: get-bio\n              description: \"Get chlorophyll, oxygen, and nutrient data\"\n              call: \"stormglass.get-bio-point\"\n              with:\n                lat: \"rest.lat\"\n                lng: \"rest.lng\"\n                params: \"rest.params\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/elevation\n          name: elevation\n          description: \"Topographic and bathymetric elevation data\"\n          operations:\n            - method: GET\n              name: get-elevation\n              description: \"Get land elevation or ocean depth\"\n              call: \"stormglass.get-elevation-point\"\n              with:\n                lat: \"rest.lat\"\n                lng: \"rest.lng\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type:\
  \ mcp\n      port: 9090\n      namespace: marine-weather-mcp\n      transport: http\n      description: \"MCP server for AI-assisted marine and weather intelligence.\"\n      tools:\n        - name: get-weather-forecast\n          description: >-\n            Retrieve hourly atmospheric weather forecast for any global coordinate.\n            Returns temperature, wind, humidity, pressure, cloud cover, and precipitation.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stormglass.get-weather-point\"\n          with:\n            lat: \"tools.lat\"\n            lng: \"tools.lng\"\n            params: \"tools.params\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-marine-conditions\n          description: >-\n            Retrieve marine environment data for any ocean coordinate.\n            Returns wave height, wave\
  \ direction, swell, water temperature, and currents.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stormglass.get-marine-point\"\n          with:\n            lat: \"tools.lat\"\n            lng: \"tools.lng\"\n            params: \"tools.params\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-tide-extremes\n          description: >-\n            Get predicted high tide and low tide events for a coastal location.\n            Returns tide timestamps, heights, and tide type (high/low).\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stormglass.get-tide-extremes\"\n          with:\n            lat: \"tools.lat\"\n            lng: \"tools.lng\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n            datum: \"tools.datum\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \n        - name: get-sea-level\n          description: \"Get hourly sea level height for coastal planning and navigation\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stormglass.get-tide-sea-level\"\n          with:\n            lat: \"tools.lat\"\n            lng: \"tools.lng\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-tide-stations\n          description: \"List all available tide monitoring stations globally\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"stormglass.get-tide-stations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-astronomy\n          description: >-\n            Get astronomical data for any location: sunrise, sunset, moonrise,\n            moonset, moon phase, civil/nautical/astronomical\
  \ dawn and dusk.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stormglass.get-astronomy-point\"\n          with:\n            lat: \"tools.lat\"\n            lng: \"tools.lng\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-solar-radiation\n          description: >-\n            Retrieve solar radiation data including UV index and downward\n            short-wave radiation flux for any location. Useful for solar energy\n            assessment and UV exposure planning.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stormglass.get-solar-point\"\n          with:\n            lat: \"tools.lat\"\n            lng: \"tools.lng\"\n            params: \"tools.params\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ get-bio-ocean-data\n          description: >-\n            Get biological and oceanographic data for marine research.\n            Returns chlorophyll, dissolved oxygen, salinity, pH, nutrients,\n            and phytoplankton data.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stormglass.get-bio-point\"\n          with:\n            lat: \"tools.lat\"\n            lng: \"tools.lng\"\n            params: \"tools.params\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-elevation\n          description: >-\n            Get land elevation or ocean depth (bathymetry) for any coordinate.\n            Positive values indicate land elevation; negative values indicate\n            ocean depth in meters.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stormglass.get-elevation-point\"\n          with:\n            lat: \"tools.lat\"\n     \
  \       lng: \"tools.lng\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stormglass/refs/heads/main/capabilities/marine-weather.yaml
tags:
- Astronomy
- Bio
- Elevation
- Forecasting
- Marine
- Solar
- Tides
- Weather
tools:
- description: Retrieve hourly atmospheric weather forecast for any global coordinate. Returns temperature, wind, humidity, pressure, cloud cover, and precipitation.
  hints:
    openWorld: true
    readOnly: true
  name: get-weather-forecast
- description: Retrieve marine environment data for any ocean coordinate. Returns wave height, wave direction, swell, water temperature, and currents.
  hints:
    openWorld: true
    readOnly: true
  name: get-marine-conditions
- description: Get predicted high tide and low tide events for a coastal location. Returns tide timestamps, heights, and tide type (high/low).
  hints:
    openWorld: true
    readOnly: true
  name: get-tide-extremes
- description: Get hourly sea level height for coastal planning and navigation
  hints:
    openWorld: true
    readOnly: true
  name: get-sea-level
- description: List all available tide monitoring stations globally
  hints:
    openWorld: false
    readOnly: true
  name: list-tide-stations
- description: 'Get astronomical data for any location: sunrise, sunset, moonrise, moonset, moon phase, civil/nautical/astronomical dawn and dusk.'
  hints:
    openWorld: true
    readOnly: true
  name: get-astronomy
- description: Retrieve solar radiation data including UV index and downward short-wave radiation flux for any location. Useful for solar energy assessment and UV exposure planning.
  hints:
    openWorld: true
    readOnly: true
  name: get-solar-radiation
- description: Get biological and oceanographic data for marine research. Returns chlorophyll, dissolved oxygen, salinity, pH, nutrients, and phytoplankton data.
  hints:
    openWorld: true
    readOnly: true
  name: get-bio-ocean-data
- description: Get land elevation or ocean depth (bathymetry) for any coordinate. Positive values indicate land elevation; negative values indicate ocean depth in meters.
  hints:
    openWorld: true
    readOnly: true
  name: get-elevation
---

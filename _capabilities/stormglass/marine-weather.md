---
categories: []
consumed_apis: []
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
- retrieve marine environment data for any ocean coordinate. returns wave height, wave direction, swell, water temperature, and currents.
- biological oceanographic data
- marine environment conditions
- tide monitoring stations
- get high and low tide events
- get astronomy
- get marine conditions
- list tide stations
- get land elevation or ocean depth (bathymetry) for any coordinate. positive values indicate land elevation; negative values indicate ocean depth in meters.
- get chlorophyll, oxygen, and nutrient data
- solar radiation data
- astronomy
- get elevation
- tidal forecast data
- list all available tide stations
- ocean
- weather
- get marine
- get marine environment data including waves and currents
- get hourly sea level relative to datum
- marine
- get predicted high tide and low tide events for a coastal location. returns tide timestamps, heights, and tide type (high/low).
- get solar
- topographic and bathymetric elevation data
- get biological and oceanographic data for marine research. returns chlorophyll, dissolved oxygen, salinity, ph, nutrients, and phytoplankton data.
- get weather
- get bio ocean data
- get hourly weather forecast for a coordinate
- forecasting
- elevation
- get sunrise, sunset, and moon data
- get solar radiation
- get bio
- get weather forecast
- hourly sea level data
- wind
- astronomical event data
- climate
- atmospheric weather forecast data
- get hourly sea level height for coastal planning and navigation
- tides
- get land elevation or ocean depth
- get sea level
- bio
- 'get astronomical data for any location: sunrise, sunset, moonrise, moonset, moon phase, civil/nautical/astronomical dawn and dusk.'
- retrieve hourly atmospheric weather forecast for any global coordinate. returns temperature, wind, humidity, pressure, cloud cover, and precipitation.
- list all available tide monitoring stations globally
- get uv index and solar radiation data
- retrieve solar radiation data including uv index and downward short-wave radiation flux for any location. useful for solar energy assessment and uv exposure planning.
- get tide extremes
- solar
slug: marine-weather
source_filename: marine-weather.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stormglass Marine and Weather Intelligence\n  description: Unified capability for accessing global marine and weather data from Stormglass. Combines weather forecasts,\n    marine conditions, tidal data, astronomical events, solar radiation, biological oceanographic measurements, and elevation\n    data for any coordinate on Earth. Used by maritime operators, renewable energy developers, outdoor activity platforms,\n    and environmental monitoring applications.\n  tags:\n  - Astronomy\n  - Bio\n  - Elevation\n  - Forecasting\n  - Marine\n  - Solar\n  - Tides\n  - Weather\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STORMGLASS_API_KEY: STORMGLASS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stormglass\n    baseUri: https://api.stormglass.io/v2\n    description: Global marine and weather data API\n    authentication:\n      type: apikey\n      key: Authorization\n      value:\
  \ '{{STORMGLASS_API_KEY}}'\n      placement: header\n    resources:\n    - name: weather\n      path: /weather\n      description: Atmospheric weather forecast data\n      operations:\n      - name: get-weather-point\n        method: GET\n        description: Retrieve hourly weather forecast for a coordinate\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude of the coordinate\n        - name: lng\n          in: query\n          type: number\n          required: true\n          description: Longitude of the coordinate\n        - name: params\n          in: query\n          type: string\n          required: true\n          description: Comma-separated weather parameters\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start timestamp (UTC)\n        - name: end\n          in: query\n          type: string\n          required:\
  \ false\n          description: End timestamp (UTC)\n        - name: source\n          in: query\n          type: string\n          required: false\n          description: Data source filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: marine\n      path: /marine\n      description: Marine environment data\n      operations:\n      - name: get-marine-point\n        method: GET\n        description: Retrieve hourly marine data for a coordinate\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude of the coordinate\n        - name: lng\n          in: query\n          type: number\n          required: true\n          description: Longitude of the coordinate\n        - name: params\n          in: query\n          type: string\n          required: true\n          description: Comma-separated marine parameters\n\
  \        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start timestamp\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End timestamp\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tides\n      path: /tide\n      description: Tidal forecast and station data\n      operations:\n      - name: get-tide-extremes\n        method: GET\n        description: Retrieve high and low tide events for a coordinate\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lng\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        - name: start\n          in: query\n          type: string\n          required: false\n\
  \          description: Start date\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End date\n        - name: datum\n          in: query\n          type: string\n          required: false\n          description: 'Datum: MLLW or MSL'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-tide-sea-level\n        method: GET\n        description: Retrieve hourly sea level data for a coordinate\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lng\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start timestamp\n        - name: end\n          in:\
  \ query\n          type: string\n          required: false\n          description: End timestamp\n        - name: datum\n          in: query\n          type: string\n          required: false\n          description: 'Datum: MLLW or MSL'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-tide-stations\n        method: GET\n        description: List all available tide stations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-tide-stations-area\n        method: GET\n        description: List tide stations within a geographic bounding box\n        inputParameters:\n        - name: box\n          in: query\n          type: string\n          required: true\n          description: 'Bounding box coordinates: lat,lng:lat,lng'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: astronomy\n      path: /astronomy\n      description: Astronomical data including sunrise, sunset, and moon phases\n      operations:\n      - name: get-astronomy-point\n        method: GET\n        description: Retrieve astronomical data for a coordinate\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lng\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start date\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: solar\n     \
  \ path: /solar\n      description: Solar radiation and UV index data\n      operations:\n      - name: get-solar-point\n        method: GET\n        description: Retrieve solar radiation data for a coordinate\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lng\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        - name: params\n          in: query\n          type: string\n          required: true\n          description: Solar parameters (e.g. uvIndex)\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start timestamp\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End timestamp\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: bio\n      path: /bio\n      description: Biological and oceanographic data\n      operations:\n      - name: get-bio-point\n        method: GET\n        description: Retrieve biological oceanographic data for a coordinate\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lng\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        - name: params\n          in: query\n          type: string\n          required: true\n          description: Bio parameters (e.g. chlorophyll,oxygen)\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start timestamp\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End timestamp\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: elevation\n      path: /elevation\n      description: Global elevation and bathymetry data\n      operations:\n      - name: get-elevation-point\n        method: GET\n        description: Retrieve elevation or ocean depth for a coordinate\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lng\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: marine-weather-api\n    description: Unified REST API for marine and weather intelligence.\n    resources:\n    - path: /v1/weather\n      name: weather\n      description: Atmospheric weather\
  \ forecast data\n      operations:\n      - method: GET\n        name: get-weather\n        description: Get hourly weather forecast for a coordinate\n        call: stormglass.get-weather-point\n        with:\n          lat: rest.lat\n          lng: rest.lng\n          params: rest.params\n          start: rest.start\n          end: rest.end\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/marine\n      name: marine\n      description: Marine environment conditions\n      operations:\n      - method: GET\n        name: get-marine\n        description: Get marine environment data including waves and currents\n        call: stormglass.get-marine-point\n        with:\n          lat: rest.lat\n          lng: rest.lng\n          params: rest.params\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tides\n      name: tides\n      description: Tidal forecast data\n      operations:\n      - method: GET\n      \
  \  name: get-tide-extremes\n        description: Get high and low tide events\n        call: stormglass.get-tide-extremes\n        with:\n          lat: rest.lat\n          lng: rest.lng\n          start: rest.start\n          end: rest.end\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sea-level\n      name: sea-level\n      description: Hourly sea level data\n      operations:\n      - method: GET\n        name: get-sea-level\n        description: Get hourly sea level relative to datum\n        call: stormglass.get-tide-sea-level\n        with:\n          lat: rest.lat\n          lng: rest.lng\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tide-stations\n      name: tide-stations\n      description: Tide monitoring stations\n      operations:\n      - method: GET\n        name: list-tide-stations\n        description: List all available tide stations\n        call: stormglass.get-tide-stations\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/astronomy\n      name: astronomy\n      description: Astronomical event data\n      operations:\n      - method: GET\n        name: get-astronomy\n        description: Get sunrise, sunset, and moon data\n        call: stormglass.get-astronomy-point\n        with:\n          lat: rest.lat\n          lng: rest.lng\n          start: rest.start\n          end: rest.end\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/solar\n      name: solar\n      description: Solar radiation data\n      operations:\n      - method: GET\n        name: get-solar\n        description: Get UV index and solar radiation data\n        call: stormglass.get-solar-point\n        with:\n          lat: rest.lat\n          lng: rest.lng\n          params: rest.params\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bio\n      name: bio\n      description:\
  \ Biological oceanographic data\n      operations:\n      - method: GET\n        name: get-bio\n        description: Get chlorophyll, oxygen, and nutrient data\n        call: stormglass.get-bio-point\n        with:\n          lat: rest.lat\n          lng: rest.lng\n          params: rest.params\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/elevation\n      name: elevation\n      description: Topographic and bathymetric elevation data\n      operations:\n      - method: GET\n        name: get-elevation\n        description: Get land elevation or ocean depth\n        call: stormglass.get-elevation-point\n        with:\n          lat: rest.lat\n          lng: rest.lng\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: marine-weather-mcp\n    transport: http\n    description: MCP server for AI-assisted marine and weather intelligence.\n    tools:\n    - name: get-weather-forecast\n\
  \      description: Retrieve hourly atmospheric weather forecast for any global coordinate. Returns temperature, wind, humidity,\n        pressure, cloud cover, and precipitation.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stormglass.get-weather-point\n      with:\n        lat: tools.lat\n        lng: tools.lng\n        params: tools.params\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-marine-conditions\n      description: Retrieve marine environment data for any ocean coordinate. Returns wave height, wave direction, swell,\n        water temperature, and currents.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stormglass.get-marine-point\n      with:\n        lat: tools.lat\n        lng: tools.lng\n        params: tools.params\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tide-extremes\n      description:\
  \ Get predicted high tide and low tide events for a coastal location. Returns tide timestamps, heights, and\n        tide type (high/low).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stormglass.get-tide-extremes\n      with:\n        lat: tools.lat\n        lng: tools.lng\n        start: tools.start\n        end: tools.end\n        datum: tools.datum\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sea-level\n      description: Get hourly sea level height for coastal planning and navigation\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stormglass.get-tide-sea-level\n      with:\n        lat: tools.lat\n        lng: tools.lng\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tide-stations\n      description: List all available tide monitoring stations globally\n      hints:\n        readOnly: true\n    \
  \    openWorld: false\n      call: stormglass.get-tide-stations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-astronomy\n      description: 'Get astronomical data for any location: sunrise, sunset, moonrise, moonset, moon phase, civil/nautical/astronomical\n        dawn and dusk.'\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stormglass.get-astronomy-point\n      with:\n        lat: tools.lat\n        lng: tools.lng\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-solar-radiation\n      description: Retrieve solar radiation data including UV index and downward short-wave radiation flux for any location.\n        Useful for solar energy assessment and UV exposure planning.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stormglass.get-solar-point\n      with:\n        lat: tools.lat\n        lng: tools.lng\n\
  \        params: tools.params\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bio-ocean-data\n      description: Get biological and oceanographic data for marine research. Returns chlorophyll, dissolved oxygen, salinity,\n        pH, nutrients, and phytoplankton data.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stormglass.get-bio-point\n      with:\n        lat: tools.lat\n        lng: tools.lng\n        params: tools.params\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-elevation\n      description: Get land elevation or ocean depth (bathymetry) for any coordinate. Positive values indicate land elevation;\n        negative values indicate ocean depth in meters.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stormglass.get-elevation-point\n      with:\n        lat: tools.lat\n        lng: tools.lng\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n"
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

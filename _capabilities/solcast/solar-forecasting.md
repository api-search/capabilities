---
categories: []
consumed_apis: []
description: Workflow capability for solar energy forecasting and real-time monitoring. Combines live and forecast radiation, PV power, soiling, and grid aggregation data to support energy market bidding, dispatch optimization, and grid management. Used by energy traders, grid operators, and renewable energy portfolio managers.
layout: capability
name: Solcast Solar Forecasting
operations:
- description: Get live solar irradiance and weather data for a lat/lon location.
  method: GET
  name: get-live-radiation-and-weather
  path: /v1/live/radiation-and-weather
- description: Get live rooftop PV power estimated actuals for a location.
  method: GET
  name: get-live-rooftop-pv-power
  path: /v1/live/rooftop-pv-power
- description: Get live advanced PV power actuals for a registered site.
  method: GET
  name: get-live-advanced-pv-power
  path: /v1/live/advanced-pv-power
- description: Get live aggregation data for a grid collection or sub-aggregation.
  method: GET
  name: get-live-aggregations
  path: /v1/live/aggregations
- description: Get live soiling loss using the Kimber model.
  method: GET
  name: get-live-soiling-kimber
  path: /v1/live/soiling
- description: Get irradiance and weather forecasts up to 14 days ahead.
  method: GET
  name: get-forecast-radiation-and-weather
  path: /v1/forecast/radiation-and-weather
- description: Get rooftop PV power forecasts up to 14 days ahead.
  method: GET
  name: get-forecast-rooftop-pv-power
  path: /v1/forecast/rooftop-pv-power
- description: Get advanced PV power forecasts for a registered site.
  method: GET
  name: get-forecast-advanced-pv-power
  path: /v1/forecast/advanced-pv-power
- description: Get forecast aggregation data for a grid collection.
  method: GET
  name: get-forecast-aggregations
  path: /v1/forecast/aggregations
- description: Get soiling loss forecasts using the Kimber model.
  method: GET
  name: get-forecast-soiling-kimber
  path: /v1/forecast/soiling
personas: []
provider_name: Solcast
provider_slug: solcast
search_terms:
- advanced pv power forecasts up to 14 days ahead for registered sites.
- get soiling loss forecasts using the kimber model.
- get solar irradiance and weather forecasts up to 14 days ahead. use for energy market bidding and dispatch planning.
- get forecast soiling hsu
- aggregations
- get soiling loss forecasts using the hsu model.
- get live advanced pv power actuals for a registered site.
- pv power
- get live aggregations
- get live soiling hsu
- irradiance
- live rooftop pv power actuals.
- get live aggregated pv generation data for a grid portfolio or collection. used for grid management and large-scale monitoring.
- soiling loss forecasts for maintenance planning.
- get high-specification pv power forecasts up to 14 days ahead for a registered site.
- get live soiling kimber
- get live soiling loss using the kimber model.
- get live solar irradiance and weather data for any lat/lon location (last 7 days, updated every 5 minutes). use for real-time solar resource monitoring.
- forecast grid aggregation data for portfolio and grid management.
- real-time irradiance and weather for a location.
- forecasting
- get live radiation and weather
- get live rooftop pv power estimated actuals for a location. no site registration required.
- get live solar irradiance and weather data for a lat/lon location.
- energy market
- live grid aggregation data for portfolios and grid operators.
- get rooftop pv power forecasts up to 14 days ahead.
- get forecast soiling kimber
- get soiling loss forecasts using the kimber model. use for planning panel cleaning schedules.
- get forecast radiation and weather
- live advanced pv power actuals for registered sites.
- live data
- get forecast advanced pv power
- get irradiance and weather forecasts up to 14 days ahead.
- get live rooftop pv power
- energy
- get forecast aggregations
- renewable energy
- get live rooftop pv power estimated actuals for a location.
- get forecast aggregation data for a grid collection.
- solar
- get live advanced pv power actuals for a registered solcast site (resource_id required).
- rooftop pv power forecasts up to 14 days ahead.
- get live advanced pv power
- get rooftop pv power forecasts up to 14 days ahead. no site registration needed.
- get forecast aggregated pv generation data for a grid portfolio or collection up to 7 days ahead.
- get live aggregation data for a grid collection or sub-aggregation.
- weather
- grid management
- live soiling loss data using kimber or hsu models.
- forecast irradiance and weather up to 14 days ahead.
- get advanced pv power forecasts for a registered site.
- get live soiling loss estimates using the kimber model. use for monitoring panel cleanliness and scheduling cleaning.
- get live soiling loss estimates using solcast's hsu model.
- get forecast rooftop pv power
slug: solar-forecasting
source_filename: solar-forecasting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Solcast Solar Forecasting\n  description: Workflow capability for solar energy forecasting and real-time monitoring. Combines live and forecast radiation,\n    PV power, soiling, and grid aggregation data to support energy market bidding, dispatch optimization, and grid management.\n    Used by energy traders, grid operators, and renewable energy portfolio managers.\n  tags:\n  - Solar\n  - Forecasting\n  - PV Power\n  - Grid Management\n  - Energy Market\n  - Renewable Energy\n  - Live Data\n  - Aggregations\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SOLCAST_API_KEY: SOLCAST_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: solcast\n    baseUri: https://api.solcast.com.au\n    description: Solcast solar irradiance, PV power, weather forecasting, and site management API.\n    authentication:\n      type: bearer\n      token: '{{SOLCAST_API_KEY}}'\n    resources:\n    - name:\
  \ live-radiation-and-weather\n      path: /data/live/radiation_and_weather\n      description: Real-time satellite-derived solar irradiance and weather data for a location (last 7 days, updated every\n        5 minutes).\n      operations:\n      - name: get-live-radiation-and-weather\n        method: GET\n        description: Get live irradiance and weather estimated actuals for a lat/lon location.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees (-90 to 90, north positive).\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees (-180 to 180, east positive).\n        - name: output_parameters\n          in: query\n          type: string\n          required: true\n          description: Comma-separated output parameters (e.g., ghi,dni,dhi,air_temp).\n        - name: period\n\
  \          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601, e.g., PT30M).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-rooftop-pv-power\n      path: /data/live/rooftop_pv_power\n      description: Live rooftop PV power estimated actuals by location without site registration.\n      operations:\n      - name: get-live-rooftop-pv-power\n        method: GET\n        description: Get live rooftop PV power estimated actuals for a lat/lon location.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n\
  \          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: capacity\n          in: query\n          type: number\n          required: false\n          description: System capacity in kilowatts.\n        - name: tilt\n          in: query\n          type: number\n          required: false\n          description: Panel tilt angle in degrees.\n        - name: azimuth\n          in: query\n          type: number\n          required: false\n          description: Panel azimuth in degrees.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: live-advanced-pv-power\n      path: /data/live/advanced_pv_power\n      description: Live high-specification PV power actuals for a registered PV site.\n      operations:\n      - name: get-live-advanced-pv-power\n        method: GET\n        description: Get live advanced PV power actuals for a registered PV power site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for a registered Solcast PV power site.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-soiling-kimber\n\
  \      path: /data/live/soiling/kimber\n      description: Live hourly soiling loss estimates using the Kimber model.\n      operations:\n      - name: get-live-soiling-kimber\n        method: GET\n        description: Get live soiling loss estimates for a location using the Kimber model.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: depo_veloc_pm10\n          in: query\n          type: number\n          required: false\n          description: Deposition velocity for PM10 particles (m/s).\n        - name: initial_soiling\n          in: query\n          type: number\n          required: false\n          description: Initial soiling fraction (0.0 = clean).\n        - name: format\n          in:\
  \ query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-soiling-hsu\n      path: /data/live/soiling/hsu\n      description: Live hourly soiling loss estimates using Solcast's HSU model.\n      operations:\n      - name: get-live-soiling-hsu\n        method: GET\n        description: Get live soiling loss estimates for a location using the HSU model.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: depo_veloc_pm10\n          in: query\n          type: number\n          required: false\n         \
  \ description: Deposition velocity for PM10 particles (m/s).\n        - name: initial_soiling\n          in: query\n          type: number\n          required: false\n          description: Initial soiling fraction (0.0 = clean).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-radiation-and-weather\n      path: /data/forecast/radiation_and_weather\n      description: Solar irradiance and weather forecasts up to 14 days ahead for a location.\n      operations:\n      - name: get-forecast-radiation-and-weather\n        method: GET\n        description: Get irradiance and weather forecasts up to 14 days ahead for a lat/lon location.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required:\
  \ true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: output_parameters\n          in: query\n          type: string\n          required: true\n          description: Comma-separated output parameters.\n        - name: hours\n          in: query\n          type: integer\n          required: false\n          description: Number of forecast hours to retrieve (up to 336 / 14 days).\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: forecast-rooftop-pv-power\n      path: /data/forecast/rooftop_pv_power\n      description: Rooftop PV power forecasts up to 14 days ahead by location.\n      operations:\n      - name: get-forecast-rooftop-pv-power\n        method: GET\n        description: Get basic rooftop PV power forecasts up to 14 days ahead for a lat/lon location.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: output_parameters\n          in: query\n          type: string\n          required: true\n          description: Comma-separated output parameters.\n        - name: capacity\n          in: query\n          type: number\n          required: false\n          description: System capacity in kilowatts.\n \
  \       - name: tilt\n          in: query\n          type: number\n          required: false\n          description: Panel tilt in degrees.\n        - name: azimuth\n          in: query\n          type: number\n          required: false\n          description: Panel azimuth in degrees.\n        - name: hours\n          in: query\n          type: integer\n          required: false\n          description: Number of forecast hours to retrieve (up to 336).\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-advanced-pv-power\n      path: /data/forecast/advanced_pv_power\n      description:\
  \ Advanced PV power forecasts up to 14 days ahead for a registered site.\n      operations:\n      - name: get-forecast-advanced-pv-power\n        method: GET\n        description: Get advanced PV power forecasts up to 14 days ahead for a registered site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for a registered Solcast PV power site.\n        - name: hours\n          in: query\n          type: integer\n          required: false\n          description: Number of forecast hours to retrieve (up to 336).\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: forecast-soiling-kimber\n      path: /data/forecast/soiling/kimber\n      description: Hourly soiling loss forecasts using the Kimber model.\n      operations:\n      - name: get-forecast-soiling-kimber\n        method: GET\n        description: Get soiling loss forecasts for a location using the Kimber model.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: depo_veloc_pm10\n          in: query\n          type: number\n          required: false\n          description: Deposition velocity for PM10 particles (m/s).\n        - name: initial_soiling\n          in: query\n          type: number\n          required: false\n\
  \          description: Initial soiling fraction.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-soiling-hsu\n      path: /data/forecast/soiling/hsu\n      description: Hourly soiling loss forecasts using the HSU model.\n      operations:\n      - name: get-forecast-soiling-hsu\n        method: GET\n        description: Get soiling loss forecasts for a location using the HSU model.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: depo_veloc_pm10\n\
  \          in: query\n          type: number\n          required: false\n          description: Deposition velocity for PM10 particles (m/s).\n        - name: initial_soiling\n          in: query\n          type: number\n          required: false\n          description: Initial soiling fraction.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-aggregations\n      path: /data/forecast/aggregations\n      description: Forecast aggregation data for grid collections or sub-aggregations.\n      operations:\n      - name: get-forecast-aggregations\n        method: GET\n        description: Get forecast aggregation data for a grid collection or sub-aggregation.\n        inputParameters:\n        - name: collection_id\n          in: query\n     \
  \     type: string\n          required: true\n          description: Unique identifier for the grid aggregation collection.\n        - name: aggregation_id\n          in: query\n          type: string\n          required: false\n          description: Unique identifier for a sub-aggregation within the collection.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historic-radiation-and-weather\n      path: /data/historic/radiation_and_weather\n      description: Historical irradiance and weather data from 2007 to 7 days before present.\n      operations:\n      - name: get-historic-radiation-and-weather\n\
  \        method: GET\n        description: Get historical irradiance and weather for up to 31 days at a time from 2007 to present minus 7 days.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start of requested period (ISO 8601 date or datetime).\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of requested period (mutually exclusive with duration).\n        - name: duration\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 duration within 31 days (mutually exclusive with\
  \ end).\n        - name: output_parameters\n          in: query\n          type: string\n          required: false\n          description: Comma-separated output parameters.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historic-rooftop-pv-power\n      path: /data/historic/rooftop_pv_power\n      description: Historical rooftop PV power data from 2007 to 7 days before present.\n      operations:\n      - name: get-historic-rooftop-pv-power\n        method: GET\n        description: Get historical rooftop PV power estimated actuals for a location.\n        inputParameters:\n        -\
  \ name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start of requested period (ISO 8601).\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of requested period (mutually exclusive with duration).\n        - name: duration\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 duration within 31 days (mutually exclusive with end).\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n\
  \          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historic-advanced-pv-power\n      path: /data/historic/advanced_pv_power\n      description: Historical advanced PV power data for a registered site from 2007 to present minus 7 days.\n      operations:\n      - name: get-historic-advanced-pv-power\n        method: GET\n        description: Get historical advanced PV power estimated actuals for a registered site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for a registered Solcast PV power site.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start of requested period (ISO 8601).\n\
  \        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of requested period (mutually exclusive with duration).\n        - name: duration\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 duration within 31 days (mutually exclusive with end).\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historic-soiling-kimber\n      path: /data/historic/soiling/kimber\n      description: Historical hourly soiling loss estimates using the Kimber model.\n      operations:\n      - name:\
  \ get-historic-soiling-kimber\n        method: GET\n        description: Get historical soiling loss estimates using the Kimber model.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start of requested period (ISO 8601).\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of requested period.\n        - name: duration\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 duration within 31 days.\n        - name: depo_veloc_pm10\n          in: query\n          type: number\n   \
  \       required: false\n          description: Deposition velocity for PM10 particles (m/s).\n        - name: initial_soiling\n          in: query\n          type: number\n          required: false\n          description: Initial soiling fraction.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historic-soiling-hsu\n      path: /data/historic/soiling/hsu\n      description: Historical hourly soiling loss estimates using the HSU model.\n      operations:\n      - name: get-historic-soiling-hsu\n        method: GET\n        description: Get historical soiling loss estimates using the HSU model.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude\
  \ in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start of requested period (ISO 8601).\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of requested period.\n        - name: duration\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 duration within 31 days.\n        - name: depo_veloc_pm10\n          in: query\n          type: number\n          required: false\n          description: Deposition velocity for PM10 particles (m/s).\n        - name: initial_soiling\n          in: query\n          type: number\n          required: false\n          description: Initial soiling fraction.\n        - name: format\n          in: query\n\
  \          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tmy-radiation-and-weather\n      path: /data/tmy/radiation_and_weather\n      description: Typical Meteorological Year irradiance and weather data (2007-2023).\n      operations:\n      - name: get-tmy-radiation-and-weather\n        method: GET\n        description: Get TMY irradiance and weather data for a location (computed from 2007-2023).\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: output_parameters\n          in: query\n          type: string\n\
  \          required: false\n          description: Comma-separated output parameters.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tmy-rooftop-pv-power\n      path: /data/tmy/rooftop_pv_power\n      description: Typical Meteorological Year rooftop PV power data (2007-2023).\n      operations:\n      - name: get-tmy-rooftop-pv-power\n        method: GET\n        description: Get TMY rooftop PV power data for a location (computed from 2007-2023).\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description:\
  \ Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: capacity\n          in: query\n          type: number\n          required: false\n          description: System capacity in kilowatts.\n        - name: tilt\n          in: query\n          type: number\n          required: false\n          description: Panel tilt in degrees.\n        - name: azimuth\n          in: query\n          type: number\n          required: false\n          description: Panel azimuth in degrees.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n    - name: live-aggregations\n      path: /data/live/aggregations\n      description: Live aggregation data for grid collections or sub-aggregations.\n      operations:\n      - name: get-live-aggregations\n        method: GET\n        description: Get live aggregation data for a grid collection or sub-aggregation.\n        inputParameters:\n        - name: collection_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the grid aggregation collection.\n        - name: aggregation_id\n          in: query\n          type: string\n          required: false\n          description: Unique identifier for a sub-aggregation within the collection.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n    \
  \      type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pv-power-sites\n      path: /resources/pv_power_sites\n      description: List all registered PV power sites for the authenticated account.\n      operations:\n      - name: list-pv-power-sites\n        method: GET\n        description: List all registered Solcast PV power sites.\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pv-power-site\n      path: /resources/pv_power_site\n      description: CRUD management of individual registered PV power sites.\n      operations:\n      - name:\
  \ get-pv-power-site\n        method: GET\n        description: Get specifications and metadata for a specific registered PV power site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the PV power site.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pv-power-site\n        method: POST\n        description: Create a new PV power site for use with the advanced PV power model.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n\
  \            latitude: '{{tools.latitude}}'\n            longitude: '{{tools.longitude}}'\n            capacity: '{{tools.capacity}}'\n            tilt: '{{tools.tilt}}'\n            azimuth: '{{tools.azimuth}}'\n      - name: patch-pv-power-site\n        method: PATCH\n        description: Partially update specifications of an existing PV power site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the PV power site to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            capacity: '{{tools.capacity}}'\n      - name: update-pv-power-site\n        method: PUT\n        description: Fully overwrite specifications of an existing PV power site.\n        inputParameters:\n        - name: resource_id\n\
  \          in: query\n          type: string\n          required: true\n          description: Unique identifier for the PV power site to overwrite.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            latitude: '{{tools.latitude}}'\n            longitude: '{{tools.longitude}}'\n            capacity: '{{tools.capacity}}'\n      - name: delete-pv-power-site\n        method: DELETE\n        description: Permanently delete a registered PV power site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the PV power site to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n\
  \    namespace: solar-forecasting-api\n    description: Unified REST API for solar energy forecasting and real-time monitoring.\n    resources:\n    - path: /v1/live/radiation-and-weather\n      name: live-radiation-and-weather\n      description: Real-time irradiance and weather for a location.\n      operations:\n      - method: GET\n        name: get-live-radiation-and-weather\n        description: Get live solar irradiance and weather data for a lat/lon location.\n        call: solcast.get-live-radiation-and-weather\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n          output_parameters: rest.output_parameters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/live/rooftop-pv-power\n      name: live-rooftop-pv-power\n      description: Live rooftop PV power actuals.\n      operations:\n      - method: GET\n        name: get-live-rooftop-pv-power\n        description: Get live rooftop PV power estimated\
  \ actuals for a location.\n        call: solcast.get-live-rooftop-pv-power\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/live/advanced-pv-power\n      name: live-advanced-pv-power\n      description: Live advanced PV power actuals for registered sites.\n      operations:\n      - method: GET\n        name: get-live-advanced-pv-power\n        description: Get live advanced PV power actuals for a registered site.\n        call: solcast.get-live-advanced-pv-power\n        with:\n          resource_id: rest.resource_id\n        outputParameters:\n        - type: object\n\n# --- truncated at 32 KB (40 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/solcast/refs/heads/main/capabilities/solar-forecasting.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/solcast/refs/heads/main/capabilities/solar-forecasting.yaml
tags:
- Solar
- Forecasting
- PV Power
- Grid Management
- Energy Market
- Renewable Energy
- Live Data
- Aggregations
tools:
- description: Get live solar irradiance and weather data for any lat/lon location (last 7 days, updated every 5 minutes). Use for real-time solar resource monitoring.
  hints:
    openWorld: true
    readOnly: true
  name: get-live-radiation-and-weather
- description: Get live rooftop PV power estimated actuals for a location. No site registration required.
  hints:
    openWorld: true
    readOnly: true
  name: get-live-rooftop-pv-power
- description: Get live advanced PV power actuals for a registered Solcast site (resource_id required).
  hints:
    openWorld: true
    readOnly: true
  name: get-live-advanced-pv-power
- description: Get live aggregated PV generation data for a grid portfolio or collection. Used for grid management and large-scale monitoring.
  hints:
    openWorld: true
    readOnly: true
  name: get-live-aggregations
- description: Get live soiling loss estimates using the Kimber model. Use for monitoring panel cleanliness and scheduling cleaning.
  hints:
    openWorld: true
    readOnly: true
  name: get-live-soiling-kimber
- description: Get live soiling loss estimates using Solcast's HSU model.
  hints:
    openWorld: true
    readOnly: true
  name: get-live-soiling-hsu
- description: Get solar irradiance and weather forecasts up to 14 days ahead. Use for energy market bidding and dispatch planning.
  hints:
    openWorld: true
    readOnly: true
  name: get-forecast-radiation-and-weather
- description: Get rooftop PV power forecasts up to 14 days ahead. No site registration needed.
  hints:
    openWorld: true
    readOnly: true
  name: get-forecast-rooftop-pv-power
- description: Get high-specification PV power forecasts up to 14 days ahead for a registered site.
  hints:
    openWorld: true
    readOnly: true
  name: get-forecast-advanced-pv-power
- description: Get forecast aggregated PV generation data for a grid portfolio or collection up to 7 days ahead.
  hints:
    openWorld: true
    readOnly: true
  name: get-forecast-aggregations
- description: Get soiling loss forecasts using the Kimber model. Use for planning panel cleaning schedules.
  hints:
    openWorld: true
    readOnly: true
  name: get-forecast-soiling-kimber
- description: Get soiling loss forecasts using the HSU model.
  hints:
    openWorld: true
    readOnly: true
  name: get-forecast-soiling-hsu
---

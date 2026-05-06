---
categories: []
consumed_apis: []
description: Workflow capability for solar resource assessment, project financing, and long-term yield analysis. Combines historical irradiance, rooftop and advanced PV power histories, TMY data, historical soiling models, and PV site management. Used by project developers, asset managers, banks, and energy consultants performing bankable resource assessments and yield studies.
layout: capability
name: Solcast Solar Resource Assessment
operations:
- description: Get historical irradiance and weather for up to 31 days at a time.
  method: GET
  name: get-historic-radiation-and-weather
  path: /v1/historic/radiation-and-weather
- description: Get historical rooftop PV power estimated actuals for a location.
  method: GET
  name: get-historic-rooftop-pv-power
  path: /v1/historic/rooftop-pv-power
- description: Get historical advanced PV power actuals for a registered site.
  method: GET
  name: get-historic-advanced-pv-power
  path: /v1/historic/advanced-pv-power
- description: Get historical soiling loss using the Kimber model.
  method: GET
  name: get-historic-soiling-kimber
  path: /v1/historic/soiling
- description: Get TMY irradiance and weather for a location.
  method: GET
  name: get-tmy-radiation-and-weather
  path: /v1/tmy/radiation-and-weather
- description: Get TMY rooftop PV power data for a location.
  method: GET
  name: get-tmy-rooftop-pv-power
  path: /v1/tmy/rooftop-pv-power
- description: List all registered PV power sites.
  method: GET
  name: list-pv-power-sites
  path: /v1/pv-power-sites
- description: Create a new PV power site.
  method: POST
  name: create-pv-power-site
  path: /v1/pv-power-sites
- description: Get a specific PV power site.
  method: GET
  name: get-pv-power-site
  path: /v1/pv-power-sites/{resource_id}
- description: Partially update a PV power site.
  method: PATCH
  name: patch-pv-power-site
  path: /v1/pv-power-sites/{resource_id}
- description: Fully overwrite a PV power site.
  method: PUT
  name: update-pv-power-site
  path: /v1/pv-power-sites/{resource_id}
- description: Delete a PV power site.
  method: DELETE
  name: delete-pv-power-site
  path: /v1/pv-power-sites/{resource_id}
personas: []
provider_name: Solcast
provider_slug: solcast
search_terms:
- get a specific pv power site.
- partially update a pv power site.
- historical irradiance and weather data from 2007 onwards.
- get historical soiling loss estimates using the kimber model. use for yield loss analysis and cleaning schedule optimization.
- partially update an existing pv power site's specifications (e.g., update capacity or tilt after hardware changes).
- individual pv power site management.
- historical data
- get tmy rooftop pv power
- fully replace an existing pv power site's specifications.
- irradiance
- get historic radiation and weather
- get specifications for a specific registered pv power site.
- soiling
- get historical solar irradiance and weather from 2007 to 7 days before present (up to 31 days per call). use for bankable resource assessment and p50/p90 yield studies.
- weather
- get tmy radiation and weather
- create a new pv power site.
- delete pv power site
- manage registered pv power sites for advanced model access.
- historical soiling loss data using kimber or hsu models.
- typical meteorological year rooftop pv power (2007-2023).
- historical rooftop pv power data from 2007 onwards.
- create pv power site
- register a new pv power site with solcast for advanced pv power model access. requires site name, latitude, and longitude.
- get historic soiling kimber
- get historic advanced pv power
- get historical rooftop pv power estimated actuals from 2007 onwards. use for yield analysis and performance benchmarking.
- permanently delete a registered pv power site.
- list pv power sites
- get historical irradiance and weather for up to 31 days at a time.
- yield analysis
- forecasting
- typical meteorological year irradiance and weather (2007-2023).
- get typical meteorological year irradiance and weather (2007-2023). use for long-run average yield studies and project feasibility.
- get tmy rooftop pv power data for a location.
- resource assessment
- get tmy irradiance and weather for a location.
- get typical meteorological year rooftop pv power data (2007-2023). use for annual yield estimation and project financing.
- pv power
- tmy
- project finance
- renewable energy
- get historic rooftop pv power
- update pv power site
- get historical advanced pv power actuals for a registered site. use for detailed yield analysis with site-specific pv model.
- energy
- list all registered pv power sites for this account.
- list all registered pv power sites.
- patch pv power site
- get historical advanced pv power actuals for a registered site.
- get historical rooftop pv power estimated actuals for a location.
- get historical soiling loss estimates using the hsu model.
- get historic soiling hsu
- historical advanced pv power data for registered sites.
- delete a pv power site.
- get historical soiling loss using the kimber model.
- fully overwrite a pv power site.
- get pv power site
- solar
slug: solar-resource-assessment
source_filename: solar-resource-assessment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Solcast Solar Resource Assessment\n  description: Workflow capability for solar resource assessment, project financing, and long-term yield analysis. Combines\n    historical irradiance, rooftop and advanced PV power histories, TMY data, historical soiling models, and PV site management.\n    Used by project developers, asset managers, banks, and energy consultants performing bankable resource assessments and\n    yield studies.\n  tags:\n  - Solar\n  - Resource Assessment\n  - Historical Data\n  - TMY\n  - PV Power\n  - Soiling\n  - Project Finance\n  - Yield Analysis\n  - Renewable Energy\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SOLCAST_API_KEY: SOLCAST_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: solcast\n    baseUri: https://api.solcast.com.au\n    description: Solcast solar irradiance, PV power, weather forecasting, and site management API.\n    authentication:\n\
  \      type: bearer\n      token: '{{SOLCAST_API_KEY}}'\n    resources:\n    - name: live-radiation-and-weather\n      path: /data/live/radiation_and_weather\n      description: Real-time satellite-derived solar irradiance and weather data for a location (last 7 days, updated every\n        5 minutes).\n      operations:\n      - name: get-live-radiation-and-weather\n        method: GET\n        description: Get live irradiance and weather estimated actuals for a lat/lon location.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees (-90 to 90, north positive).\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees (-180 to 180, east positive).\n        - name: output_parameters\n          in: query\n          type: string\n          required: true\n          description:\
  \ Comma-separated output parameters (e.g., ghi,dni,dhi,air_temp).\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601, e.g., PT30M).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-rooftop-pv-power\n      path: /data/live/rooftop_pv_power\n      description: Live rooftop PV power estimated actuals by location without site registration.\n      operations:\n      - name: get-live-rooftop-pv-power\n        method: GET\n        description: Get live rooftop PV power estimated actuals for a lat/lon location.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n       \
  \   description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: capacity\n          in: query\n          type: number\n          required: false\n          description: System capacity in kilowatts.\n        - name: tilt\n          in: query\n          type: number\n          required: false\n          description: Panel tilt angle in degrees.\n        - name: azimuth\n          in: query\n          type: number\n          required: false\n          description: Panel azimuth in degrees.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-advanced-pv-power\n      path: /data/live/advanced_pv_power\n      description: Live high-specification PV power actuals for a registered PV site.\n      operations:\n      - name: get-live-advanced-pv-power\n        method: GET\n        description: Get live advanced PV power actuals for a registered PV power site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for a registered Solcast PV power site.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: live-soiling-kimber\n      path: /data/live/soiling/kimber\n      description: Live hourly soiling loss estimates using the Kimber model.\n      operations:\n      - name: get-live-soiling-kimber\n        method: GET\n        description: Get live soiling loss estimates for a location using the Kimber model.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: depo_veloc_pm10\n          in: query\n          type: number\n          required: false\n          description: Deposition velocity for PM10 particles (m/s).\n        - name: initial_soiling\n          in: query\n          type: number\n          required: false\n\
  \          description: Initial soiling fraction (0.0 = clean).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-soiling-hsu\n      path: /data/live/soiling/hsu\n      description: Live hourly soiling loss estimates using Solcast's HSU model.\n      operations:\n      - name: get-live-soiling-hsu\n        method: GET\n        description: Get live soiling loss estimates for a location using the HSU model.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name:\
  \ depo_veloc_pm10\n          in: query\n          type: number\n          required: false\n          description: Deposition velocity for PM10 particles (m/s).\n        - name: initial_soiling\n          in: query\n          type: number\n          required: false\n          description: Initial soiling fraction (0.0 = clean).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-radiation-and-weather\n      path: /data/forecast/radiation_and_weather\n      description: Solar irradiance and weather forecasts up to 14 days ahead for a location.\n      operations:\n      - name: get-forecast-radiation-and-weather\n        method: GET\n        description: Get irradiance and weather forecasts up to 14 days ahead for a lat/lon location.\n        inputParameters:\n\
  \        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: output_parameters\n          in: query\n          type: string\n          required: true\n          description: Comma-separated output parameters.\n        - name: hours\n          in: query\n          type: integer\n          required: false\n          description: Number of forecast hours to retrieve (up to 336 / 14 days).\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-rooftop-pv-power\n      path: /data/forecast/rooftop_pv_power\n      description: Rooftop PV power forecasts up to 14 days ahead by location.\n      operations:\n      - name: get-forecast-rooftop-pv-power\n        method: GET\n        description: Get basic rooftop PV power forecasts up to 14 days ahead for a lat/lon location.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: output_parameters\n          in: query\n          type: string\n          required: true\n          description: Comma-separated output parameters.\n        - name: capacity\n          in: query\n          type:\
  \ number\n          required: false\n          description: System capacity in kilowatts.\n        - name: tilt\n          in: query\n          type: number\n          required: false\n          description: Panel tilt in degrees.\n        - name: azimuth\n          in: query\n          type: number\n          required: false\n          description: Panel azimuth in degrees.\n        - name: hours\n          in: query\n          type: integer\n          required: false\n          description: Number of forecast hours to retrieve (up to 336).\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ forecast-advanced-pv-power\n      path: /data/forecast/advanced_pv_power\n      description: Advanced PV power forecasts up to 14 days ahead for a registered site.\n      operations:\n      - name: get-forecast-advanced-pv-power\n        method: GET\n        description: Get advanced PV power forecasts up to 14 days ahead for a registered site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for a registered Solcast PV power site.\n        - name: hours\n          in: query\n          type: integer\n          required: false\n          description: Number of forecast hours to retrieve (up to 336).\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description:\
  \ 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-soiling-kimber\n      path: /data/forecast/soiling/kimber\n      description: Hourly soiling loss forecasts using the Kimber model.\n      operations:\n      - name: get-forecast-soiling-kimber\n        method: GET\n        description: Get soiling loss forecasts for a location using the Kimber model.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: depo_veloc_pm10\n          in: query\n          type: number\n          required: false\n          description: Deposition velocity for PM10 particles (m/s).\n        -\
  \ name: initial_soiling\n          in: query\n          type: number\n          required: false\n          description: Initial soiling fraction.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-soiling-hsu\n      path: /data/forecast/soiling/hsu\n      description: Hourly soiling loss forecasts using the HSU model.\n      operations:\n      - name: get-forecast-soiling-hsu\n        method: GET\n        description: Get soiling loss forecasts for a location using the HSU model.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required:\
  \ true\n          description: Longitude in decimal degrees.\n        - name: depo_veloc_pm10\n          in: query\n          type: number\n          required: false\n          description: Deposition velocity for PM10 particles (m/s).\n        - name: initial_soiling\n          in: query\n          type: number\n          required: false\n          description: Initial soiling fraction.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecast-aggregations\n      path: /data/forecast/aggregations\n      description: Forecast aggregation data for grid collections or sub-aggregations.\n      operations:\n      - name: get-forecast-aggregations\n        method: GET\n        description: Get forecast aggregation data for a grid collection or sub-aggregation.\n\
  \        inputParameters:\n        - name: collection_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the grid aggregation collection.\n        - name: aggregation_id\n          in: query\n          type: string\n          required: false\n          description: Unique identifier for a sub-aggregation within the collection.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historic-radiation-and-weather\n      path: /data/historic/radiation_and_weather\n      description: Historical irradiance and weather data from 2007\
  \ to 7 days before present.\n      operations:\n      - name: get-historic-radiation-and-weather\n        method: GET\n        description: Get historical irradiance and weather for up to 31 days at a time from 2007 to present minus 7 days.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start of requested period (ISO 8601 date or datetime).\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of requested period (mutually exclusive with duration).\n        - name: duration\n          in: query\n          type: string\n        \
  \  required: false\n          description: ISO 8601 duration within 31 days (mutually exclusive with end).\n        - name: output_parameters\n          in: query\n          type: string\n          required: false\n          description: Comma-separated output parameters.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historic-rooftop-pv-power\n      path: /data/historic/rooftop_pv_power\n      description: Historical rooftop PV power data from 2007 to 7 days before present.\n      operations:\n      - name: get-historic-rooftop-pv-power\n        method: GET\n        description: Get\
  \ historical rooftop PV power estimated actuals for a location.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start of requested period (ISO 8601).\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of requested period (mutually exclusive with duration).\n        - name: duration\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 duration within 31 days (mutually exclusive with end).\n        - name: period\n          in: query\n          type: string\n          required:\
  \ false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historic-advanced-pv-power\n      path: /data/historic/advanced_pv_power\n      description: Historical advanced PV power data for a registered site from 2007 to present minus 7 days.\n      operations:\n      - name: get-historic-advanced-pv-power\n        method: GET\n        description: Get historical advanced PV power estimated actuals for a registered site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for a registered Solcast PV power site.\n        - name: start\n          in: query\n          type:\
  \ string\n          required: true\n          description: Start of requested period (ISO 8601).\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of requested period (mutually exclusive with duration).\n        - name: duration\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 duration within 31 days (mutually exclusive with end).\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historic-soiling-kimber\n      path: /data/historic/soiling/kimber\n      description:\
  \ Historical hourly soiling loss estimates using the Kimber model.\n      operations:\n      - name: get-historic-soiling-kimber\n        method: GET\n        description: Get historical soiling loss estimates using the Kimber model.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start of requested period (ISO 8601).\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of requested period.\n        - name: duration\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 duration\
  \ within 31 days.\n        - name: depo_veloc_pm10\n          in: query\n          type: number\n          required: false\n          description: Deposition velocity for PM10 particles (m/s).\n        - name: initial_soiling\n          in: query\n          type: number\n          required: false\n          description: Initial soiling fraction.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historic-soiling-hsu\n      path: /data/historic/soiling/hsu\n      description: Historical hourly soiling loss estimates using the HSU model.\n      operations:\n      - name: get-historic-soiling-hsu\n        method: GET\n        description: Get historical soiling loss estimates using the HSU model.\n        inputParameters:\n        - name: latitude\n  \
  \        in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start of requested period (ISO 8601).\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End of requested period.\n        - name: duration\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 duration within 31 days.\n        - name: depo_veloc_pm10\n          in: query\n          type: number\n          required: false\n          description: Deposition velocity for PM10 particles (m/s).\n        - name: initial_soiling\n          in: query\n          type: number\n          required:\
  \ false\n          description: Initial soiling fraction.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tmy-radiation-and-weather\n      path: /data/tmy/radiation_and_weather\n      description: Typical Meteorological Year irradiance and weather data (2007-2023).\n      operations:\n      - name: get-tmy-radiation-and-weather\n        method: GET\n        description: Get TMY irradiance and weather data for a location (computed from 2007-2023).\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude\
  \ in decimal degrees.\n        - name: output_parameters\n          in: query\n          type: string\n          required: false\n          description: Comma-separated output parameters.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tmy-rooftop-pv-power\n      path: /data/tmy/rooftop_pv_power\n      description: Typical Meteorological Year rooftop PV power data (2007-2023).\n      operations:\n      - name: get-tmy-rooftop-pv-power\n        method: GET\n        description: Get TMY rooftop PV power data for a location (computed from 2007-2023).\n        inputParameters:\n        - name:\
  \ latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude in decimal degrees.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude in decimal degrees.\n        - name: capacity\n          in: query\n          type: number\n          required: false\n          description: System capacity in kilowatts.\n        - name: tilt\n          in: query\n          type: number\n          required: false\n          description: Panel tilt in degrees.\n        - name: azimuth\n          in: query\n          type: number\n          required: false\n          description: Panel azimuth in degrees.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description:\
  \ 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-aggregations\n      path: /data/live/aggregations\n      description: Live aggregation data for grid collections or sub-aggregations.\n      operations:\n      - name: get-live-aggregations\n        method: GET\n        description: Get live aggregation data for a grid collection or sub-aggregation.\n        inputParameters:\n        - name: collection_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the grid aggregation collection.\n        - name: aggregation_id\n          in: query\n          type: string\n          required: false\n          description: Unique identifier for a sub-aggregation within the collection.\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Time\
  \ period between data points (ISO 8601).\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pv-power-sites\n      path: /resources/pv_power_sites\n      description: List all registered PV power sites for the authenticated account.\n      operations:\n      - name: list-pv-power-sites\n        method: GET\n        description: List all registered Solcast PV power sites.\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pv-power-site\n      path: /resources/pv_power_site\n      description:\
  \ CRUD management of individual registered PV power sites.\n      operations:\n      - name: get-pv-power-site\n        method: GET\n        description: Get specifications and metadata for a specific registered PV power site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the PV power site.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or csv.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pv-power-site\n        method: POST\n        description: Create a new PV power site for use with the advanced PV power model.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            latitude: '{{tools.latitude}}'\n            longitude: '{{tools.longitude}}'\n            capacity: '{{tools.capacity}}'\n            tilt: '{{tools.tilt}}'\n            azimuth: '{{tools.azimuth}}'\n      - name: patch-pv-power-site\n        method: PATCH\n        description: Partially update specifications of an existing PV power site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the PV power site to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            capacity: '{{tools.capacity}}'\n      - name: update-pv-power-site\n        method: PUT\n        description: Fully overwrite\
  \ specifications of an existing PV power site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the PV power site to overwrite.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            latitude: '{{tools.latitude}}'\n            longitude: '{{tools.longitude}}'\n            capacity: '{{tools.capacity}}'\n      - name: delete-pv-power-site\n        method: DELETE\n        description: Permanently delete a registered PV power site.\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier for the PV power site to delete.\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: solar-resource-assessment-api\n    description: Unified REST API for solar resource assessment and long-term yield analysis.\n    resources:\n    - path: /v1/historic/radiation-and-weather\n      name: historic-radiation-and-weather\n      description: Historical irradiance and weather data from 2007 onwards.\n      operations:\n      - method: GET\n        name: get-historic-radiation-and-weather\n        description: Get historical irradiance and weather for up to 31 days at a time.\n        call: solcast.get-historic-radiation-and-weather\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n          start: rest.start\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/historic/rooftop-pv-power\n      name: historic-rooftop-pv-power\n      description: Historical rooftop PV power data from 2007\
  \ onwards.\n      operations:\n      - method: GET\n        name: get-historic-rooftop-pv-power\n        description: Get historical rooftop PV power estimated actuals for a location.\n        call: solcast.get-historic-rooftop-pv-power\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n          start: rest.start\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/historic/advanced-pv-power\n      name: historic-advanced-pv-power\n      description: Historical advanced PV power data for registered sites.\n      operations:\n      - method: GET\n        name: get-historic-advanced-pv-power\n        description: Get historical advanced PV p\n\n# --- truncated at 32 KB (41 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/solcast/refs/heads/main/capabilities/solar-resource-assessment.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/solcast/refs/heads/main/capabilities/solar-resource-assessment.yaml
tags:
- Solar
- Resource Assessment
- Historical Data
- TMY
- PV Power
- Soiling
- Project Finance
- Yield Analysis
- Renewable Energy
tools:
- description: Get historical solar irradiance and weather from 2007 to 7 days before present (up to 31 days per call). Use for bankable resource assessment and P50/P90 yield studies.
  hints:
    openWorld: true
    readOnly: true
  name: get-historic-radiation-and-weather
- description: Get historical rooftop PV power estimated actuals from 2007 onwards. Use for yield analysis and performance benchmarking.
  hints:
    openWorld: true
    readOnly: true
  name: get-historic-rooftop-pv-power
- description: Get historical advanced PV power actuals for a registered site. Use for detailed yield analysis with site-specific PV model.
  hints:
    openWorld: true
    readOnly: true
  name: get-historic-advanced-pv-power
- description: Get historical soiling loss estimates using the Kimber model. Use for yield loss analysis and cleaning schedule optimization.
  hints:
    openWorld: true
    readOnly: true
  name: get-historic-soiling-kimber
- description: Get historical soiling loss estimates using the HSU model.
  hints:
    openWorld: true
    readOnly: true
  name: get-historic-soiling-hsu
- description: Get Typical Meteorological Year irradiance and weather (2007-2023). Use for long-run average yield studies and project feasibility.
  hints:
    openWorld: true
    readOnly: true
  name: get-tmy-radiation-and-weather
- description: Get Typical Meteorological Year rooftop PV power data (2007-2023). Use for annual yield estimation and project financing.
  hints:
    openWorld: true
    readOnly: true
  name: get-tmy-rooftop-pv-power
- description: List all registered PV power sites for this account.
  hints:
    openWorld: false
    readOnly: true
  name: list-pv-power-sites
- description: Get specifications for a specific registered PV power site.
  hints:
    openWorld: false
    readOnly: true
  name: get-pv-power-site
- description: Register a new PV power site with Solcast for advanced PV power model access. Requires site name, latitude, and longitude.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-pv-power-site
- description: Partially update an existing PV power site's specifications (e.g., update capacity or tilt after hardware changes).
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: patch-pv-power-site
- description: Fully replace an existing PV power site's specifications.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-pv-power-site
- description: Permanently delete a registered PV power site.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-pv-power-site
---

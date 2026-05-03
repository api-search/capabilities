---
api_specs:
- filename: solcast-openapi.yml
  format: yaml
  label: solcast
  slug: solcast
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/solcast/refs/heads/main/openapi/solcast-openapi.yml
categories: []
consumed_apis:
- solcast
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
- get high-specification pv power forecasts up to 14 days ahead for a registered site.
- get live solar irradiance and weather data for a lat/lon location.
- grid management
- soiling loss forecasts for maintenance planning.
- get forecast advanced pv power
- get forecast radiation and weather
- live soiling loss data using kimber or hsu models.
- renewable energy
- get advanced pv power forecasts for a registered site.
- get soiling loss forecasts using the hsu model.
- get forecast soiling hsu
- get live rooftop pv power estimated actuals for a location. no site registration required.
- get live aggregations
- get soiling loss forecasts using the kimber model.
- get live advanced pv power actuals for a registered solcast site (resource_id required).
- get live soiling kimber
- get soiling loss forecasts using the kimber model. use for planning panel cleaning schedules.
- get forecast aggregations
- live data
- get live soiling loss estimates using the kimber model. use for monitoring panel cleanliness and scheduling cleaning.
- get forecast aggregated pv generation data for a grid portfolio or collection up to 7 days ahead.
- get rooftop pv power forecasts up to 14 days ahead.
- get live soiling loss estimates using solcast's hsu model.
- live advanced pv power actuals for registered sites.
- get live radiation and weather
- solar
- aggregations
- energy
- get live solar irradiance and weather data for any lat/lon location (last 7 days, updated every 5 minutes). use for real-time solar resource monitoring.
- rooftop pv power forecasts up to 14 days ahead.
- advanced pv power forecasts up to 14 days ahead for registered sites.
- pv power
- get live rooftop pv power
- get forecast soiling kimber
- irradiance
- real-time irradiance and weather for a location.
- get live soiling loss using the kimber model.
- get forecast aggregation data for a grid collection.
- get live rooftop pv power estimated actuals for a location.
- get forecast rooftop pv power
- energy market
- get live aggregation data for a grid collection or sub-aggregation.
- forecasting
- get rooftop pv power forecasts up to 14 days ahead. no site registration needed.
- get live advanced pv power actuals for a registered site.
- forecast irradiance and weather up to 14 days ahead.
- get live aggregated pv generation data for a grid portfolio or collection. used for grid management and large-scale monitoring.
- get live advanced pv power
- live rooftop pv power actuals.
- get irradiance and weather forecasts up to 14 days ahead.
- live grid aggregation data for portfolios and grid operators.
- forecast grid aggregation data for portfolio and grid management.
- get live soiling hsu
- weather
- get solar irradiance and weather forecasts up to 14 days ahead. use for energy market bidding and dispatch planning.
slug: solar-forecasting
source_filename: solar-forecasting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Solcast Solar Forecasting\"\n  description: >-\n    Workflow capability for solar energy forecasting and real-time monitoring.\n    Combines live and forecast radiation, PV power, soiling, and grid aggregation\n    data to support energy market bidding, dispatch optimization, and grid management.\n    Used by energy traders, grid operators, and renewable energy portfolio managers.\n  tags:\n    - Solar\n    - Forecasting\n    - PV Power\n    - Grid Management\n    - Energy Market\n    - Renewable Energy\n    - Live Data\n    - Aggregations\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SOLCAST_API_KEY: SOLCAST_API_KEY\n\ncapability:\n  consumes:\n    - import: solcast\n      location: ./shared/solcast.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: solar-forecasting-api\n      description: \"Unified REST API for solar energy forecasting and real-time\
  \ monitoring.\"\n      resources:\n        - path: /v1/live/radiation-and-weather\n          name: live-radiation-and-weather\n          description: \"Real-time irradiance and weather for a location.\"\n          operations:\n            - method: GET\n              name: get-live-radiation-and-weather\n              description: \"Get live solar irradiance and weather data for a lat/lon location.\"\n              call: \"solcast.get-live-radiation-and-weather\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                output_parameters: \"rest.output_parameters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/live/rooftop-pv-power\n          name: live-rooftop-pv-power\n          description: \"Live rooftop PV power actuals.\"\n          operations:\n            - method: GET\n              name: get-live-rooftop-pv-power\n              description:\
  \ \"Get live rooftop PV power estimated actuals for a location.\"\n              call: \"solcast.get-live-rooftop-pv-power\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/live/advanced-pv-power\n          name: live-advanced-pv-power\n          description: \"Live advanced PV power actuals for registered sites.\"\n          operations:\n            - method: GET\n              name: get-live-advanced-pv-power\n              description: \"Get live advanced PV power actuals for a registered site.\"\n              call: \"solcast.get-live-advanced-pv-power\"\n              with:\n                resource_id: \"rest.resource_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/live/aggregations\n          name: live-aggregations\n\
  \          description: \"Live grid aggregation data for portfolios and grid operators.\"\n          operations:\n            - method: GET\n              name: get-live-aggregations\n              description: \"Get live aggregation data for a grid collection or sub-aggregation.\"\n              call: \"solcast.get-live-aggregations\"\n              with:\n                collection_id: \"rest.collection_id\"\n                aggregation_id: \"rest.aggregation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/live/soiling\n          name: live-soiling\n          description: \"Live soiling loss data using Kimber or HSU models.\"\n          operations:\n            - method: GET\n              name: get-live-soiling-kimber\n              description: \"Get live soiling loss using the Kimber model.\"\n              call: \"solcast.get-live-soiling-kimber\"\n              with:\n                latitude: \"rest.latitude\"\
  \n                longitude: \"rest.longitude\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/forecast/radiation-and-weather\n          name: forecast-radiation-and-weather\n          description: \"Forecast irradiance and weather up to 14 days ahead.\"\n          operations:\n            - method: GET\n              name: get-forecast-radiation-and-weather\n              description: \"Get irradiance and weather forecasts up to 14 days ahead.\"\n              call: \"solcast.get-forecast-radiation-and-weather\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                output_parameters: \"rest.output_parameters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/forecast/rooftop-pv-power\n          name: forecast-rooftop-pv-power\n          description: \"Rooftop PV\
  \ power forecasts up to 14 days ahead.\"\n          operations:\n            - method: GET\n              name: get-forecast-rooftop-pv-power\n              description: \"Get rooftop PV power forecasts up to 14 days ahead.\"\n              call: \"solcast.get-forecast-rooftop-pv-power\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                output_parameters: \"rest.output_parameters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/forecast/advanced-pv-power\n          name: forecast-advanced-pv-power\n          description: \"Advanced PV power forecasts up to 14 days ahead for registered sites.\"\n          operations:\n            - method: GET\n              name: get-forecast-advanced-pv-power\n              description: \"Get advanced PV power forecasts for a registered site.\"\n              call: \"solcast.get-forecast-advanced-pv-power\"\
  \n              with:\n                resource_id: \"rest.resource_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/forecast/aggregations\n          name: forecast-aggregations\n          description: \"Forecast grid aggregation data for portfolio and grid management.\"\n          operations:\n            - method: GET\n              name: get-forecast-aggregations\n              description: \"Get forecast aggregation data for a grid collection.\"\n              call: \"solcast.get-forecast-aggregations\"\n              with:\n                collection_id: \"rest.collection_id\"\n                aggregation_id: \"rest.aggregation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/forecast/soiling\n          name: forecast-soiling\n          description: \"Soiling loss forecasts for maintenance planning.\"\n          operations:\n\
  \            - method: GET\n              name: get-forecast-soiling-kimber\n              description: \"Get soiling loss forecasts using the Kimber model.\"\n              call: \"solcast.get-forecast-soiling-kimber\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: solar-forecasting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted solar energy forecasting and real-time monitoring.\"\n      tools:\n        - name: get-live-radiation-and-weather\n          description: \"Get live solar irradiance and weather data for any lat/lon location (last 7 days, updated every 5 minutes). Use for real-time solar resource monitoring.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-live-radiation-and-weather\"\
  \n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            output_parameters: \"tools.output_parameters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-live-rooftop-pv-power\n          description: \"Get live rooftop PV power estimated actuals for a location. No site registration required.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-live-rooftop-pv-power\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-live-advanced-pv-power\n          description: \"Get live advanced PV power actuals for a registered Solcast site (resource_id required).\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-live-advanced-pv-power\"\
  \n          with:\n            resource_id: \"tools.resource_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-live-aggregations\n          description: \"Get live aggregated PV generation data for a grid portfolio or collection. Used for grid management and large-scale monitoring.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-live-aggregations\"\n          with:\n            collection_id: \"tools.collection_id\"\n            aggregation_id: \"tools.aggregation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-live-soiling-kimber\n          description: \"Get live soiling loss estimates using the Kimber model. Use for monitoring panel cleanliness and scheduling cleaning.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-live-soiling-kimber\"\
  \n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-live-soiling-hsu\n          description: \"Get live soiling loss estimates using Solcast's HSU model.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-live-soiling-hsu\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-forecast-radiation-and-weather\n          description: \"Get solar irradiance and weather forecasts up to 14 days ahead. Use for energy market bidding and dispatch planning.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-forecast-radiation-and-weather\"\n          with:\n        \
  \    latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            output_parameters: \"tools.output_parameters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-forecast-rooftop-pv-power\n          description: \"Get rooftop PV power forecasts up to 14 days ahead. No site registration needed.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-forecast-rooftop-pv-power\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            output_parameters: \"tools.output_parameters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-forecast-advanced-pv-power\n          description: \"Get high-specification PV power forecasts up to 14 days ahead for a registered site.\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"solcast.get-forecast-advanced-pv-power\"\n          with:\n            resource_id: \"tools.resource_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-forecast-aggregations\n          description: \"Get forecast aggregated PV generation data for a grid portfolio or collection up to 7 days ahead.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-forecast-aggregations\"\n          with:\n            collection_id: \"tools.collection_id\"\n            aggregation_id: \"tools.aggregation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-forecast-soiling-kimber\n          description: \"Get soiling loss forecasts using the Kimber model. Use for planning panel cleaning schedules.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-forecast-soiling-kimber\"\
  \n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-forecast-soiling-hsu\n          description: \"Get soiling loss forecasts using the HSU model.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"solcast.get-forecast-soiling-hsu\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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

---
categories: []
consumed_apis: []
description: '<h4>Timestamp Format Options</h4> <p>When specifying timestamps, you can choose from the following three formats:</p> <ol> <li><strong>ISO 8601 Format</strong>: <ul> <li>This format includes the full date and time, with an optional timezone indicator.</li> <li>Examples: <ul> <li><code>2025-01-01T17:00Z</code> (UTC time)</li> <li><code>2025-01-01T18:00+01:00</code> (Local time offset by +01:00)</li> </ul> </li> </ul> </li> <li><strong>Daily Format</strong>: <ul> <li>This format specifies only the date.</li> <li>The start time is assumed to be at 00:00 on the specified date in the local timezone'
layout: capability
name: Energy-Charts API
operations:
- description: Public Power
  method: GET
  name: public-power-public-power-get
  path: /public_power
- description: Public Power Forecast
  method: GET
  name: public-power-forecast-public-power-forecast-get
  path: /public_power_forecast
- description: Total Power
  method: GET
  name: total-power-total-power-get
  path: /total_power
- description: Installed Power
  method: GET
  name: installed-power-installed-power-get
  path: /installed_power
- description: Day Ahead Price
  method: GET
  name: day-ahead-price-price-get
  path: /price
- description: Cross Border Electricity Trading
  method: GET
  name: cross-border-electricity-trading-cbet-get
  path: /cbet
- description: Cross Border Physical Flows
  method: GET
  name: cross-border-physical-flows-cbpf-get
  path: /cbpf
- description: Traffic Signal
  method: GET
  name: traffic-signal-signal-get
  path: /signal
- description: Renewable Share Forecast
  method: GET
  name: renewable-share-forecast-ren-share-forecast-get
  path: /ren_share_forecast
- description: Ren Share Daily Avg
  method: GET
  name: ren-share-daily-avg-ren-share-daily-avg-get
  path: /ren_share_daily_avg
- description: Solar Share
  method: GET
  name: solar-share-solar-share-get
  path: /solar_share
- description: Solar Share Daily Avg
  method: GET
  name: solar-share-daily-avg-solar-share-daily-avg-get
  path: /solar_share_daily_avg
- description: Wind Onshore Share
  method: GET
  name: wind-onshore-share-wind-onshore-share-get
  path: /wind_onshore_share
- description: Wind Onshore Share Daily Avg
  method: GET
  name: wind-onshore-share-daily-avg-wind-onshore-share-
  path: /wind_onshore_share_daily_avg
- description: Wind Offshore Share
  method: GET
  name: wind-offshore-share-wind-offshore-share-get
  path: /wind_offshore_share
- description: Wind Offshore Share Daily Avg
  method: GET
  name: wind-offshore-share-daily-avg-wind-offshore-shar
  path: /wind_offshore_share_daily_avg
- description: Frequency
  method: GET
  name: frequency-frequency-get
  path: /frequency
personas: []
provider_name: Energy Charts API
provider_slug: energy-charts-api
search_terms:
- wind offshore share daily avg
- ren share daily avg ren share daily avg get
- solar share daily avg solar share daily avg get
- europe
- public power forecast public power forecast get
- renewable share forecast ren share forecast get
- cross border physical flows
- day ahead price
- cross border electricity trading
- solar share
- solar share daily avg
- wind offshore share
- renewable share forecast
- wind onshore share daily avg
- ren share daily avg
- power
- traffic signal signal get
- grid
- cross border physical flows cbpf get
- forecasts
- public power public power get
- total power total power get
- installed power installed power get
- wind onshore share
- api
- public power forecast
- cross border electricity trading cbet get
- installed power
- energy
- frequency
- public power
- electricity
- wind onshore share daily avg wind onshore share
- charts
- wind onshore share wind onshore share get
- pricing
- traffic signal
- wind offshore share wind offshore share get
- frequency frequency get
- renewables
- day ahead price price get
- solar share solar share get
- wind offshore share daily avg wind offshore shar
- total power
slug: energy-charts-api-capability
source_filename: energy-charts-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Energy-Charts API\n  description: '<h4>Timestamp Format Options</h4> <p>When specifying timestamps, you can choose from the following three formats:</p>\n    <ol> <li><strong>ISO 8601 Format</strong>: <ul> <li>This format includes the full date and time, with an optional timezone\n    indicator.</li> <li>Examples: <ul> <li><code>2025-01-01T17:00Z</code> (UTC time)</li> <li><code>2025-01-01T18:00+01:00</code>\n    (Local time offset by +01:00)</li> </ul> </li> </ul> </li> <li><strong>Daily Format</strong>: <ul> <li>This format specifies\n    only the date.</li> <li>The start time is assumed to be at 00:00 on the specified date in the local timezone'\n  tags:\n  - Energy\n  - Charts\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: energy-charts-api\n    baseUri: https://api.example.com\n    description: Energy-Charts API HTTP API.\n    resources:\n    - name: public-power\n\
  \      path: /public_power\n      operations:\n      - name: public-power-public-power-get\n        method: GET\n        description: Public Power\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        - name: start\n          in: query\n          type: string\n        - name: end\n          in: query\n          type: string\n        - name: subtype\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-power-forecast\n      path: /public_power_forecast\n      operations:\n      - name: public-power-forecast-public-power-forecast-get\n        method: GET\n        description: Public Power Forecast\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        - name: production_type\n          in: query\n          type: string\n        - name: forecast_type\n \
  \         in: query\n          type: string\n        - name: start\n          in: query\n          type: string\n        - name: end\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: total-power\n      path: /total_power\n      operations:\n      - name: total-power-total-power-get\n        method: GET\n        description: Total Power\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        - name: start\n          in: query\n          type: string\n        - name: end\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: installed-power\n      path: /installed_power\n      operations:\n      - name: installed-power-installed-power-get\n        method: GET\n        description:\
  \ Installed Power\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        - name: time_step\n          in: query\n          type: string\n        - name: installation_decommission\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: price\n      path: /price\n      operations:\n      - name: day-ahead-price-price-get\n        method: GET\n        description: Day Ahead Price\n        inputParameters:\n        - name: bzn\n          in: query\n          type: string\n        - name: start\n          in: query\n          type: string\n        - name: end\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cbet\n      path: /cbet\n      operations:\n      - name: cross-border-electricity-trading-cbet-get\n\
  \        method: GET\n        description: Cross Border Electricity Trading\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        - name: start\n          in: query\n          type: string\n        - name: end\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cbpf\n      path: /cbpf\n      operations:\n      - name: cross-border-physical-flows-cbpf-get\n        method: GET\n        description: Cross Border Physical Flows\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        - name: start\n          in: query\n          type: string\n        - name: end\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: signal\n      path:\
  \ /signal\n      operations:\n      - name: traffic-signal-signal-get\n        method: GET\n        description: Traffic Signal\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        - name: postal_code\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ren-share-forecast\n      path: /ren_share_forecast\n      operations:\n      - name: renewable-share-forecast-ren-share-forecast-get\n        method: GET\n        description: Renewable Share Forecast\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ren-share-daily-avg\n      path: /ren_share_daily_avg\n      operations:\n      - name: ren-share-daily-avg-ren-share-daily-avg-get\n\
  \        method: GET\n        description: Ren Share Daily Avg\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        - name: year\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: solar-share\n      path: /solar_share\n      operations:\n      - name: solar-share-solar-share-get\n        method: GET\n        description: Solar Share\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: solar-share-daily-avg\n      path: /solar_share_daily_avg\n      operations:\n      - name: solar-share-daily-avg-solar-share-daily-avg-get\n        method: GET\n        description: Solar Share Daily Avg\n        inputParameters:\n        -\
  \ name: country\n          in: query\n          type: string\n        - name: year\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wind-onshore-share\n      path: /wind_onshore_share\n      operations:\n      - name: wind-onshore-share-wind-onshore-share-get\n        method: GET\n        description: Wind Onshore Share\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wind-onshore-share-daily-avg\n      path: /wind_onshore_share_daily_avg\n      operations:\n      - name: wind-onshore-share-daily-avg-wind-onshore-share-\n        method: GET\n        description: Wind Onshore Share Daily Avg\n        inputParameters:\n        - name: country\n          in: query\n    \
  \      type: string\n        - name: year\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wind-offshore-share\n      path: /wind_offshore_share\n      operations:\n      - name: wind-offshore-share-wind-offshore-share-get\n        method: GET\n        description: Wind Offshore Share\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wind-offshore-share-daily-avg\n      path: /wind_offshore_share_daily_avg\n      operations:\n      - name: wind-offshore-share-daily-avg-wind-offshore-shar\n        method: GET\n        description: Wind Offshore Share Daily Avg\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n        - name:\
  \ year\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: frequency\n      path: /frequency\n      operations:\n      - name: frequency-frequency-get\n        method: GET\n        description: Frequency\n        inputParameters:\n        - name: region\n          in: query\n          type: string\n        - name: start\n          in: query\n          type: string\n        - name: end\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: energy-charts-api-rest\n    description: REST adapter for Energy-Charts API.\n    resources:\n    - path: /public_power\n      name: public-power-public-power-get\n      operations:\n      - method: GET\n        name: public-power-public-power-get\n\
  \        description: Public Power\n        call: energy-charts-api.public-power-public-power-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /public_power_forecast\n      name: public-power-forecast-public-power-forecast-get\n      operations:\n      - method: GET\n        name: public-power-forecast-public-power-forecast-get\n        description: Public Power Forecast\n        call: energy-charts-api.public-power-forecast-public-power-forecast-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /total_power\n      name: total-power-total-power-get\n      operations:\n      - method: GET\n        name: total-power-total-power-get\n        description: Total Power\n        call: energy-charts-api.total-power-total-power-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /installed_power\n      name: installed-power-installed-power-get\n      operations:\n      - method:\
  \ GET\n        name: installed-power-installed-power-get\n        description: Installed Power\n        call: energy-charts-api.installed-power-installed-power-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /price\n      name: day-ahead-price-price-get\n      operations:\n      - method: GET\n        name: day-ahead-price-price-get\n        description: Day Ahead Price\n        call: energy-charts-api.day-ahead-price-price-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cbet\n      name: cross-border-electricity-trading-cbet-get\n      operations:\n      - method: GET\n        name: cross-border-electricity-trading-cbet-get\n        description: Cross Border Electricity Trading\n        call: energy-charts-api.cross-border-electricity-trading-cbet-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cbpf\n      name: cross-border-physical-flows-cbpf-get\n     \
  \ operations:\n      - method: GET\n        name: cross-border-physical-flows-cbpf-get\n        description: Cross Border Physical Flows\n        call: energy-charts-api.cross-border-physical-flows-cbpf-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /signal\n      name: traffic-signal-signal-get\n      operations:\n      - method: GET\n        name: traffic-signal-signal-get\n        description: Traffic Signal\n        call: energy-charts-api.traffic-signal-signal-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ren_share_forecast\n      name: renewable-share-forecast-ren-share-forecast-get\n      operations:\n      - method: GET\n        name: renewable-share-forecast-ren-share-forecast-get\n        description: Renewable Share Forecast\n        call: energy-charts-api.renewable-share-forecast-ren-share-forecast-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /ren_share_daily_avg\n      name: ren-share-daily-avg-ren-share-daily-avg-get\n      operations:\n      - method: GET\n        name: ren-share-daily-avg-ren-share-daily-avg-get\n        description: Ren Share Daily Avg\n        call: energy-charts-api.ren-share-daily-avg-ren-share-daily-avg-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /solar_share\n      name: solar-share-solar-share-get\n      operations:\n      - method: GET\n        name: solar-share-solar-share-get\n        description: Solar Share\n        call: energy-charts-api.solar-share-solar-share-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /solar_share_daily_avg\n      name: solar-share-daily-avg-solar-share-daily-avg-get\n      operations:\n      - method: GET\n        name: solar-share-daily-avg-solar-share-daily-avg-get\n        description: Solar Share Daily Avg\n        call: energy-charts-api.solar-share-daily-avg-solar-share-daily-avg-get\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wind_onshore_share\n      name: wind-onshore-share-wind-onshore-share-get\n      operations:\n      - method: GET\n        name: wind-onshore-share-wind-onshore-share-get\n        description: Wind Onshore Share\n        call: energy-charts-api.wind-onshore-share-wind-onshore-share-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wind_onshore_share_daily_avg\n      name: wind-onshore-share-daily-avg-wind-onshore-share\n      operations:\n      - method: GET\n        name: wind-onshore-share-daily-avg-wind-onshore-share-\n        description: Wind Onshore Share Daily Avg\n        call: energy-charts-api.wind-onshore-share-daily-avg-wind-onshore-share-\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wind_offshore_share\n      name: wind-offshore-share-wind-offshore-share-get\n      operations:\n      - method: GET\n   \
  \     name: wind-offshore-share-wind-offshore-share-get\n        description: Wind Offshore Share\n        call: energy-charts-api.wind-offshore-share-wind-offshore-share-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wind_offshore_share_daily_avg\n      name: wind-offshore-share-daily-avg-wind-offshore-shar\n      operations:\n      - method: GET\n        name: wind-offshore-share-daily-avg-wind-offshore-shar\n        description: Wind Offshore Share Daily Avg\n        call: energy-charts-api.wind-offshore-share-daily-avg-wind-offshore-shar\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /frequency\n      name: frequency-frequency-get\n      operations:\n      - method: GET\n        name: frequency-frequency-get\n        description: Frequency\n        call: energy-charts-api.frequency-frequency-get\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n\
  \    namespace: energy-charts-api-mcp\n    transport: http\n    description: MCP adapter for Energy-Charts API for AI agent use.\n    tools:\n    - name: public-power-public-power-get\n      description: Public Power\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.public-power-public-power-get\n      with:\n        country: tools.country\n        start: tools.start\n        end: tools.end\n        subtype: tools.subtype\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      - name: start\n        type: string\n        description: start\n      - name: end\n        type: string\n        description: end\n      - name: subtype\n        type: string\n        description: subtype\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: public-power-forecast-public-power-forecast-get\n      description: Public Power Forecast\n      hints:\n  \
  \      readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.public-power-forecast-public-power-forecast-get\n      with:\n        country: tools.country\n        production_type: tools.production_type\n        forecast_type: tools.forecast_type\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      - name: production_type\n        type: string\n        description: production_type\n      - name: forecast_type\n        type: string\n        description: forecast_type\n      - name: start\n        type: string\n        description: start\n      - name: end\n        type: string\n        description: end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: total-power-total-power-get\n      description: Total Power\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ energy-charts-api.total-power-total-power-get\n      with:\n        country: tools.country\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      - name: start\n        type: string\n        description: start\n      - name: end\n        type: string\n        description: end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: installed-power-installed-power-get\n      description: Installed Power\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.installed-power-installed-power-get\n      with:\n        country: tools.country\n        time_step: tools.time_step\n        installation_decommission: tools.installation_decommission\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      - name: time_step\n        type: string\n        description:\
  \ time_step\n      - name: installation_decommission\n        type: boolean\n        description: installation_decommission\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: day-ahead-price-price-get\n      description: Day Ahead Price\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.day-ahead-price-price-get\n      with:\n        bzn: tools.bzn\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: bzn\n        type: string\n        description: bzn\n      - name: start\n        type: string\n        description: start\n      - name: end\n        type: string\n        description: end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cross-border-electricity-trading-cbet-get\n      description: Cross Border Electricity Trading\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: energy-charts-api.cross-border-electricity-trading-cbet-get\n      with:\n        country: tools.country\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      - name: start\n        type: string\n        description: start\n      - name: end\n        type: string\n        description: end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cross-border-physical-flows-cbpf-get\n      description: Cross Border Physical Flows\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.cross-border-physical-flows-cbpf-get\n      with:\n        country: tools.country\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      - name: start\n        type: string\n        description: start\n\
  \      - name: end\n        type: string\n        description: end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: traffic-signal-signal-get\n      description: Traffic Signal\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.traffic-signal-signal-get\n      with:\n        country: tools.country\n        postal_code: tools.postal_code\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      - name: postal_code\n        type: string\n        description: postal_code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: renewable-share-forecast-ren-share-forecast-get\n      description: Renewable Share Forecast\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.renewable-share-forecast-ren-share-forecast-get\n      with:\n        country:\
  \ tools.country\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ren-share-daily-avg-ren-share-daily-avg-get\n      description: Ren Share Daily Avg\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.ren-share-daily-avg-ren-share-daily-avg-get\n      with:\n        country: tools.country\n        year: tools.year\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      - name: year\n        type: integer\n        description: year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: solar-share-solar-share-get\n      description: Solar Share\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.solar-share-solar-share-get\n      with:\n      \
  \  country: tools.country\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: solar-share-daily-avg-solar-share-daily-avg-get\n      description: Solar Share Daily Avg\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.solar-share-daily-avg-solar-share-daily-avg-get\n      with:\n        country: tools.country\n        year: tools.year\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      - name: year\n        type: integer\n        description: year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: wind-onshore-share-wind-onshore-share-get\n      description: Wind Onshore Share\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.wind-onshore-share-wind-onshore-share-get\n\
  \      with:\n        country: tools.country\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: wind-onshore-share-daily-avg-wind-onshore-share-\n      description: Wind Onshore Share Daily Avg\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.wind-onshore-share-daily-avg-wind-onshore-share-\n      with:\n        country: tools.country\n        year: tools.year\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      - name: year\n        type: integer\n        description: year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: wind-offshore-share-wind-offshore-share-get\n      description: Wind Offshore Share\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ energy-charts-api.wind-offshore-share-wind-offshore-share-get\n      with:\n        country: tools.country\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: wind-offshore-share-daily-avg-wind-offshore-shar\n      description: Wind Offshore Share Daily Avg\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: energy-charts-api.wind-offshore-share-daily-avg-wind-offshore-shar\n      with:\n        country: tools.country\n        year: tools.year\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n      - name: year\n        type: integer\n        description: year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: frequency-frequency-get\n      description: Frequency\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: energy-charts-api.frequency-frequency-get\n      with:\n        region: tools.region\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: region\n        type: string\n        description: region\n      - name: start\n        type: string\n        description: start\n      - name: end\n        type: string\n        description: end\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/energy-charts-api/refs/heads/main/capabilities/energy-charts-api-capability.yaml
tags:
- Energy
- Charts
- Api
- API
tools:
- description: Public Power
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: public-power-public-power-get
- description: Public Power Forecast
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: public-power-forecast-public-power-forecast-get
- description: Total Power
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: total-power-total-power-get
- description: Installed Power
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: installed-power-installed-power-get
- description: Day Ahead Price
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: day-ahead-price-price-get
- description: Cross Border Electricity Trading
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cross-border-electricity-trading-cbet-get
- description: Cross Border Physical Flows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cross-border-physical-flows-cbpf-get
- description: Traffic Signal
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: traffic-signal-signal-get
- description: Renewable Share Forecast
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: renewable-share-forecast-ren-share-forecast-get
- description: Ren Share Daily Avg
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ren-share-daily-avg-ren-share-daily-avg-get
- description: Solar Share
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: solar-share-solar-share-get
- description: Solar Share Daily Avg
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: solar-share-daily-avg-solar-share-daily-avg-get
- description: Wind Onshore Share
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: wind-onshore-share-wind-onshore-share-get
- description: Wind Onshore Share Daily Avg
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: wind-onshore-share-daily-avg-wind-onshore-share-
- description: Wind Offshore Share
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: wind-offshore-share-wind-offshore-share-get
- description: Wind Offshore Share Daily Avg
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: wind-offshore-share-daily-avg-wind-offshore-shar
- description: Frequency
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: frequency-frequency-get
---

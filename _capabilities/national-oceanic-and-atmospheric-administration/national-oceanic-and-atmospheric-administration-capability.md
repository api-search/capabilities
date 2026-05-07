---
categories: []
consumed_apis: []
description: The NOAA Center for Operational Oceanographic Products and Services (CO-OPS) Data API provides observations and predictions from CO-OPS stations including water levels, tides, currents, meteorological data, and derived products. Operated by the National Oceanic and Atmospheric Administration (NOAA), U.S. Department of Commerce.
layout: capability
name: NOAA CO-OPS Data API
operations:
- description: Retrieve CO-OPS station observations and predictions
  method: GET
  name: getdata
  path: /datagetter
personas: []
provider_name: National Oceanic and Atmospheric Administration
provider_slug: national-oceanic-and-atmospheric-administration
search_terms:
- atmosphere
- oceanic
- retrieve co-ops station observations and predictions
- oceans
- weather
- and
- getdata
- federal government
- api
- atmospheric
- national
- administration
slug: national-oceanic-and-atmospheric-administration-capability
source_filename: national-oceanic-and-atmospheric-administration-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NOAA CO-OPS Data API\n  description: The NOAA Center for Operational Oceanographic Products and Services (CO-OPS) Data API provides observations\n    and predictions from CO-OPS stations including water levels, tides, currents, meteorological data, and derived products.\n    Operated by the National Oceanic and Atmospheric Administration (NOAA), U.S. Department of Commerce.\n  tags:\n  - National\n  - Oceanic\n  - And\n  - Atmospheric\n  - Administration\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: national-oceanic-and-atmospheric-administration\n    baseUri: https://api.tidesandcurrents.noaa.gov/api/prod\n    description: NOAA CO-OPS Data API HTTP API.\n    resources:\n    - name: datagetter\n      path: /datagetter\n      operations:\n      - name: getdata\n        method: GET\n        description: Retrieve CO-OPS station observations and predictions\n        inputParameters:\n\
  \        - name: station\n          in: query\n          type: string\n          required: true\n          description: 7-character CO-OPS station ID, or currents identifier.\n        - name: product\n          in: query\n          type: string\n          required: true\n          description: Data product to retrieve.\n        - name: begin_date\n          in: query\n          type: string\n          description: Start of the time window (yyyyMMdd, yyyyMMdd HH:mm, MM/dd/yyyy, or MM/dd/yyyy HH:mm).\n        - name: end_date\n          in: query\n          type: string\n          description: End of the time window.\n        - name: range\n          in: query\n          type: integer\n          description: Hours of data to retrieve relative to begin_date, end_date, or now.\n        - name: date\n          in: query\n          type: string\n          description: Convenience selector (today, latest, recent).\n        - name: datum\n          in: query\n          type: string\n         \
  \ description: Vertical datum reference for water level products.\n        - name: units\n          in: query\n          type: string\n          description: Unit system for returned values.\n        - name: time_zone\n          in: query\n          type: string\n          description: Time zone for timestamps.\n        - name: format\n          in: query\n          type: string\n          description: Response format.\n        - name: interval\n          in: query\n          type: string\n          description: Sampling interval for predictions and meteorological data.\n        - name: bin\n          in: query\n          type: integer\n          description: Bin number for currents requests.\n        - name: vel_type\n          in: query\n          type: string\n          description: Velocity reporting style for currents (speed_dir or default).\n        - name: application\n          in: query\n          type: string\n          description: Application identifier for the requesting client\
  \ (recommended).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: national-oceanic-and-atmospheric-administration-rest\n    description: REST adapter for NOAA CO-OPS Data API.\n    resources:\n    - path: /datagetter\n      name: getdata\n      operations:\n      - method: GET\n        name: getdata\n        description: Retrieve CO-OPS station observations and predictions\n        call: national-oceanic-and-atmospheric-administration.getdata\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: national-oceanic-and-atmospheric-administration-mcp\n    transport: http\n    description: MCP adapter for NOAA CO-OPS Data API for AI agent use.\n    tools:\n    - name: getdata\n      description: Retrieve CO-OPS station observations and predictions\n      hints:\n        readOnly: true\n  \
  \      destructive: false\n        idempotent: true\n      call: national-oceanic-and-atmospheric-administration.getdata\n      with:\n        station: tools.station\n        product: tools.product\n        begin_date: tools.begin_date\n        end_date: tools.end_date\n        range: tools.range\n        date: tools.date\n        datum: tools.datum\n        units: tools.units\n        time_zone: tools.time_zone\n        format: tools.format\n        interval: tools.interval\n        bin: tools.bin\n        vel_type: tools.vel_type\n        application: tools.application\n      inputParameters:\n      - name: station\n        type: string\n        description: 7-character CO-OPS station ID, or currents identifier.\n        required: true\n      - name: product\n        type: string\n        description: Data product to retrieve.\n        required: true\n      - name: begin_date\n        type: string\n        description: Start of the time window (yyyyMMdd, yyyyMMdd HH:mm, MM/dd/yyyy, or\
  \ MM/dd/yyyy HH:mm).\n      - name: end_date\n        type: string\n        description: End of the time window.\n      - name: range\n        type: integer\n        description: Hours of data to retrieve relative to begin_date, end_date, or now.\n      - name: date\n        type: string\n        description: Convenience selector (today, latest, recent).\n      - name: datum\n        type: string\n        description: Vertical datum reference for water level products.\n      - name: units\n        type: string\n        description: Unit system for returned values.\n      - name: time_zone\n        type: string\n        description: Time zone for timestamps.\n      - name: format\n        type: string\n        description: Response format.\n      - name: interval\n        type: string\n        description: Sampling interval for predictions and meteorological data.\n      - name: bin\n        type: integer\n        description: Bin number for currents requests.\n      - name: vel_type\n\
  \        type: string\n        description: Velocity reporting style for currents (speed_dir or default).\n      - name: application\n        type: string\n        description: Application identifier for the requesting client (recommended).\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/national-oceanic-and-atmospheric-administration/refs/heads/main/capabilities/national-oceanic-and-atmospheric-administration-capability.yaml
tags:
- National
- Oceanic
- And
- Atmospheric
- Administration
- API
tools:
- description: Retrieve CO-OPS station observations and predictions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdata
---

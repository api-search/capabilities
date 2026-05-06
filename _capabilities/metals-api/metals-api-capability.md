---
categories: []
consumed_apis: []
description: Metals-API provides a free, simple, and lightweight JSON API for current and historical precious metals rates and currency conversion. It supports real-time and historical data for gold, silver, platinum, palladium, and other metals in 170 world currencies.
layout: capability
name: Metals-API
operations:
- description: List supported symbols
  method: GET
  name: getsymbols
  path: /symbols
- description: Get latest rates
  method: GET
  name: getlatest
  path: /latest
- description: Get historical rates by date
  method: GET
  name: gethistoricalrates
  path: /{date}
- description: Convert between currencies and metals
  method: GET
  name: convert
  path: /convert
- description: Get rates over a time series
  method: GET
  name: gettimeseries
  path: /timeseries
- description: Get rate fluctuation
  method: GET
  name: getfluctuation
  path: /fluctuation
- description: Get gold prices by carat
  method: GET
  name: getcarat
  path: /carat
- description: Get daily lowest and highest prices
  method: GET
  name: getlowesthighest
  path: /lowest-highest/{date}
- description: Get OHLC data
  method: GET
  name: getohlc
  path: /open-high-low-close/{date}
personas: []
provider_name: Metals-API
provider_slug: metals-api
search_terms:
- getcarat
- get rate fluctuation
- get historical rates by date
- getlatest
- getsymbols
- gold
- precious metals
- get daily lowest and highest prices
- silver
- list supported symbols
- metals
- get latest rates
- gethistoricalrates
- financial data
- api
- get rates over a time series
- getohlc
- convert
- get gold prices by carat
- gettimeseries
- getfluctuation
- get ohlc data
- convert between currencies and metals
- getlowesthighest
- currency
slug: metals-api-capability
source_filename: metals-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Metals-API\n  description: Metals-API provides a free, simple, and lightweight JSON API for current and historical precious metals rates\n    and currency conversion. It supports real-time and historical data for gold, silver, platinum, palladium, and other metals\n    in 170 world currencies.\n  tags:\n  - Metals\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: metals-api\n    baseUri: https://metals-api.com/api\n    description: Metals-API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: access_key\n      value: '{{METALS_API_TOKEN}}'\n    resources:\n    - name: symbols\n      path: /symbols\n      operations:\n      - name: getsymbols\n        method: GET\n        description: List supported symbols\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: latest\n      path: /latest\n      operations:\n      - name: getlatest\n        method: GET\n        description: Get latest rates\n        inputParameters:\n        - name: unit\n          in: query\n          type: string\n          description: Unit of measure (e.g., troy_ounce, gram, kilogram).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: date\n      path: /{date}\n      operations:\n      - name: gethistoricalrates\n        method: GET\n        description: Get historical rates by date\n        inputParameters:\n        - name: date\n          in: path\n          type: string\n          required: true\n          description: Date in YYYY-MM-DD format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: convert\n      path: /convert\n      operations:\n      - name: convert\n        method:\
  \ GET\n        description: Convert between currencies and metals\n        inputParameters:\n        - name: from\n          in: query\n          type: string\n          required: true\n          description: Source currency or metal symbol.\n        - name: to\n          in: query\n          type: string\n          required: true\n          description: Target currency or metal symbol.\n        - name: amount\n          in: query\n          type: number\n          required: true\n          description: Amount to convert.\n        - name: date\n          in: query\n          type: string\n          description: Optional historical date in YYYY-MM-DD format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timeseries\n      path: /timeseries\n      operations:\n      - name: gettimeseries\n        method: GET\n        description: Get rates over a time series\n        inputParameters:\n        - name:\
  \ start_date\n          in: query\n          type: string\n          required: true\n        - name: end_date\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fluctuation\n      path: /fluctuation\n      operations:\n      - name: getfluctuation\n        method: GET\n        description: Get rate fluctuation\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          required: true\n        - name: end_date\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carat\n      path: /carat\n      operations:\n      - name: getcarat\n        method: GET\n        description: Get gold prices by carat\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lowest-highest-date\n      path: /lowest-highest/{date}\n      operations:\n      - name: getlowesthighest\n        method: GET\n        description: Get daily lowest and highest prices\n        inputParameters:\n        - name: date\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: open-high-low-close-date\n      path: /open-high-low-close/{date}\n      operations:\n      - name: getohlc\n        method: GET\n        description: Get OHLC data\n        inputParameters:\n        - name: date\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port:\
  \ 8080\n    namespace: metals-api-rest\n    description: REST adapter for Metals-API.\n    resources:\n    - path: /symbols\n      name: getsymbols\n      operations:\n      - method: GET\n        name: getsymbols\n        description: List supported symbols\n        call: metals-api.getsymbols\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /latest\n      name: getlatest\n      operations:\n      - method: GET\n        name: getlatest\n        description: Get latest rates\n        call: metals-api.getlatest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{date}\n      name: gethistoricalrates\n      operations:\n      - method: GET\n        name: gethistoricalrates\n        description: Get historical rates by date\n        call: metals-api.gethistoricalrates\n        with:\n          date: rest.date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /convert\n      name:\
  \ convert\n      operations:\n      - method: GET\n        name: convert\n        description: Convert between currencies and metals\n        call: metals-api.convert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /timeseries\n      name: gettimeseries\n      operations:\n      - method: GET\n        name: gettimeseries\n        description: Get rates over a time series\n        call: metals-api.gettimeseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fluctuation\n      name: getfluctuation\n      operations:\n      - method: GET\n        name: getfluctuation\n        description: Get rate fluctuation\n        call: metals-api.getfluctuation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carat\n      name: getcarat\n      operations:\n      - method: GET\n        name: getcarat\n        description: Get gold prices by carat\n        call: metals-api.getcarat\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lowest-highest/{date}\n      name: getlowesthighest\n      operations:\n      - method: GET\n        name: getlowesthighest\n        description: Get daily lowest and highest prices\n        call: metals-api.getlowesthighest\n        with:\n          date: rest.date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /open-high-low-close/{date}\n      name: getohlc\n      operations:\n      - method: GET\n        name: getohlc\n        description: Get OHLC data\n        call: metals-api.getohlc\n        with:\n          date: rest.date\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: metals-api-mcp\n    transport: http\n    description: MCP adapter for Metals-API for AI agent use.\n    tools:\n    - name: getsymbols\n      description: List supported symbols\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: metals-api.getsymbols\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlatest\n      description: Get latest rates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-api.getlatest\n      with:\n        unit: tools.unit\n      inputParameters:\n      - name: unit\n        type: string\n        description: Unit of measure (e.g., troy_ounce, gram, kilogram).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethistoricalrates\n      description: Get historical rates by date\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-api.gethistoricalrates\n      with:\n        date: tools.date\n      inputParameters:\n      - name: date\n        type: string\n        description: Date in YYYY-MM-DD format.\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: convert\n      description: Convert between currencies and metals\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-api.convert\n      with:\n        from: tools.from\n        to: tools.to\n        amount: tools.amount\n        date: tools.date\n      inputParameters:\n      - name: from\n        type: string\n        description: Source currency or metal symbol.\n        required: true\n      - name: to\n        type: string\n        description: Target currency or metal symbol.\n        required: true\n      - name: amount\n        type: number\n        description: Amount to convert.\n        required: true\n      - name: date\n        type: string\n        description: Optional historical date in YYYY-MM-DD format.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettimeseries\n      description: Get rates over a time series\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-api.gettimeseries\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n      inputParameters:\n      - name: start_date\n        type: string\n        description: start_date\n        required: true\n      - name: end_date\n        type: string\n        description: end_date\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfluctuation\n      description: Get rate fluctuation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-api.getfluctuation\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n      inputParameters:\n      - name: start_date\n        type: string\n        description: start_date\n        required: true\n      - name: end_date\n        type: string\n        description: end_date\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcarat\n      description: Get gold prices by carat\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-api.getcarat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlowesthighest\n      description: Get daily lowest and highest prices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-api.getlowesthighest\n      with:\n        date: tools.date\n      inputParameters:\n      - name: date\n        type: string\n        description: date\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getohlc\n      description: Get OHLC data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-api.getohlc\n      with:\n        date: tools.date\n  \
  \    inputParameters:\n      - name: date\n        type: string\n        description: date\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    METALS_API_TOKEN: METALS_API_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/metals-api/refs/heads/main/capabilities/metals-api-capability.yaml
tags:
- Metals
- Api
- API
tools:
- description: List supported symbols
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsymbols
- description: Get latest rates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlatest
- description: Get historical rates by date
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethistoricalrates
- description: Convert between currencies and metals
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: convert
- description: Get rates over a time series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettimeseries
- description: Get rate fluctuation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfluctuation
- description: Get gold prices by carat
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcarat
- description: Get daily lowest and highest prices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlowesthighest
- description: Get OHLC data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getohlc
---

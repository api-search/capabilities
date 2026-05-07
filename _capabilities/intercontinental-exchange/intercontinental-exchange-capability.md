---
categories: []
consumed_apis: []
description: The ICE Consolidated Feed API provides access to ICE Data Services real-time and delayed market data from exchanges operated by Intercontinental Exchange including ICE Futures, NYSE, and other trading venues.
layout: capability
name: ICE Consolidated Feed API
operations:
- description: List instruments
  method: GET
  name: listinstruments
  path: /marketdata/instruments
- description: Get market quotes
  method: GET
  name: getquotes
  path: /marketdata/quotes
- description: Get market data history
  method: GET
  name: getmarkethistory
  path: /marketdata/history
- description: List exchanges
  method: GET
  name: listexchanges
  path: /reference/exchanges
personas: []
provider_name: Intercontinental Exchange
provider_slug: intercontinental-exchange
search_terms:
- listinstruments
- get market quotes
- get market data history
- listexchanges
- financial exchanges
- trading
- market data
- list instruments
- list exchanges
- getmarkethistory
- getquotes
- nyse
- api
- exchange
- intercontinental
- commodities
slug: intercontinental-exchange-capability
source_filename: intercontinental-exchange-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ICE Consolidated Feed API\n  description: The ICE Consolidated Feed API provides access to ICE Data Services real-time and delayed market data from exchanges\n    operated by Intercontinental Exchange including ICE Futures, NYSE, and other trading venues.\n  tags:\n  - Intercontinental\n  - Exchange\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: intercontinental-exchange\n    baseUri: https://api.theice.com\n    description: ICE Consolidated Feed API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{INTERCONTINENTAL_EXCHANGE_TOKEN}}'\n    resources:\n    - name: marketdata-instruments\n      path: /marketdata/instruments\n      operations:\n      - name: listinstruments\n        method: GET\n        description: List instruments\n        inputParameters:\n        - name: exchange\n          in: query\n \
  \         type: string\n          description: Filter by exchange code.\n        - name: productType\n          in: query\n          type: string\n          description: Filter by product type (futures, options, etc.).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: marketdata-quotes\n      path: /marketdata/quotes\n      operations:\n      - name: getquotes\n        method: GET\n        description: Get market quotes\n        inputParameters:\n        - name: instrumentId\n          in: query\n          type: string\n          required: true\n          description: The instrument identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: marketdata-history\n      path: /marketdata/history\n      operations:\n      - name: getmarkethistory\n        method: GET\n        description: Get market data history\n\
  \        inputParameters:\n        - name: instrumentId\n          in: query\n          type: string\n          required: true\n          description: The instrument identifier.\n        - name: startDate\n          in: query\n          type: string\n          description: Start date for historical data.\n        - name: endDate\n          in: query\n          type: string\n          description: End date for historical data.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reference-exchanges\n      path: /reference/exchanges\n      operations:\n      - name: listexchanges\n        method: GET\n        description: List exchanges\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: intercontinental-exchange-rest\n    description: REST adapter for ICE Consolidated\
  \ Feed API.\n    resources:\n    - path: /marketdata/instruments\n      name: listinstruments\n      operations:\n      - method: GET\n        name: listinstruments\n        description: List instruments\n        call: intercontinental-exchange.listinstruments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /marketdata/quotes\n      name: getquotes\n      operations:\n      - method: GET\n        name: getquotes\n        description: Get market quotes\n        call: intercontinental-exchange.getquotes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /marketdata/history\n      name: getmarkethistory\n      operations:\n      - method: GET\n        name: getmarkethistory\n        description: Get market data history\n        call: intercontinental-exchange.getmarkethistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reference/exchanges\n      name: listexchanges\n    \
  \  operations:\n      - method: GET\n        name: listexchanges\n        description: List exchanges\n        call: intercontinental-exchange.listexchanges\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: intercontinental-exchange-mcp\n    transport: http\n    description: MCP adapter for ICE Consolidated Feed API for AI agent use.\n    tools:\n    - name: listinstruments\n      description: List instruments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercontinental-exchange.listinstruments\n      with:\n        exchange: tools.exchange\n        productType: tools.productType\n      inputParameters:\n      - name: exchange\n        type: string\n        description: Filter by exchange code.\n      - name: productType\n        type: string\n        description: Filter by product type (futures, options, etc.).\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getquotes\n      description: Get market quotes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercontinental-exchange.getquotes\n      with:\n        instrumentId: tools.instrumentId\n      inputParameters:\n      - name: instrumentId\n        type: string\n        description: The instrument identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmarkethistory\n      description: Get market data history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercontinental-exchange.getmarkethistory\n      with:\n        instrumentId: tools.instrumentId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      inputParameters:\n      - name: instrumentId\n        type: string\n        description: The instrument identifier.\n        required: true\n      - name:\
  \ startDate\n        type: string\n        description: Start date for historical data.\n      - name: endDate\n        type: string\n        description: End date for historical data.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listexchanges\n      description: List exchanges\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercontinental-exchange.listexchanges\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    INTERCONTINENTAL_EXCHANGE_TOKEN: INTERCONTINENTAL_EXCHANGE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/intercontinental-exchange/refs/heads/main/capabilities/intercontinental-exchange-capability.yaml
tags:
- Intercontinental
- Exchange
- API
tools:
- description: List instruments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstruments
- description: Get market quotes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquotes
- description: Get market data history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmarkethistory
- description: List exchanges
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listexchanges
---

---
categories: []
consumed_apis: []
description: Unified workflow for accessing real-time and historical market data including prices, quotes, news, tick history, options, and FX rates. Used by traders and market data analysts.
layout: capability
name: FactSet Market Data and Pricing
operations:
- description: Get equity prices.
  method: GET
  name: get-prices
  path: /v1/prices
- description: Get real-time quotes.
  method: GET
  name: get-quotes
  path: /v1/quotes
- description: Get options data.
  method: GET
  name: get-options
  path: /v1/options
- description: Get FX rates.
  method: GET
  name: get-fx
  path: /v1/fx-rates
- description: Get tick history.
  method: GET
  name: get-ticks
  path: /v1/tick-history
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- real-time quotes.
- research
- market data
- get intraday ticks
- get tick history
- investment analytics
- global equity prices.
- get real-time news.
- get intraday tick history.
- get options
- get rt news
- get options data.
- get fx
- get tick history.
- portfolio analytics
- get prices
- get equity prices.
- get real-time time series.
- foreign exchange rates.
- options data.
- get real-time quotes.
- factset
- get quotes
- financial data
- get price alerts
- real-time data
- get price alerting data.
- historical tick data.
- get fx rates.
- get global prices
- get global equity prices.
- financial
- get historical tick data.
- get equity prices and returns.
- pricing
- get fx rates
- get foreign exchange rates.
- get time series
- get rt quotes
- get ticks
slug: market-data-pricing
source_filename: market-data-pricing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FactSet Market Data and Pricing\n  description: Unified workflow for accessing real-time and historical market data including prices, quotes, news, tick history,\n    options, and FX rates. Used by traders and market data analysts.\n  tags:\n  - FactSet\n  - Market Data\n  - Real-Time Data\n  - Pricing\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACTSET_USERNAME: FACTSET_USERNAME\n    FACTSET_PASSWORD: FACTSET_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: factset-global-prices\n    baseUri: https://api.factset.com/content\n    description: Global equity prices, volume, turnover, and VWAP data.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: global_prices\n      path: /\n      description: Global Prices API resources.\n      operations:\n      - name: list-global-prices\n\
  \        method: GET\n        description: List Global Prices resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password:\
  \ '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri:\
  \ https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description:\
  \ Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n\
  \      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: market-data-api\n    description: Unified REST API for market data and pricing.\n    resources:\n    - path: /v1/prices\n      name: prices\n      description: Global equity prices.\n      operations:\n      - method: GET\n        name: get-prices\n        description: Get equity prices.\n        call: factset-prices.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/quotes\n      name: quotes\n      description: Real-time quotes.\n      operations:\n    \
  \  - method: GET\n        name: get-quotes\n        description: Get real-time quotes.\n        call: factset-rt-quotes.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/options\n      name: options\n      description: Options data.\n      operations:\n      - method: GET\n        name: get-options\n        description: Get options data.\n        call: factset-options.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fx-rates\n      name: fx-rates\n      description: Foreign exchange rates.\n      operations:\n      - method: GET\n        name: get-fx\n        description: Get FX rates.\n        call: factset-fx.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tick-history\n      name: tick-history\n      description: Historical tick data.\n      operations:\n      - method: GET\n        name: get-ticks\n        description: Get tick history.\n    \
  \    call: factset-tick.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: market-data-mcp\n    transport: http\n    description: MCP server for AI-assisted market data analysis.\n    tools:\n    - name: get-global-prices\n      description: Get global equity prices.\n      hints:\n        readOnly: true\n      call: factset-global-prices.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-prices\n      description: Get equity prices and returns.\n      hints:\n        readOnly: true\n      call: factset-prices.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rt-quotes\n      description: Get real-time quotes.\n      hints:\n        readOnly: true\n      call: factset-rt-quotes.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rt-news\n      description: Get real-time news.\n      hints:\n     \
  \   readOnly: true\n      call: factset-rt-news.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-time-series\n      description: Get real-time time series.\n      hints:\n        readOnly: true\n      call: factset-rt-ts.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-price-alerts\n      description: Get price alerting data.\n      hints:\n        readOnly: true\n      call: factset-rt-alert.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-options\n      description: Get options data.\n      hints:\n        readOnly: true\n      call: factset-options.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fx-rates\n      description: Get foreign exchange rates.\n      hints:\n        readOnly: true\n      call: factset-fx.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-intraday-ticks\n   \
  \   description: Get intraday tick history.\n      hints:\n        readOnly: true\n      call: factset-intraday.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tick-history\n      description: Get historical tick data.\n      hints:\n        readOnly: true\n      call: factset-tick.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/market-data-pricing.yaml
tags:
- FactSet
- Market Data
- Real-Time Data
- Pricing
tools:
- description: Get global equity prices.
  hints:
    readOnly: true
  name: get-global-prices
- description: Get equity prices and returns.
  hints:
    readOnly: true
  name: get-prices
- description: Get real-time quotes.
  hints:
    readOnly: true
  name: get-rt-quotes
- description: Get real-time news.
  hints:
    readOnly: true
  name: get-rt-news
- description: Get real-time time series.
  hints:
    readOnly: true
  name: get-time-series
- description: Get price alerting data.
  hints:
    readOnly: true
  name: get-price-alerts
- description: Get options data.
  hints:
    readOnly: true
  name: get-options
- description: Get foreign exchange rates.
  hints:
    readOnly: true
  name: get-fx-rates
- description: Get intraday tick history.
  hints:
    readOnly: true
  name: get-intraday-ticks
- description: Get historical tick data.
  hints:
    readOnly: true
  name: get-tick-history
---

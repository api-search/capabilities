---
categories: []
consumed_apis: []
description: The Level2 Strategy Builder API provides programmatic access to market data, technical analysis, and trading strategy capabilities offered by the Level2 platform (by Bytemine Technologies Ltd.). It includes endpoints for retrieving candlestick pattern detection, ticker trend analysis, historical OHLC (Open-High-Low-Close) data, similar stock discovery, and company fundamental summaries. These endpoints power the Level2 visual no-code strategy builder used by over 50,000 traders to create, backtest, and deploy automated trading strategies without writing code.
layout: capability
name: Level2 Strategy Builder API
operations:
- description: Check for candlestick patterns
  method: GET
  name: checkforcandlestick
  path: /checkForCandlestick/{api_key}/{ticker}/{timeframe}
- description: Get ticker trend analysis
  method: GET
  name: gettickertrend
  path: /getTickerTrend/{api_key}/{ticker}/{timeframe}
- description: Get OHLC historical data
  method: GET
  name: getohlcdata
  path: /olhc/{api_key}/{ticker}/{timeframe}/{range}
- description: Get similar stocks
  method: GET
  name: getsimilarstocks
  path: /similar/{api_key}/{ticker}
- description: Get company summary
  method: GET
  name: getcompanysummary
  path: /summary/{api_key}/{ticker}
personas: []
provider_name: level2
provider_slug: level2
search_terms:
- gettickertrend
- getsimilarstocks
- get ohlc historical data
- getohlcdata
- get ticker trend analysis
- api
- check for candlestick patterns
- get company summary
- getcompanysummary
- get similar stocks
- checkforcandlestick
- level2
slug: level2-capability
source_filename: level2-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Level2 Strategy Builder API\n  description: The Level2 Strategy Builder API provides programmatic access to market data, technical analysis, and trading\n    strategy capabilities offered by the Level2 platform (by Bytemine Technologies Ltd.). It includes endpoints for retrieving\n    candlestick pattern detection, ticker trend analysis, historical OHLC (Open-High-Low-Close) data, similar stock discovery,\n    and company fundamental summaries. These endpoints power the Level2 visual no-code strategy builder used by over 50,000\n    traders to create, backtest, and deploy automated trading strategies without writing code.\n  tags:\n  - Level2\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: level2\n    baseUri: https://app.bytemine.io/api\n    description: Level2 Strategy Builder API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: api_key\n\
  \      value: '{{LEVEL2_TOKEN}}'\n    resources:\n    - name: checkforcandlestick-api-key-ticker-timeframe\n      path: /checkForCandlestick/{api_key}/{ticker}/{timeframe}\n      operations:\n      - name: checkforcandlestick\n        method: GET\n        description: Check for candlestick patterns\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gettickertrend-api-key-ticker-timeframe\n      path: /getTickerTrend/{api_key}/{ticker}/{timeframe}\n      operations:\n      - name: gettickertrend\n        method: GET\n        description: Get ticker trend analysis\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: olhc-api-key-ticker-timeframe-range\n      path: /olhc/{api_key}/{ticker}/{timeframe}/{range}\n      operations:\n      - name: getohlcdata\n        method: GET\n        description: Get OHLC historical\
  \ data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: similar-api-key-ticker\n      path: /similar/{api_key}/{ticker}\n      operations:\n      - name: getsimilarstocks\n        method: GET\n        description: Get similar stocks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: summary-api-key-ticker\n      path: /summary/{api_key}/{ticker}\n      operations:\n      - name: getcompanysummary\n        method: GET\n        description: Get company summary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: level2-rest\n    description: REST adapter for Level2 Strategy Builder API.\n    resources:\n    - path: /checkForCandlestick/{api_key}/{ticker}/{timeframe}\n      name:\
  \ checkforcandlestick\n      operations:\n      - method: GET\n        name: checkforcandlestick\n        description: Check for candlestick patterns\n        call: level2.checkforcandlestick\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /getTickerTrend/{api_key}/{ticker}/{timeframe}\n      name: gettickertrend\n      operations:\n      - method: GET\n        name: gettickertrend\n        description: Get ticker trend analysis\n        call: level2.gettickertrend\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /olhc/{api_key}/{ticker}/{timeframe}/{range}\n      name: getohlcdata\n      operations:\n      - method: GET\n        name: getohlcdata\n        description: Get OHLC historical data\n        call: level2.getohlcdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /similar/{api_key}/{ticker}\n      name: getsimilarstocks\n      operations:\n      - method: GET\n\
  \        name: getsimilarstocks\n        description: Get similar stocks\n        call: level2.getsimilarstocks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /summary/{api_key}/{ticker}\n      name: getcompanysummary\n      operations:\n      - method: GET\n        name: getcompanysummary\n        description: Get company summary\n        call: level2.getcompanysummary\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: level2-mcp\n    transport: http\n    description: MCP adapter for Level2 Strategy Builder API for AI agent use.\n    tools:\n    - name: checkforcandlestick\n      description: Check for candlestick patterns\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: level2.checkforcandlestick\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettickertrend\n      description: Get ticker\
  \ trend analysis\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: level2.gettickertrend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getohlcdata\n      description: Get OHLC historical data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: level2.getohlcdata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsimilarstocks\n      description: Get similar stocks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: level2.getsimilarstocks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcompanysummary\n      description: Get company summary\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: level2.getcompanysummary\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\nbinds:\n- namespace: env\n  keys:\n    LEVEL2_TOKEN: LEVEL2_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/level2/refs/heads/main/capabilities/level2-capability.yaml
tags:
- Level2
- API
tools:
- description: Check for candlestick patterns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: checkforcandlestick
- description: Get ticker trend analysis
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettickertrend
- description: Get OHLC historical data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getohlcdata
- description: Get similar stocks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsimilarstocks
- description: Get company summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompanysummary
---

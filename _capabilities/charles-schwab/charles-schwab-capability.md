---
categories: []
consumed_apis: []
description: REST API for retrieving real-time and historical market data from Charles Schwab including quotes, option chains, price history, market hours, instrument metadata, and movers for major US indices.
layout: capability
name: Charles Schwab Market Data API
operations:
- description: Get quotes for one or more symbols
  method: GET
  name: getquotes
  path: /quotes
- description: Get quote for a specific symbol
  method: GET
  name: getquote
  path: /{symbol_id}/quotes
- description: Get option chain for a symbol
  method: GET
  name: getoptionchains
  path: /chains
- description: Get option expiration chain for a symbol
  method: GET
  name: getoptionexpirationchain
  path: /expirationchain
- description: Get price history candles for a symbol
  method: GET
  name: getpricehistory
  path: /pricehistory
- description: Get top movers for an index
  method: GET
  name: getmovers
  path: /movers/{symbol_id}
- description: Get market hours for one or more markets
  method: GET
  name: getmarkethours
  path: /markets
- description: Get market hours for a single market
  method: GET
  name: getmarkethoursformarket
  path: /markets/{market_id}
- description: Search instruments by symbol or CUSIP
  method: GET
  name: searchinstruments
  path: /instruments
personas: []
provider_name: Charles Schwab
provider_slug: charles-schwab
search_terms:
- get price history candles for a symbol
- getoptionexpirationchain
- get option expiration chain for a symbol
- getquotes
- investing
- oauth 2.0
- searchinstruments
- api
- get market hours for one or more markets
- getmovers
- orders
- get quote for a specific symbol
- brokerage
- get top movers for an index
- get option chain for a symbol
- getquote
- get quotes for one or more symbols
- financial services
- trading
- getoptionchains
- accounts
- schwab
- charles
- search instruments by symbol or cusip
- getpricehistory
- get market hours for a single market
- banking
- market data
- getmarkethoursformarket
- getmarkethours
slug: charles-schwab-capability
source_filename: charles-schwab-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Charles Schwab Market Data API\n  description: REST API for retrieving real-time and historical market data from Charles Schwab including quotes, option chains,\n    price history, market hours, instrument metadata, and movers for major US indices.\n  tags:\n  - Charles\n  - Schwab\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: charles-schwab\n    baseUri: https://api.schwabapi.com/marketdata/v1\n    description: Charles Schwab Market Data API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CHARLES_SCHWAB_TOKEN}}'\n    resources:\n    - name: quotes\n      path: /quotes\n      operations:\n      - name: getquotes\n        method: GET\n        description: Get quotes for one or more symbols\n        inputParameters:\n        - name: symbols\n          in: query\n          type: string\n          required: true\n          description: Comma-separated\
  \ list of ticker symbols.\n        - name: fields\n          in: query\n          type: string\n        - name: indicative\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: symbol-id-quotes\n      path: /{symbol_id}/quotes\n      operations:\n      - name: getquote\n        method: GET\n        description: Get quote for a specific symbol\n        inputParameters:\n        - name: symbol_id\n          in: path\n          type: string\n          required: true\n        - name: fields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chains\n      path: /chains\n      operations:\n      - name: getoptionchains\n        method: GET\n        description: Get option chain for a symbol\n        inputParameters:\n        - name:\
  \ symbol\n          in: query\n          type: string\n          required: true\n        - name: contractType\n          in: query\n          type: string\n        - name: strikeCount\n          in: query\n          type: integer\n        - name: includeQuotes\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: expirationchain\n      path: /expirationchain\n      operations:\n      - name: getoptionexpirationchain\n        method: GET\n        description: Get option expiration chain for a symbol\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pricehistory\n      path: /pricehistory\n      operations:\n      - name: getpricehistory\n        method:\
  \ GET\n        description: Get price history candles for a symbol\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n        - name: periodType\n          in: query\n          type: string\n        - name: period\n          in: query\n          type: integer\n        - name: frequencyType\n          in: query\n          type: string\n        - name: frequency\n          in: query\n          type: integer\n        - name: startDate\n          in: query\n          type: integer\n        - name: endDate\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: movers-symbol-id\n      path: /movers/{symbol_id}\n      operations:\n      - name: getmovers\n        method: GET\n        description: Get top movers for an index\n        inputParameters:\n        - name: symbol_id\n          in: path\n\
  \          type: string\n          required: true\n          description: Index symbol such as $DJI, $COMPX, or $SPX.\n        - name: sort\n          in: query\n          type: string\n        - name: frequency\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: markets\n      path: /markets\n      operations:\n      - name: getmarkethours\n        method: GET\n        description: Get market hours for one or more markets\n        inputParameters:\n        - name: markets\n          in: query\n          type: string\n          required: true\n        - name: date\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: markets-market-id\n      path: /markets/{market_id}\n      operations:\n      - name: getmarkethoursformarket\n\
  \        method: GET\n        description: Get market hours for a single market\n        inputParameters:\n        - name: market_id\n          in: path\n          type: string\n          required: true\n        - name: date\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instruments\n      path: /instruments\n      operations:\n      - name: searchinstruments\n        method: GET\n        description: Search instruments by symbol or CUSIP\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n        - name: projection\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: charles-schwab-rest\n\
  \    description: REST adapter for Charles Schwab Market Data API.\n    resources:\n    - path: /quotes\n      name: getquotes\n      operations:\n      - method: GET\n        name: getquotes\n        description: Get quotes for one or more symbols\n        call: charles-schwab.getquotes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{symbol_id}/quotes\n      name: getquote\n      operations:\n      - method: GET\n        name: getquote\n        description: Get quote for a specific symbol\n        call: charles-schwab.getquote\n        with:\n          symbol_id: rest.symbol_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /chains\n      name: getoptionchains\n      operations:\n      - method: GET\n        name: getoptionchains\n        description: Get option chain for a symbol\n        call: charles-schwab.getoptionchains\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /expirationchain\n      name: getoptionexpirationchain\n      operations:\n      - method: GET\n        name: getoptionexpirationchain\n        description: Get option expiration chain for a symbol\n        call: charles-schwab.getoptionexpirationchain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pricehistory\n      name: getpricehistory\n      operations:\n      - method: GET\n        name: getpricehistory\n        description: Get price history candles for a symbol\n        call: charles-schwab.getpricehistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /movers/{symbol_id}\n      name: getmovers\n      operations:\n      - method: GET\n        name: getmovers\n        description: Get top movers for an index\n        call: charles-schwab.getmovers\n        with:\n          symbol_id: rest.symbol_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /markets\n\
  \      name: getmarkethours\n      operations:\n      - method: GET\n        name: getmarkethours\n        description: Get market hours for one or more markets\n        call: charles-schwab.getmarkethours\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /markets/{market_id}\n      name: getmarkethoursformarket\n      operations:\n      - method: GET\n        name: getmarkethoursformarket\n        description: Get market hours for a single market\n        call: charles-schwab.getmarkethoursformarket\n        with:\n          market_id: rest.market_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instruments\n      name: searchinstruments\n      operations:\n      - method: GET\n        name: searchinstruments\n        description: Search instruments by symbol or CUSIP\n        call: charles-schwab.searchinstruments\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n  \
  \  port: 9090\n    namespace: charles-schwab-mcp\n    transport: http\n    description: MCP adapter for Charles Schwab Market Data API for AI agent use.\n    tools:\n    - name: getquotes\n      description: Get quotes for one or more symbols\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charles-schwab.getquotes\n      with:\n        symbols: tools.symbols\n        fields: tools.fields\n        indicative: tools.indicative\n      inputParameters:\n      - name: symbols\n        type: string\n        description: Comma-separated list of ticker symbols.\n        required: true\n      - name: fields\n        type: string\n        description: fields\n      - name: indicative\n        type: boolean\n        description: indicative\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getquote\n      description: Get quote for a specific symbol\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: charles-schwab.getquote\n      with:\n        symbol_id: tools.symbol_id\n        fields: tools.fields\n      inputParameters:\n      - name: symbol_id\n        type: string\n        description: symbol_id\n        required: true\n      - name: fields\n        type: string\n        description: fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoptionchains\n      description: Get option chain for a symbol\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charles-schwab.getoptionchains\n      with:\n        symbol: tools.symbol\n        contractType: tools.contractType\n        strikeCount: tools.strikeCount\n        includeQuotes: tools.includeQuotes\n      inputParameters:\n      - name: symbol\n        type: string\n        description: symbol\n        required: true\n      - name: contractType\n        type: string\n        description: contractType\n\
  \      - name: strikeCount\n        type: integer\n        description: strikeCount\n      - name: includeQuotes\n        type: boolean\n        description: includeQuotes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoptionexpirationchain\n      description: Get option expiration chain for a symbol\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charles-schwab.getoptionexpirationchain\n      with:\n        symbol: tools.symbol\n      inputParameters:\n      - name: symbol\n        type: string\n        description: symbol\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpricehistory\n      description: Get price history candles for a symbol\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charles-schwab.getpricehistory\n      with:\n        symbol: tools.symbol\n        periodType:\
  \ tools.periodType\n        period: tools.period\n        frequencyType: tools.frequencyType\n        frequency: tools.frequency\n        startDate: tools.startDate\n        endDate: tools.endDate\n      inputParameters:\n      - name: symbol\n        type: string\n        description: symbol\n        required: true\n      - name: periodType\n        type: string\n        description: periodType\n      - name: period\n        type: integer\n        description: period\n      - name: frequencyType\n        type: string\n        description: frequencyType\n      - name: frequency\n        type: integer\n        description: frequency\n      - name: startDate\n        type: integer\n        description: startDate\n      - name: endDate\n        type: integer\n        description: endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmovers\n      description: Get top movers for an index\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: charles-schwab.getmovers\n      with:\n        symbol_id: tools.symbol_id\n        sort: tools.sort\n        frequency: tools.frequency\n      inputParameters:\n      - name: symbol_id\n        type: string\n        description: Index symbol such as $DJI, $COMPX, or $SPX.\n        required: true\n      - name: sort\n        type: string\n        description: sort\n      - name: frequency\n        type: integer\n        description: frequency\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmarkethours\n      description: Get market hours for one or more markets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charles-schwab.getmarkethours\n      with:\n        markets: tools.markets\n        date: tools.date\n      inputParameters:\n      - name: markets\n        type: string\n        description: markets\n        required: true\n      - name: date\n       \
  \ type: string\n        description: date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmarkethoursformarket\n      description: Get market hours for a single market\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charles-schwab.getmarkethoursformarket\n      with:\n        market_id: tools.market_id\n        date: tools.date\n      inputParameters:\n      - name: market_id\n        type: string\n        description: market_id\n        required: true\n      - name: date\n        type: string\n        description: date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchinstruments\n      description: Search instruments by symbol or CUSIP\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: charles-schwab.searchinstruments\n      with:\n        symbol: tools.symbol\n        projection: tools.projection\n   \
  \   inputParameters:\n      - name: symbol\n        type: string\n        description: symbol\n        required: true\n      - name: projection\n        type: string\n        description: projection\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHARLES_SCHWAB_TOKEN: CHARLES_SCHWAB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/charles-schwab/refs/heads/main/capabilities/charles-schwab-capability.yaml
tags:
- Charles
- Schwab
- API
tools:
- description: Get quotes for one or more symbols
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquotes
- description: Get quote for a specific symbol
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquote
- description: Get option chain for a symbol
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoptionchains
- description: Get option expiration chain for a symbol
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoptionexpirationchain
- description: Get price history candles for a symbol
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpricehistory
- description: Get top movers for an index
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmovers
- description: Get market hours for one or more markets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmarkethours
- description: Get market hours for a single market
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmarkethoursformarket
- description: Search instruments by symbol or CUSIP
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchinstruments
---

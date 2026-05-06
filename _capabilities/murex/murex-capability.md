---
categories: []
consumed_apis: []
description: Real-time and historical market data API providing quotes, yield curves, volatility surfaces, and reference data for pricing and valuation on the Murex MX.3 platform.
layout: capability
name: Murex MX.3 Market Data API
operations:
- description: Murex Get market quotes
  method: GET
  name: getquotes
  path: /quotes
- description: Murex Get historical quotes
  method: GET
  name: getquotehistory
  path: /quotes/history
- description: Murex List available curves
  method: GET
  name: listcurves
  path: /curves
- description: Murex Get curve data
  method: GET
  name: getcurve
  path: /curves/{curveId}
- description: Murex List volatility surfaces
  method: GET
  name: listvolatilitysurfaces
  path: /volatility/surfaces
- description: Murex Get volatility surface data
  method: GET
  name: getvolatilitysurface
  path: /volatility/surfaces/{surfaceId}
- description: Murex Get FX rates
  method: GET
  name: getfxrates
  path: /fx/rates
- description: Murex Get FX rate history
  method: GET
  name: getfxratehistory
  path: /fx/rates/history
- description: Murex List market calendars
  method: GET
  name: listcalendars
  path: /reference/calendars
- description: Murex List currencies
  method: GET
  name: listcurrencies
  path: /reference/currencies
personas: []
provider_name: Murex
provider_slug: murex
search_terms:
- murex get market quotes
- getfxratehistory
- murex list currencies
- financial services
- listcurves
- risk management
- getquotehistory
- listcalendars
- murex get curve data
- getvolatilitysurface
- trading
- getfxrates
- api
- getquotes
- murex list market calendars
- murex get historical quotes
- getcurve
- listvolatilitysurfaces
- murex get fx rate history
- murex
- murex list volatility surfaces
- murex list available curves
- listcurrencies
- capital markets
- enterprise software
- murex get volatility surface data
- murex get fx rates
- fintech
slug: murex-capability
source_filename: murex-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Murex MX.3 Market Data API\n  description: Real-time and historical market data API providing quotes, yield curves, volatility surfaces, and reference\n    data for pricing and valuation on the Murex MX.3 platform.\n  tags:\n  - Murex\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: murex\n    baseUri: https://api.murex.com/v1/marketdata\n    description: Murex MX.3 Market Data API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MUREX_TOKEN}}'\n    resources:\n    - name: quotes\n      path: /quotes\n      operations:\n      - name: getquotes\n        method: GET\n        description: Murex Get market quotes\n        inputParameters:\n        - name: instrumentIds\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of instrument identifiers\n        - name: fields\n          in: query\n\
  \          type: string\n          description: Comma-separated list of quote fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: quotes-history\n      path: /quotes/history\n      operations:\n      - name: getquotehistory\n        method: GET\n        description: Murex Get historical quotes\n        inputParameters:\n        - name: instrumentId\n          in: query\n          type: string\n          required: true\n          description: Instrument identifier\n        - name: fromDate\n          in: query\n          type: string\n          required: true\n          description: Start date\n        - name: toDate\n          in: query\n          type: string\n          required: true\n          description: End date\n        - name: frequency\n          in: query\n          type: string\n          description: Data frequency\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: curves\n      path: /curves\n      operations:\n      - name: listcurves\n        method: GET\n        description: Murex List available curves\n        inputParameters:\n        - name: currency\n          in: query\n          type: string\n          description: Filter by currency\n        - name: curveType\n          in: query\n          type: string\n          description: Filter by curve type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: curves-curveid\n      path: /curves/{curveId}\n      operations:\n      - name: getcurve\n        method: GET\n        description: Murex Get curve data\n        inputParameters:\n        - name: curveId\n          in: path\n          type: string\n          required: true\n          description: Curve unique identifier\n        - name: asOfDate\n          in: query\n      \
  \    type: string\n          description: Curve valuation date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: volatility-surfaces\n      path: /volatility/surfaces\n      operations:\n      - name: listvolatilitysurfaces\n        method: GET\n        description: Murex List volatility surfaces\n        inputParameters:\n        - name: underlying\n          in: query\n          type: string\n          description: Filter by underlying instrument or index\n        - name: assetClass\n          in: query\n          type: string\n          description: Filter by asset class\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: volatility-surfaces-surfaceid\n      path: /volatility/surfaces/{surfaceId}\n      operations:\n      - name: getvolatilitysurface\n        method: GET\n        description: Murex Get volatility\
  \ surface data\n        inputParameters:\n        - name: surfaceId\n          in: path\n          type: string\n          required: true\n          description: Volatility surface identifier\n        - name: asOfDate\n          in: query\n          type: string\n          description: Surface valuation date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fx-rates\n      path: /fx/rates\n      operations:\n      - name: getfxrates\n        method: GET\n        description: Murex Get FX rates\n        inputParameters:\n        - name: currencyPairs\n          in: query\n          type: string\n          required: true\n          description: Comma-separated currency pairs (e.g., EURUSD,GBPUSD)\n        - name: rateType\n          in: query\n          type: string\n          description: Rate type\n        - name: tenor\n          in: query\n          type: string\n          description: Forward tenor\
  \ (required when rateType is Forward)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fx-rates-history\n      path: /fx/rates/history\n      operations:\n      - name: getfxratehistory\n        method: GET\n        description: Murex Get FX rate history\n        inputParameters:\n        - name: currencyPair\n          in: query\n          type: string\n          required: true\n          description: Currency pair (e.g., EURUSD)\n        - name: fromDate\n          in: query\n          type: string\n          required: true\n        - name: toDate\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reference-calendars\n      path: /reference/calendars\n      operations:\n      - name: listcalendars\n        method: GET\n        description:\
  \ Murex List market calendars\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          description: Filter by country code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reference-currencies\n      path: /reference/currencies\n      operations:\n      - name: listcurrencies\n        method: GET\n        description: Murex List currencies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: murex-rest\n    description: REST adapter for Murex MX.3 Market Data API.\n    resources:\n    - path: /quotes\n      name: getquotes\n      operations:\n      - method: GET\n        name: getquotes\n        description: Murex Get market quotes\n        call: murex.getquotes\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /quotes/history\n      name: getquotehistory\n      operations:\n      - method: GET\n        name: getquotehistory\n        description: Murex Get historical quotes\n        call: murex.getquotehistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /curves\n      name: listcurves\n      operations:\n      - method: GET\n        name: listcurves\n        description: Murex List available curves\n        call: murex.listcurves\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /curves/{curveId}\n      name: getcurve\n      operations:\n      - method: GET\n        name: getcurve\n        description: Murex Get curve data\n        call: murex.getcurve\n        with:\n          curveId: rest.curveId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /volatility/surfaces\n      name: listvolatilitysurfaces\n      operations:\n      - method: GET\n\
  \        name: listvolatilitysurfaces\n        description: Murex List volatility surfaces\n        call: murex.listvolatilitysurfaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /volatility/surfaces/{surfaceId}\n      name: getvolatilitysurface\n      operations:\n      - method: GET\n        name: getvolatilitysurface\n        description: Murex Get volatility surface data\n        call: murex.getvolatilitysurface\n        with:\n          surfaceId: rest.surfaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fx/rates\n      name: getfxrates\n      operations:\n      - method: GET\n        name: getfxrates\n        description: Murex Get FX rates\n        call: murex.getfxrates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fx/rates/history\n      name: getfxratehistory\n      operations:\n      - method: GET\n        name: getfxratehistory\n        description:\
  \ Murex Get FX rate history\n        call: murex.getfxratehistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reference/calendars\n      name: listcalendars\n      operations:\n      - method: GET\n        name: listcalendars\n        description: Murex List market calendars\n        call: murex.listcalendars\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reference/currencies\n      name: listcurrencies\n      operations:\n      - method: GET\n        name: listcurrencies\n        description: Murex List currencies\n        call: murex.listcurrencies\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: murex-mcp\n    transport: http\n    description: MCP adapter for Murex MX.3 Market Data API for AI agent use.\n    tools:\n    - name: getquotes\n      description: Murex Get market quotes\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: murex.getquotes\n      with:\n        instrumentIds: tools.instrumentIds\n        fields: tools.fields\n      inputParameters:\n      - name: instrumentIds\n        type: string\n        description: Comma-separated list of instrument identifiers\n        required: true\n      - name: fields\n        type: string\n        description: Comma-separated list of quote fields to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getquotehistory\n      description: Murex Get historical quotes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: murex.getquotehistory\n      with:\n        instrumentId: tools.instrumentId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        frequency: tools.frequency\n      inputParameters:\n      - name: instrumentId\n        type: string\n        description: Instrument identifier\n        required: true\n\
  \      - name: fromDate\n        type: string\n        description: Start date\n        required: true\n      - name: toDate\n        type: string\n        description: End date\n        required: true\n      - name: frequency\n        type: string\n        description: Data frequency\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcurves\n      description: Murex List available curves\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: murex.listcurves\n      with:\n        currency: tools.currency\n        curveType: tools.curveType\n      inputParameters:\n      - name: currency\n        type: string\n        description: Filter by currency\n      - name: curveType\n        type: string\n        description: Filter by curve type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcurve\n      description: Murex Get curve data\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: murex.getcurve\n      with:\n        curveId: tools.curveId\n        asOfDate: tools.asOfDate\n      inputParameters:\n      - name: curveId\n        type: string\n        description: Curve unique identifier\n        required: true\n      - name: asOfDate\n        type: string\n        description: Curve valuation date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvolatilitysurfaces\n      description: Murex List volatility surfaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: murex.listvolatilitysurfaces\n      with:\n        underlying: tools.underlying\n        assetClass: tools.assetClass\n      inputParameters:\n      - name: underlying\n        type: string\n        description: Filter by underlying instrument or index\n      - name: assetClass\n        type: string\n        description: Filter by asset class\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvolatilitysurface\n      description: Murex Get volatility surface data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: murex.getvolatilitysurface\n      with:\n        surfaceId: tools.surfaceId\n        asOfDate: tools.asOfDate\n      inputParameters:\n      - name: surfaceId\n        type: string\n        description: Volatility surface identifier\n        required: true\n      - name: asOfDate\n        type: string\n        description: Surface valuation date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfxrates\n      description: Murex Get FX rates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: murex.getfxrates\n      with:\n        currencyPairs: tools.currencyPairs\n        rateType: tools.rateType\n        tenor: tools.tenor\n      inputParameters:\n\
  \      - name: currencyPairs\n        type: string\n        description: Comma-separated currency pairs (e.g., EURUSD,GBPUSD)\n        required: true\n      - name: rateType\n        type: string\n        description: Rate type\n      - name: tenor\n        type: string\n        description: Forward tenor (required when rateType is Forward)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfxratehistory\n      description: Murex Get FX rate history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: murex.getfxratehistory\n      with:\n        currencyPair: tools.currencyPair\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      inputParameters:\n      - name: currencyPair\n        type: string\n        description: Currency pair (e.g., EURUSD)\n        required: true\n      - name: fromDate\n        type: string\n        description: fromDate\n        required: true\n      - name: toDate\n\
  \        type: string\n        description: toDate\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcalendars\n      description: Murex List market calendars\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: murex.listcalendars\n      with:\n        country: tools.country\n      inputParameters:\n      - name: country\n        type: string\n        description: Filter by country code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcurrencies\n      description: Murex List currencies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: murex.listcurrencies\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MUREX_TOKEN: MUREX_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/murex/refs/heads/main/capabilities/murex-capability.yaml
tags:
- Murex
- API
tools:
- description: Murex Get market quotes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquotes
- description: Murex Get historical quotes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquotehistory
- description: Murex List available curves
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcurves
- description: Murex Get curve data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurve
- description: Murex List volatility surfaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvolatilitysurfaces
- description: Murex Get volatility surface data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvolatilitysurface
- description: Murex Get FX rates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfxrates
- description: Murex Get FX rate history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfxratehistory
- description: Murex List market calendars
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcalendars
- description: Murex List currencies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcurrencies
---

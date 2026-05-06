---
categories: []
consumed_apis: []
description: Access end-of-day historical OHLCV data for stocks, ETFs, funds, indices, and currencies across global exchanges. Returns daily, weekly, or monthly historical price and volume data with both raw and split/dividend-adjusted closing prices.
layout: capability
name: EODHD End-Of-Day Historical Data API
operations:
- description: Retrieve end-of-day historical data
  method: GET
  name: geteodhistoricaldata
  path: /eod/{symbol}
personas: []
provider_name: EODHD
provider_slug: eodhd
search_terms:
- retrieve end-of-day historical data
- financial
- stocks
- api
- stock options
- market data
- geteodhistoricaldata
- eodhd
slug: eodhd-capability
source_filename: eodhd-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: EODHD End-Of-Day Historical Data API\n  description: Access end-of-day historical OHLCV data for stocks, ETFs, funds, indices, and currencies across global exchanges.\n    Returns daily, weekly, or monthly historical price and volume data with both raw and split/dividend-adjusted closing prices.\n  tags:\n  - Eodhd\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: eodhd\n    baseUri: https://eodhd.com/api\n    description: EODHD End-Of-Day Historical Data API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: api_token\n      value: '{{EODHD_TOKEN}}'\n    resources:\n    - name: eod-symbol\n      path: /eod/{symbol}\n      operations:\n      - name: geteodhistoricaldata\n        method: GET\n        description: Retrieve end-of-day historical data\n        inputParameters:\n        - name: symbol\n          in: path\n          type: string\n\
  \          required: true\n          description: Ticker symbol with exchange suffix, e.g. AAPL.US.\n        - name: api_token\n          in: query\n          type: string\n          required: true\n          description: API token assigned to your EODHD account.\n        - name: fmt\n          in: query\n          type: string\n          description: Response format. Defaults to csv.\n        - name: period\n          in: query\n          type: string\n          description: Aggregation period. d=daily, w=weekly, m=monthly.\n        - name: order\n          in: query\n          type: string\n          description: Sort order of returned rows. a=ascending, d=descending.\n        - name: from\n          in: query\n          type: string\n          description: Inclusive start date in YYYY-MM-DD format.\n        - name: to\n          in: query\n          type: string\n          description: Inclusive end date in YYYY-MM-DD format.\n        - name: filter\n          in: query\n          type:\
  \ string\n          description: Return only a single field, e.g. last_close or last_volume.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: eodhd-rest\n    description: REST adapter for EODHD End-Of-Day Historical Data API.\n    resources:\n    - path: /eod/{symbol}\n      name: geteodhistoricaldata\n      operations:\n      - method: GET\n        name: geteodhistoricaldata\n        description: Retrieve end-of-day historical data\n        call: eodhd.geteodhistoricaldata\n        with:\n          symbol: rest.symbol\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: eodhd-mcp\n    transport: http\n    description: MCP adapter for EODHD End-Of-Day Historical Data API for AI agent use.\n    tools:\n    - name: geteodhistoricaldata\n      description: Retrieve end-of-day historical\
  \ data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eodhd.geteodhistoricaldata\n      with:\n        symbol: tools.symbol\n        api_token: tools.api_token\n        fmt: tools.fmt\n        period: tools.period\n        order: tools.order\n        from: tools.from\n        to: tools.to\n        filter: tools.filter\n      inputParameters:\n      - name: symbol\n        type: string\n        description: Ticker symbol with exchange suffix, e.g. AAPL.US.\n        required: true\n      - name: api_token\n        type: string\n        description: API token assigned to your EODHD account.\n        required: true\n      - name: fmt\n        type: string\n        description: Response format. Defaults to csv.\n      - name: period\n        type: string\n        description: Aggregation period. d=daily, w=weekly, m=monthly.\n      - name: order\n        type: string\n        description: Sort order of returned rows. a=ascending, d=descending.\n\
  \      - name: from\n        type: string\n        description: Inclusive start date in YYYY-MM-DD format.\n      - name: to\n        type: string\n        description: Inclusive end date in YYYY-MM-DD format.\n      - name: filter\n        type: string\n        description: Return only a single field, e.g. last_close or last_volume.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    EODHD_TOKEN: EODHD_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/eodhd/refs/heads/main/capabilities/eodhd-capability.yaml
tags:
- Eodhd
- API
tools:
- description: Retrieve end-of-day historical data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteodhistoricaldata
---

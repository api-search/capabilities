---
categories: []
consumed_apis: []
description: Financial Modeling Prep (FMP) provides financial market data including real-time and historical stock quotes, company fundamentals, financial statements (income, balance sheet, cash flow), insider transactions, earnings, ratios, and economic data. This OpenAPI spec covers a representative subset of the public REST API.
layout: capability
name: Financial Modeling Prep API
operations:
- description: Get real-time stock quote
  method: GET
  name: getquote
  path: /quote/{symbol}
- description: Get historical end-of-day prices
  method: GET
  name: gethistoricalprice
  path: /historical-price-full/{symbol}
- description: Get company income statement
  method: GET
  name: getincomestatement
  path: /income-statement/{symbol}
- description: Get company balance sheet
  method: GET
  name: getbalancesheet
  path: /balance-sheet-statement/{symbol}
- description: Get company cash flow statement
  method: GET
  name: getcashflowstatement
  path: /cash-flow-statement/{symbol}
- description: Get company profile
  method: GET
  name: getcompanyprofile
  path: /profile/{symbol}
- description: Search for ticker symbols
  method: GET
  name: searchsymbols
  path: /search
- description: List all available stock symbols
  method: GET
  name: liststocks
  path: /stock/list
- description: Get insider transactions
  method: GET
  name: getinsidertrading
  path: /insider-trading
- description: Get company financial ratios
  method: GET
  name: getfinancialratios
  path: /ratios/{symbol}
personas: []
provider_name: Financial Modeling Prep
provider_slug: financial-modeling-prep
search_terms:
- get company income statement
- liststocks
- get company profile
- market data
- prep
- get historical end-of-day prices
- get real-time stock quote
- getcompanyprofile
- search for ticker symbols
- getbalancesheet
- financial statements
- getinsidertrading
- getquote
- searchsymbols
- historical
- modeling
- financial data
- fundamentals
- api
- get company balance sheet
- financial
- list all available stock symbols
- getcashflowstatement
- gethistoricalprice
- get company financial ratios
- get insider transactions
- stocks
- getincomestatement
- getfinancialratios
- get company cash flow statement
- quotes
slug: financial-modeling-prep-capability
source_filename: financial-modeling-prep-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Financial Modeling Prep API\n  description: Financial Modeling Prep (FMP) provides financial market data including real-time and historical stock quotes,\n    company fundamentals, financial statements (income, balance sheet, cash flow), insider transactions, earnings, ratios,\n    and economic data. This OpenAPI spec covers a representative subset of the public REST API.\n  tags:\n  - Financial\n  - Modeling\n  - Prep\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: financial-modeling-prep\n    baseUri: https://financialmodelingprep.com/api/v3\n    description: Financial Modeling Prep API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: apikey\n      value: '{{FINANCIAL_MODELING_PREP_TOKEN}}'\n    resources:\n    - name: quote-symbol\n      path: /quote/{symbol}\n      operations:\n      - name: getquote\n        method: GET\n        description:\
  \ Get real-time stock quote\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historical-price-full-symbol\n      path: /historical-price-full/{symbol}\n      operations:\n      - name: gethistoricalprice\n        method: GET\n        description: Get historical end-of-day prices\n        inputParameters:\n        - name: from\n          in: query\n          type: string\n        - name: to\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: income-statement-symbol\n      path: /income-statement/{symbol}\n      operations:\n      - name: getincomestatement\n        method: GET\n        description: Get company income statement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: balance-sheet-statement-symbol\n\
  \      path: /balance-sheet-statement/{symbol}\n      operations:\n      - name: getbalancesheet\n        method: GET\n        description: Get company balance sheet\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cash-flow-statement-symbol\n      path: /cash-flow-statement/{symbol}\n      operations:\n      - name: getcashflowstatement\n        method: GET\n        description: Get company cash flow statement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profile-symbol\n      path: /profile/{symbol}\n      operations:\n      - name: getcompanyprofile\n        method: GET\n        description: Get company profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      operations:\n    \
  \  - name: searchsymbols\n        method: GET\n        description: Search for ticker symbols\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: exchange\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stock-list\n      path: /stock/list\n      operations:\n      - name: liststocks\n        method: GET\n        description: List all available stock symbols\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insider-trading\n      path: /insider-trading\n      operations:\n      - name: getinsidertrading\n        method: GET\n        description: Get insider transactions\n        inputParameters:\n        - name:\
  \ symbol\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ratios-symbol\n      path: /ratios/{symbol}\n      operations:\n      - name: getfinancialratios\n        method: GET\n        description: Get company financial ratios\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: financial-modeling-prep-rest\n    description: REST adapter for Financial Modeling Prep API.\n    resources:\n    - path: /quote/{symbol}\n      name: getquote\n      operations:\n      - method: GET\n        name: getquote\n        description: Get real-time stock quote\n        call: financial-modeling-prep.getquote\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /historical-price-full/{symbol}\n      name:\
  \ gethistoricalprice\n      operations:\n      - method: GET\n        name: gethistoricalprice\n        description: Get historical end-of-day prices\n        call: financial-modeling-prep.gethistoricalprice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /income-statement/{symbol}\n      name: getincomestatement\n      operations:\n      - method: GET\n        name: getincomestatement\n        description: Get company income statement\n        call: financial-modeling-prep.getincomestatement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /balance-sheet-statement/{symbol}\n      name: getbalancesheet\n      operations:\n      - method: GET\n        name: getbalancesheet\n        description: Get company balance sheet\n        call: financial-modeling-prep.getbalancesheet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cash-flow-statement/{symbol}\n      name: getcashflowstatement\n\
  \      operations:\n      - method: GET\n        name: getcashflowstatement\n        description: Get company cash flow statement\n        call: financial-modeling-prep.getcashflowstatement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /profile/{symbol}\n      name: getcompanyprofile\n      operations:\n      - method: GET\n        name: getcompanyprofile\n        description: Get company profile\n        call: financial-modeling-prep.getcompanyprofile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search\n      name: searchsymbols\n      operations:\n      - method: GET\n        name: searchsymbols\n        description: Search for ticker symbols\n        call: financial-modeling-prep.searchsymbols\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stock/list\n      name: liststocks\n      operations:\n      - method: GET\n        name: liststocks\n        description:\
  \ List all available stock symbols\n        call: financial-modeling-prep.liststocks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /insider-trading\n      name: getinsidertrading\n      operations:\n      - method: GET\n        name: getinsidertrading\n        description: Get insider transactions\n        call: financial-modeling-prep.getinsidertrading\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ratios/{symbol}\n      name: getfinancialratios\n      operations:\n      - method: GET\n        name: getfinancialratios\n        description: Get company financial ratios\n        call: financial-modeling-prep.getfinancialratios\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: financial-modeling-prep-mcp\n    transport: http\n    description: MCP adapter for Financial Modeling Prep API for AI agent use.\n    tools:\n    - name: getquote\n\
  \      description: Get real-time stock quote\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: financial-modeling-prep.getquote\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethistoricalprice\n      description: Get historical end-of-day prices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: financial-modeling-prep.gethistoricalprice\n      with:\n        from: tools.from\n        to: tools.to\n      inputParameters:\n      - name: from\n        type: string\n        description: from\n      - name: to\n        type: string\n        description: to\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getincomestatement\n      description: Get company income statement\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: financial-modeling-prep.getincomestatement\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbalancesheet\n      description: Get company balance sheet\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: financial-modeling-prep.getbalancesheet\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcashflowstatement\n      description: Get company cash flow statement\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: financial-modeling-prep.getcashflowstatement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcompanyprofile\n      description: Get company profile\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: financial-modeling-prep.getcompanyprofile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchsymbols\n      description: Search\
  \ for ticker symbols\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: financial-modeling-prep.searchsymbols\n      with:\n        query: tools.query\n        limit: tools.limit\n        exchange: tools.exchange\n      inputParameters:\n      - name: query\n        type: string\n        description: query\n        required: true\n      - name: limit\n        type: integer\n        description: limit\n      - name: exchange\n        type: string\n        description: exchange\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststocks\n      description: List all available stock symbols\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: financial-modeling-prep.liststocks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinsidertrading\n      description: Get insider transactions\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: financial-modeling-prep.getinsidertrading\n      with:\n        symbol: tools.symbol\n      inputParameters:\n      - name: symbol\n        type: string\n        description: symbol\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfinancialratios\n      description: Get company financial ratios\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: financial-modeling-prep.getfinancialratios\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FINANCIAL_MODELING_PREP_TOKEN: FINANCIAL_MODELING_PREP_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/financial-modeling-prep/refs/heads/main/capabilities/financial-modeling-prep-capability.yaml
tags:
- Financial
- Modeling
- Prep
- API
tools:
- description: Get real-time stock quote
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquote
- description: Get historical end-of-day prices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethistoricalprice
- description: Get company income statement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getincomestatement
- description: Get company balance sheet
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbalancesheet
- description: Get company cash flow statement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcashflowstatement
- description: Get company profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompanyprofile
- description: Search for ticker symbols
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchsymbols
- description: List all available stock symbols
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststocks
- description: Get insider transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinsidertrading
- description: Get company financial ratios
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfinancialratios
---

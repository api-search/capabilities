---
api_specs:
- filename: stockdata-openapi.yml
  format: yaml
  label: stockdata
  slug: stockdata
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/stockdata/refs/heads/main/openapi/stockdata-openapi.yml
categories: []
consumed_apis:
- stockdata
description: Unified market data and financial intelligence workflow combining real-time stock quotes, historical price data, corporate actions, and AI-enriched news sentiment analysis. Designed for quantitative analysts, algorithmic traders, and financial application developers who need comprehensive market data with sentiment context in a single integration.
layout: capability
name: StockData Market Data and Intelligence
operations:
- description: Get real-time prices for one or more US-listed stocks.
  method: GET
  name: get-stock-quote
  path: /v1/quotes
- description: Get split-adjusted intraday data with minute or hour resolution.
  method: GET
  name: get-intraday-adjusted
  path: /v1/intraday
- description: Get historical end-of-day OHLCV data at daily to yearly intervals.
  method: GET
  name: get-end-of-day-data
  path: /v1/eod
- description: Retrieve historical stock split records.
  method: GET
  name: get-stock-splits
  path: /v1/splits
- description: Retrieve historical dividend payment records.
  method: GET
  name: get-stock-dividends
  path: /v1/dividends
- description: Get financial news with entity-level sentiment scoring.
  method: GET
  name: get-financial-news
  path: /v1/news
- description: Identify trending entities by news volume and sentiment.
  method: GET
  name: get-trending-entities
  path: /v1/news/trending
- description: Search for financial entities by name, symbol, type, or industry.
  method: GET
  name: search-entities
  path: /v1/entities
personas: []
provider_name: StockData
provider_slug: stockdata
search_terms:
- news
- get split-adjusted historical intraday ohlcv data at minute or hour intervals. use for chart data, technical analysis, or volatility studies.
- market data
- get global financial news with entity-level sentiment scoring. use to gauge market sentiment, find relevant news for a stock, or analyze news impact on securities.
- search for financial entities by name, symbol, type, or industry.
- real-time stock prices for us-listed equities.
- retrieve historical dividend payment records.
- get intraday data
- finance
- identify the most-talked-about financial entities in recent news. use for market awareness, discovering momentum stocks, or monitoring news flow across sectors.
- financial data
- get intraday adjusted
- search entities
- financial entity search.
- get financial news
- search for financial entities (stocks, etfs, indices, crypto, currencies) by name, symbol, industry, or country.
- retrieve historical stock split records.
- get historical end-of-day ohlcv data at daily to yearly intervals.
- stock market
- historical stock split events.
- historical dividend payments.
- get trending entities
- get dividends
- get historical eod data
- get stock splits
- historical end-of-day stock data.
- trending financial entities by news volume.
- get split-adjusted intraday data with minute or hour resolution.
- identify trending entities by news volume and sentiment.
- get stock dividends
- get historical end-of-day ohlcv data for long-term trend analysis, backtesting, and performance attribution.
- get stock quote
- algorithmic trading
- get real-time prices for one or more us-listed stocks.
- get financial news with entity-level sentiment scoring.
- sentiment analysis
- get real-time stock prices for us-listed equities. use when a user asks about current stock prices, market cap, or trading volume.
- get historical dividend records. use for calculating total return, dividend yield analysis, or income-focused portfolio research.
- global financial news with sentiment analysis.
- retrieve historical stock split information. use for adjusting historical price series or understanding share dilution events.
- historical intraday ohlcv data.
- get end of day data
slug: market-data-intelligence
source_filename: market-data-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: StockData Market Data and Intelligence\n  description: >-\n    Unified market data and financial intelligence workflow combining real-time\n    stock quotes, historical price data, corporate actions, and AI-enriched news\n    sentiment analysis. Designed for quantitative analysts, algorithmic traders,\n    and financial application developers who need comprehensive market data with\n    sentiment context in a single integration.\n  tags:\n    - Finance\n    - Financial Data\n    - Stock Market\n    - Market Data\n    - News\n    - Sentiment Analysis\n    - Algorithmic Trading\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STOCKDATA_API_TOKEN: STOCKDATA_API_TOKEN\n\ncapability:\n  consumes:\n    - import: stockdata\n      location: ./shared/stockdata.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: market-intelligence-api\n      description: >-\n     \
  \   Unified REST API for comprehensive market data and news intelligence.\n      resources:\n        - path: /v1/quotes\n          name: quotes\n          description: Real-time stock prices for US-listed equities.\n          operations:\n            - method: GET\n              name: get-stock-quote\n              description: Get real-time prices for one or more US-listed stocks.\n              call: \"stockdata.get-stock-quote\"\n              with:\n                symbols: \"rest.symbols\"\n                extended_hours: \"rest.extended_hours\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/intraday\n          name: intraday-data\n          description: Historical intraday OHLCV data.\n          operations:\n            - method: GET\n              name: get-intraday-adjusted\n              description: Get split-adjusted intraday data with minute or hour resolution.\n              call: \"stockdata.get-intraday-adjusted\"\
  \n              with:\n                symbols: \"rest.symbols\"\n                interval: \"rest.interval\"\n                date_from: \"rest.date_from\"\n                date_to: \"rest.date_to\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/eod\n          name: eod-data\n          description: Historical end-of-day stock data.\n          operations:\n            - method: GET\n              name: get-end-of-day-data\n              description: Get historical end-of-day OHLCV data at daily to yearly intervals.\n              call: \"stockdata.get-end-of-day-data\"\n              with:\n                symbols: \"rest.symbols\"\n                interval: \"rest.interval\"\n                date_from: \"rest.date_from\"\n                date_to: \"rest.date_to\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/splits\n          name: splits\n\
  \          description: Historical stock split events.\n          operations:\n            - method: GET\n              name: get-stock-splits\n              description: Retrieve historical stock split records.\n              call: \"stockdata.get-stock-splits\"\n              with:\n                symbols: \"rest.symbols\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/dividends\n          name: dividends\n          description: Historical dividend payments.\n          operations:\n            - method: GET\n              name: get-stock-dividends\n              description: Retrieve historical dividend payment records.\n              call: \"stockdata.get-stock-dividends\"\n              with:\n                symbols: \"rest.symbols\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/news\n          name: news\n          description:\
  \ Global financial news with sentiment analysis.\n          operations:\n            - method: GET\n              name: get-financial-news\n              description: Get financial news with entity-level sentiment scoring.\n              call: \"stockdata.get-financial-news\"\n              with:\n                symbols: \"rest.symbols\"\n                search: \"rest.search\"\n                sentiment_gte: \"rest.sentiment_gte\"\n                language: \"rest.language\"\n                page: \"rest.page\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/news/trending\n          name: trending-entities\n          description: Trending financial entities by news volume.\n          operations:\n            - method: GET\n              name: get-trending-entities\n              description: Identify trending entities by news volume and sentiment.\n              call: \"\
  stockdata.get-trending-entities\"\n              with:\n                group_by: \"rest.group_by\"\n                sentiment_gte: \"rest.sentiment_gte\"\n                min_doc_count: \"rest.min_doc_count\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/entities\n          name: entities\n          description: Financial entity search.\n          operations:\n            - method: GET\n              name: search-entities\n              description: Search for financial entities by name, symbol, type, or industry.\n              call: \"stockdata.search-entities\"\n              with:\n                search: \"rest.search\"\n                types: \"rest.types\"\n                industries: \"rest.industries\"\n                countries: \"rest.countries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace:\
  \ market-intelligence-mcp\n      transport: http\n      description: >-\n        MCP server for AI-assisted market data analysis, news sentiment\n        interpretation, and financial research workflows.\n      tools:\n        - name: get-stock-quote\n          description: >-\n            Get real-time stock prices for US-listed equities. Use when a user\n            asks about current stock prices, market cap, or trading volume.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stockdata.get-stock-quote\"\n          with:\n            symbols: \"tools.symbols\"\n            extended_hours: \"tools.extended_hours\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-intraday-data\n          description: >-\n            Get split-adjusted historical intraday OHLCV data at minute or hour\n            intervals. Use for chart data, technical analysis, or volatility studies.\n         \
  \ hints:\n            readOnly: true\n            idempotent: true\n          call: \"stockdata.get-intraday-adjusted\"\n          with:\n            symbols: \"tools.symbols\"\n            interval: \"tools.interval\"\n            date_from: \"tools.date_from\"\n            date_to: \"tools.date_to\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-historical-eod-data\n          description: >-\n            Get historical end-of-day OHLCV data for long-term trend analysis,\n            backtesting, and performance attribution.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stockdata.get-end-of-day-data\"\n          with:\n            symbols: \"tools.symbols\"\n            interval: \"tools.interval\"\n            date_from: \"tools.date_from\"\n            date_to: \"tools.date_to\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n  \
  \      - name: get-stock-splits\n          description: >-\n            Retrieve historical stock split information. Use for adjusting\n            historical price series or understanding share dilution events.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stockdata.get-stock-splits\"\n          with:\n            symbols: \"tools.symbols\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-dividends\n          description: >-\n            Get historical dividend records. Use for calculating total return,\n            dividend yield analysis, or income-focused portfolio research.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stockdata.get-stock-dividends\"\n          with:\n            symbols: \"tools.symbols\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-financial-news\n\
  \          description: >-\n            Get global financial news with entity-level sentiment scoring.\n            Use to gauge market sentiment, find relevant news for a stock,\n            or analyze news impact on securities.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stockdata.get-financial-news\"\n          with:\n            symbols: \"tools.symbols\"\n            search: \"tools.search\"\n            sentiment_gte: \"tools.sentiment_gte\"\n            language: \"tools.language\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-trending-entities\n          description: >-\n            Identify the most-talked-about financial entities in recent news.\n            Use for market awareness, discovering momentum stocks, or\n            monitoring news flow across sectors.\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"stockdata.get-trending-entities\"\n          with:\n            group_by: \"tools.group_by\"\n            sentiment_gte: \"tools.sentiment_gte\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-entities\n          description: >-\n            Search for financial entities (stocks, ETFs, indices, crypto,\n            currencies) by name, symbol, industry, or country.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stockdata.search-entities\"\n          with:\n            search: \"tools.search\"\n            types: \"tools.types\"\n            industries: \"tools.industries\"\n            countries: \"tools.countries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stockdata/refs/heads/main/capabilities/market-data-intelligence.yaml
tags:
- Finance
- Financial Data
- Stock Market
- Market Data
- News
- Sentiment Analysis
- Algorithmic Trading
tools:
- description: Get real-time stock prices for US-listed equities. Use when a user asks about current stock prices, market cap, or trading volume.
  hints:
    idempotent: true
    readOnly: true
  name: get-stock-quote
- description: Get split-adjusted historical intraday OHLCV data at minute or hour intervals. Use for chart data, technical analysis, or volatility studies.
  hints:
    idempotent: true
    readOnly: true
  name: get-intraday-data
- description: Get historical end-of-day OHLCV data for long-term trend analysis, backtesting, and performance attribution.
  hints:
    idempotent: true
    readOnly: true
  name: get-historical-eod-data
- description: Retrieve historical stock split information. Use for adjusting historical price series or understanding share dilution events.
  hints:
    idempotent: true
    readOnly: true
  name: get-stock-splits
- description: Get historical dividend records. Use for calculating total return, dividend yield analysis, or income-focused portfolio research.
  hints:
    idempotent: true
    readOnly: true
  name: get-dividends
- description: Get global financial news with entity-level sentiment scoring. Use to gauge market sentiment, find relevant news for a stock, or analyze news impact on securities.
  hints:
    idempotent: true
    readOnly: true
  name: get-financial-news
- description: Identify the most-talked-about financial entities in recent news. Use for market awareness, discovering momentum stocks, or monitoring news flow across sectors.
  hints:
    idempotent: true
    readOnly: true
  name: get-trending-entities
- description: Search for financial entities (stocks, ETFs, indices, crypto, currencies) by name, symbol, industry, or country.
  hints:
    idempotent: true
    readOnly: true
  name: search-entities
---

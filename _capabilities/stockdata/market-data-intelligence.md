---
categories: []
consumed_apis: []
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
- identify the most-talked-about financial entities in recent news. use for market awareness, discovering momentum stocks, or monitoring news flow across sectors.
- get split-adjusted historical intraday ohlcv data at minute or hour intervals. use for chart data, technical analysis, or volatility studies.
- get historical end-of-day ohlcv data at daily to yearly intervals.
- historical end-of-day stock data.
- get global financial news with entity-level sentiment scoring. use to gauge market sentiment, find relevant news for a stock, or analyze news impact on securities.
- historical stock split events.
- historical dividend payments.
- get intraday adjusted
- global financial news with sentiment analysis.
- algorithmic trading
- sentiment analysis
- identify trending entities by news volume and sentiment.
- get stock quote
- financial entity search.
- get financial news
- stock market
- get stock splits
- get real-time stock prices for us-listed equities. use when a user asks about current stock prices, market cap, or trading volume.
- get dividends
- financial data
- finance
- retrieve historical dividend payment records.
- get financial news with entity-level sentiment scoring.
- get stock dividends
- get split-adjusted intraday data with minute or hour resolution.
- retrieve historical stock split records.
- retrieve historical stock split information. use for adjusting historical price series or understanding share dilution events.
- real-time stock prices for us-listed equities.
- get real-time prices for one or more us-listed stocks.
- search for financial entities (stocks, etfs, indices, crypto, currencies) by name, symbol, industry, or country.
- get end of day data
- trending financial entities by news volume.
- search for financial entities by name, symbol, type, or industry.
- market data
- get intraday data
- get historical end-of-day ohlcv data for long-term trend analysis, backtesting, and performance attribution.
- get trending entities
- get historical dividend records. use for calculating total return, dividend yield analysis, or income-focused portfolio research.
- historical intraday ohlcv data.
- get historical eod data
- news
- search entities
slug: market-data-intelligence
source_filename: market-data-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: StockData Market Data and Intelligence\n  description: Unified market data and financial intelligence workflow combining real-time stock quotes, historical price\n    data, corporate actions, and AI-enriched news sentiment analysis. Designed for quantitative analysts, algorithmic traders,\n    and financial application developers who need comprehensive market data with sentiment context in a single integration.\n  tags:\n  - Finance\n  - Financial Data\n  - Stock Market\n  - Market Data\n  - News\n  - Sentiment Analysis\n  - Algorithmic Trading\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STOCKDATA_API_TOKEN: STOCKDATA_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: stockdata\n    baseUri: https://api.stockdata.org/v1\n    description: StockData REST API for market data and financial news.\n    authentication:\n      type: apikey\n      key: api_token\n      value: '{{STOCKDATA_API_TOKEN}}'\n\
  \      placement: query\n    resources:\n    - name: stock-quotes\n      path: /data/quote\n      description: Real-time US stock quotes.\n      operations:\n      - name: get-stock-quote\n        method: GET\n        description: Get real-time prices for US-listed stocks.\n        inputParameters:\n        - name: symbols\n          in: query\n          type: string\n          required: true\n          description: Comma-separated ticker symbols.\n        - name: extended_hours\n          in: query\n          type: boolean\n          required: false\n          description: Include extended hours data.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: intraday-adjusted\n      path: /data/intraday/adjusted\n      description: Historical intraday data adjusted for splits.\n      operations:\n      - name: get-intraday-adjusted\n        method: GET\n        description: Get split-adjusted historical\
  \ intraday OHLCV data.\n        inputParameters:\n        - name: symbols\n          in: query\n          type: string\n          required: true\n          description: Comma-separated ticker symbols.\n        - name: interval\n          in: query\n          type: string\n          required: false\n          description: Data interval (minute or hour).\n        - name: date_from\n          in: query\n          type: string\n          required: false\n          description: Start date/time (ISO 8601).\n        - name: date_to\n          in: query\n          type: string\n          required: false\n          description: End date/time (ISO 8601).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: intraday-raw\n      path: /data/intraday\n      description: Historical intraday data without split adjustments.\n      operations:\n      - name: get-intraday-raw\n        method: GET\n        description:\
  \ Get unadjusted historical intraday OHLCV data.\n        inputParameters:\n        - name: symbols\n          in: query\n          type: string\n          required: true\n          description: Comma-separated ticker symbols.\n        - name: interval\n          in: query\n          type: string\n          required: false\n          description: Data interval (minute or hour).\n        - name: date_from\n          in: query\n          type: string\n          required: false\n          description: Start date/time (ISO 8601).\n        - name: date_to\n          in: query\n          type: string\n          required: false\n          description: End date/time (ISO 8601).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: eod-data\n      path: /data/eod\n      description: Historical end-of-day stock data.\n      operations:\n      - name: get-end-of-day-data\n        method: GET\n        description:\
  \ Get historical end-of-day OHLCV data adjusted for splits.\n        inputParameters:\n        - name: symbols\n          in: query\n          type: string\n          required: true\n          description: Comma-separated ticker symbols.\n        - name: interval\n          in: query\n          type: string\n          required: false\n          description: Data interval (day, week, month, quarter, year).\n        - name: date_from\n          in: query\n          type: string\n          required: false\n          description: Start date.\n        - name: date_to\n          in: query\n          type: string\n          required: false\n          description: End date.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: splits\n      path: /data/splits\n      description: Historical stock split data.\n      operations:\n      - name: get-stock-splits\n        method: GET\n        description: Retrieve\
  \ historical stock split information.\n        inputParameters:\n        - name: symbols\n          in: query\n          type: string\n          required: true\n          description: Comma-separated ticker symbols.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dividends\n      path: /data/dividends\n      description: Historical dividend records.\n      operations:\n      - name: get-stock-dividends\n        method: GET\n        description: Access dividend payment records for US-listed stocks.\n        inputParameters:\n        - name: symbols\n          in: query\n          type: string\n          required: true\n          description: Comma-separated ticker symbols.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: news\n      path: /news/all\n      description: Global financial news with sentiment analysis.\n\
  \      operations:\n      - name: get-financial-news\n        method: GET\n        description: Get global financial news filtered by entities with sentiment analysis.\n        inputParameters:\n        - name: symbols\n          in: query\n          type: string\n          required: false\n          description: Filter by ticker symbols.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Full-text search query.\n        - name: sentiment_gte\n          in: query\n          type: number\n          required: false\n          description: Minimum sentiment score.\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Language code filter.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: limit\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: news-trending\n      path: /news/stats/trending\n      description: Trending financial entities based on news.\n      operations:\n      - name: get-trending-entities\n        method: GET\n        description: Identify trending entities based on news volume and sentiment.\n        inputParameters:\n        - name: group_by\n          in: query\n          type: string\n          required: false\n          description: Field to group results by.\n        - name: sentiment_gte\n          in: query\n          type: number\n          required: false\n          description: Minimum sentiment score.\n        - name: min_doc_count\n          in: query\n          type: integer\n          required: false\n          description: Minimum article count.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: entity-search\n      path: /entity/search\n      description: Financial entity search.\n      operations:\n      - name: search-entities\n        method: GET\n        description: Search for financial entities by name, symbol, type, or industry.\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search query.\n        - name: symbols\n          in: query\n          type: string\n          required: false\n          description: Filter by ticker symbols.\n        - name: types\n          in: query\n          type: string\n          required: false\n          description: Filter by entity type.\n        - name: industries\n          in: query\n          type: string\n          required: false\n          description: Filter by industry.\n        - name: countries\n          in: query\n          type: string\n     \
  \     required: false\n          description: Filter by country code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: market-intelligence-api\n    description: Unified REST API for comprehensive market data and news intelligence.\n    resources:\n    - path: /v1/quotes\n      name: quotes\n      description: Real-time stock prices for US-listed equities.\n      operations:\n      - method: GET\n        name: get-stock-quote\n        description: Get real-time prices for one or more US-listed stocks.\n        call: stockdata.get-stock-quote\n        with:\n          symbols: rest.symbols\n          extended_hours: rest.extended_hours\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/intraday\n      name: intraday-data\n      description: Historical intraday OHLCV data.\n      operations:\n      - method: GET\n\
  \        name: get-intraday-adjusted\n        description: Get split-adjusted intraday data with minute or hour resolution.\n        call: stockdata.get-intraday-adjusted\n        with:\n          symbols: rest.symbols\n          interval: rest.interval\n          date_from: rest.date_from\n          date_to: rest.date_to\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/eod\n      name: eod-data\n      description: Historical end-of-day stock data.\n      operations:\n      - method: GET\n        name: get-end-of-day-data\n        description: Get historical end-of-day OHLCV data at daily to yearly intervals.\n        call: stockdata.get-end-of-day-data\n        with:\n          symbols: rest.symbols\n          interval: rest.interval\n          date_from: rest.date_from\n          date_to: rest.date_to\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/splits\n      name: splits\n      description: Historical\
  \ stock split events.\n      operations:\n      - method: GET\n        name: get-stock-splits\n        description: Retrieve historical stock split records.\n        call: stockdata.get-stock-splits\n        with:\n          symbols: rest.symbols\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dividends\n      name: dividends\n      description: Historical dividend payments.\n      operations:\n      - method: GET\n        name: get-stock-dividends\n        description: Retrieve historical dividend payment records.\n        call: stockdata.get-stock-dividends\n        with:\n          symbols: rest.symbols\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/news\n      name: news\n      description: Global financial news with sentiment analysis.\n      operations:\n      - method: GET\n        name: get-financial-news\n        description: Get financial news with entity-level sentiment scoring.\n        call:\
  \ stockdata.get-financial-news\n        with:\n          symbols: rest.symbols\n          search: rest.search\n          sentiment_gte: rest.sentiment_gte\n          language: rest.language\n          page: rest.page\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/news/trending\n      name: trending-entities\n      description: Trending financial entities by news volume.\n      operations:\n      - method: GET\n        name: get-trending-entities\n        description: Identify trending entities by news volume and sentiment.\n        call: stockdata.get-trending-entities\n        with:\n          group_by: rest.group_by\n          sentiment_gte: rest.sentiment_gte\n          min_doc_count: rest.min_doc_count\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities\n      name: entities\n      description: Financial entity search.\n      operations:\n      - method: GET\n  \
  \      name: search-entities\n        description: Search for financial entities by name, symbol, type, or industry.\n        call: stockdata.search-entities\n        with:\n          search: rest.search\n          types: rest.types\n          industries: rest.industries\n          countries: rest.countries\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: market-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted market data analysis, news sentiment interpretation, and financial research workflows.\n    tools:\n    - name: get-stock-quote\n      description: Get real-time stock prices for US-listed equities. Use when a user asks about current stock prices, market\n        cap, or trading volume.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stockdata.get-stock-quote\n      with:\n        symbols: tools.symbols\n        extended_hours: tools.extended_hours\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-intraday-data\n      description: Get split-adjusted historical intraday OHLCV data at minute or hour intervals. Use for chart data, technical\n        analysis, or volatility studies.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stockdata.get-intraday-adjusted\n      with:\n        symbols: tools.symbols\n        interval: tools.interval\n        date_from: tools.date_from\n        date_to: tools.date_to\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-historical-eod-data\n      description: Get historical end-of-day OHLCV data for long-term trend analysis, backtesting, and performance attribution.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stockdata.get-end-of-day-data\n      with:\n        symbols: tools.symbols\n        interval: tools.interval\n        date_from: tools.date_from\n        date_to:\
  \ tools.date_to\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-stock-splits\n      description: Retrieve historical stock split information. Use for adjusting historical price series or understanding\n        share dilution events.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stockdata.get-stock-splits\n      with:\n        symbols: tools.symbols\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dividends\n      description: Get historical dividend records. Use for calculating total return, dividend yield analysis, or income-focused\n        portfolio research.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stockdata.get-stock-dividends\n      with:\n        symbols: tools.symbols\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-financial-news\n      description: Get global financial news with entity-level sentiment scoring.\
  \ Use to gauge market sentiment, find relevant\n        news for a stock, or analyze news impact on securities.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stockdata.get-financial-news\n      with:\n        symbols: tools.symbols\n        search: tools.search\n        sentiment_gte: tools.sentiment_gte\n        language: tools.language\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trending-entities\n      description: Identify the most-talked-about financial entities in recent news. Use for market awareness, discovering\n        momentum stocks, or monitoring news flow across sectors.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stockdata.get-trending-entities\n      with:\n        group_by: tools.group_by\n        sentiment_gte: tools.sentiment_gte\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-entities\n      description:\
  \ Search for financial entities (stocks, ETFs, indices, crypto, currencies) by name, symbol, industry, or\n        country.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stockdata.search-entities\n      with:\n        search: tools.search\n        types: tools.types\n        industries: tools.industries\n        countries: tools.countries\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

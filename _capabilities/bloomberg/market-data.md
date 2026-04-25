---
consumed_apis:
- blpapi
description: Unified workflow for accessing Bloomberg reference data, historical data, intraday analytics, and field discovery. Used by quantitative analysts and portfolio managers.
layout: capability
name: Bloomberg Market Data
operations:
- description: Request reference data.
  method: POST
  name: reference-data-request
  path: /v1/reference-data
- description: Request historical data.
  method: POST
  name: historical-data-request
  path: /v1/historical-data
- description: Request intraday bars.
  method: POST
  name: intraday-bar-request
  path: /v1/intraday-bars
- description: Request intraday ticks.
  method: POST
  name: intraday-tick-request
  path: /v1/intraday-ticks
- description: Look up field metadata.
  method: POST
  name: field-info-request
  path: /v1/fields
- description: Search for fields.
  method: POST
  name: field-search-request
  path: /v1/fields
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- search for fields.
- transaction cost analysis
- analytics
- request intraday ticks.
- request historical data.
- subscribe market vwap
- intraday tick queries.
- subscribe to streaming real-time market data.
- subscribe to custom vwap stream.
- quantitative analysis
- subscribe market data
- request raw intraday tick data for a security.
- enterprise
- news
- reference data request
- execution management
- request intraday bars.
- financial services
- intraday bar queries.
- intraday tick request
- subscribe market bar
- request end-of-day historical data for securities.
- intraday bar request
- request intraday ohlc bars for a security.
- request reference data for securities and fields.
- request reference data.
- reference data queries.
- look up metadata for bloomberg field mnemonics.
- trading
- market data
- business intelligence
- subscribe to interval-based real-time bars.
- field search request
- bloomberg
- historical data queries.
- search the bloomberg api data dictionary for fields.
- look up field metadata.
- field info request
- data license
- historical data request
- field discovery.
slug: market-data
tags:
- Bloomberg
- Market Data
- Financial Services
- Quantitative Analysis
tools:
- description: Request reference data for securities and fields.
  hints:
    openWorld: true
    readOnly: true
  name: reference-data-request
- description: Request end-of-day historical data for securities.
  hints:
    openWorld: true
    readOnly: true
  name: historical-data-request
- description: Request intraday OHLC bars for a security.
  hints:
    readOnly: true
  name: intraday-bar-request
- description: Request raw intraday tick data for a security.
  hints:
    readOnly: true
  name: intraday-tick-request
- description: Look up metadata for Bloomberg field mnemonics.
  hints:
    readOnly: true
  name: field-info-request
- description: Search the Bloomberg API Data Dictionary for fields.
  hints:
    openWorld: true
    readOnly: true
  name: field-search-request
- description: Subscribe to streaming real-time market data.
  hints:
    readOnly: true
  name: subscribe-market-data
- description: Subscribe to interval-based real-time bars.
  hints:
    readOnly: true
  name: subscribe-market-bar
- description: Subscribe to custom VWAP stream.
  hints:
    readOnly: true
  name: subscribe-market-vwap
---

---
consumed_apis:
- factset-global-prices
- factset-prices
- factset-rt-quotes
- factset-rt-news
- factset-rt-ts
- factset-rt-alert
- factset-options
- factset-fx
- factset-intraday
- factset-tick
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
- portfolio analytics
- global equity prices.
- pricing
- get fx rates.
- get quotes
- get real-time news.
- market data
- get real-time quotes.
- research
- get ticks
- get real-time time series.
- get price alerting data.
- options data.
- real-time data
- get rt quotes
- get price alerts
- real-time quotes.
- get intraday ticks
- get tick history
- get intraday tick history.
- get equity prices and returns.
- get rt news
- get global equity prices.
- get equity prices.
- get options
- get time series
- get fx rates
- investment analytics
- get historical tick data.
- historical tick data.
- financial data
- get tick history.
- financial
- factset
- foreign exchange rates.
- get prices
- get fx
- get global prices
- get options data.
- get foreign exchange rates.
slug: market-data-pricing
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

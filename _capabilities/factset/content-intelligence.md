---
categories: []
consumed_apis:
- factset-callstreet
- factset-streetaccount
- factset-filings
- factset-signals
- factset-nlp
- factset-search
- factset-conv
description: Unified workflow for content retrieval and intelligence including news, filings, earnings calls, NLP, signals, and conversational search. Used by content consumers and data scientists.
layout: capability
name: FactSet Content and Intelligence
operations:
- description: Get news articles.
  method: GET
  name: get-news
  path: /v1/news
- description: Get regulatory filings.
  method: GET
  name: get-filings
  path: /v1/filings
- description: Get signals.
  method: GET
  name: get-signals
  path: /v1/signals
- description: Search for answers.
  method: GET
  name: search
  path: /v1/search
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- get signals.
- streetaccount news.
- factset
- search for answers.
- investment analytics
- get news articles.
- global filings.
- conversational query
- material event signals.
- get streetaccount news.
- portfolio analytics
- get regulatory filings.
- signals
- financial data
- get global regulatory filings.
- conversational ai query.
- news
- natural language search.
- content
- financial
- run nlp analysis on text.
- get callstreet events
- search
- get material event signals.
- get signals
- get filings
- market data
- get earnings call transcripts.
- run nlp
- search answers
- nlp
- research
- get news
slug: content-intelligence
tags:
- FactSet
- Content
- NLP
- News
- Signals
tools:
- description: Get earnings call transcripts.
  hints:
    readOnly: true
  name: get-callstreet-events
- description: Get StreetAccount news.
  hints:
    readOnly: true
  name: get-news
- description: Get global regulatory filings.
  hints:
    readOnly: true
  name: get-filings
- description: Get material event signals.
  hints:
    readOnly: true
  name: get-signals
- description: Run NLP analysis on text.
  hints:
    readOnly: true
  name: run-nlp
- description: Natural language search.
  hints:
    readOnly: true
  name: search-answers
- description: Conversational AI query.
  hints:
    readOnly: true
  name: conversational-query
---

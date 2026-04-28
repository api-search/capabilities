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
- streetaccount news.
- get regulatory filings.
- run nlp
- get streetaccount news.
- conversational query
- content
- natural language search.
- financial
- search
- get global regulatory filings.
- get material event signals.
- factset
- get filings
- news
- get signals
- get signals.
- run nlp analysis on text.
- conversational ai query.
- nlp
- portfolio analytics
- get earnings call transcripts.
- search for answers.
- investment analytics
- market data
- get callstreet events
- get news
- get news articles.
- search answers
- material event signals.
- signals
- financial data
- global filings.
- research
slug: content-intelligence
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"FactSet Content and Intelligence\"\n  description: \"Unified workflow for content retrieval and intelligence including news, filings, earnings calls, NLP, signals, and conversational search. Used by content consumers and data scientists.\"\n  tags:\n    - FactSet\n    - Content\n    - NLP\n    - News\n    - Signals\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACTSET_USERNAME: FACTSET_USERNAME\n      FACTSET_PASSWORD: FACTSET_PASSWORD\n\ncapability:\n  consumes:\n    - import: factset-callstreet\n      location: ./shared/documents-distributor-callstreet-events.yaml\n    - import: factset-streetaccount\n      location: ./shared/streetaccount-news.yaml\n    - import: factset-filings\n      location: ./shared/global-filings.yaml\n    - import: factset-signals\n      location: ./shared/signals.yaml\n    - import: factset-nlp\n      location: ./shared/natural-language-processing.yaml\n\
  \    - import: factset-search\n      location: ./shared/search-answers.yaml\n    - import: factset-conv\n      location: ./shared/conversational-api-powered-by-mercury.yaml\n\n  exposes:\n    - type: rest\n      port: 8087\n      namespace: content-intel-api\n      description: \"Unified REST API for content and intelligence.\"\n      resources:\n        - path: /v1/news\n          name: news\n          description: \"StreetAccount news.\"\n          operations:\n            - method: GET\n              name: get-news\n              description: \"Get news articles.\"\n              call: \"factset-streetaccount.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/filings\n          name: filings\n          description: \"Global filings.\"\n          operations:\n            - method: GET\n              name: get-filings\n              description: \"Get regulatory filings.\"\n              call: \"factset-filings.list\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/signals\n          name: signals\n          description: \"Material event signals.\"\n          operations:\n            - method: GET\n              name: get-signals\n              description: \"Get signals.\"\n              call: \"factset-signals.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: \"Natural language search.\"\n          operations:\n            - method: GET\n              name: search\n              description: \"Search for answers.\"\n              call: \"factset-search.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9087\n      namespace: content-intel-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ content intelligence.\"\n      tools:\n        - name: get-callstreet-events\n          description: \"Get earnings call transcripts.\"\n          hints:\n            readOnly: true\n          call: \"factset-callstreet.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-news\n          description: \"Get StreetAccount news.\"\n          hints:\n            readOnly: true\n          call: \"factset-streetaccount.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-filings\n          description: \"Get global regulatory filings.\"\n          hints:\n            readOnly: true\n          call: \"factset-filings.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-signals\n          description: \"Get material event signals.\"\n          hints:\n            readOnly: true\n          call: \"factset-signals.list\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-nlp\n          description: \"Run NLP analysis on text.\"\n          hints:\n            readOnly: true\n          call: \"factset-nlp.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-answers\n          description: \"Natural language search.\"\n          hints:\n            readOnly: true\n          call: \"factset-search.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: conversational-query\n          description: \"Conversational AI query.\"\n          hints:\n            readOnly: true\n          call: \"factset-conv.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/content-intelligence.yaml
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

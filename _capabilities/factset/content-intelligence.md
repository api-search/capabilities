---
categories: []
consumed_apis: []
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
- get filings
- get news
- get signals.
- conversational ai query.
- news
- conversational query
- get streetaccount news.
- get news articles.
- factset
- get material event signals.
- run nlp analysis on text.
- nlp
- natural language search.
- portfolio analytics
- get signals
- signals
- financial data
- research
- search answers
- content
- get global regulatory filings.
- get regulatory filings.
- run nlp
- financial
- get earnings call transcripts.
- market data
- material event signals.
- search
- streetaccount news.
- investment analytics
- global filings.
- search for answers.
- get callstreet events
slug: content-intelligence
source_filename: content-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FactSet Content and Intelligence\n  description: Unified workflow for content retrieval and intelligence including news, filings, earnings calls, NLP, signals,\n    and conversational search. Used by content consumers and data scientists.\n  tags:\n  - FactSet\n  - Content\n  - NLP\n  - News\n  - Signals\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACTSET_USERNAME: FACTSET_USERNAME\n    FACTSET_PASSWORD: FACTSET_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n  \
  \    path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event\
  \ signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8087\n    namespace: content-intel-api\n    description: Unified REST API for content and intelligence.\n    resources:\n    - path: /v1/news\n      name: news\n      description: StreetAccount news.\n      operations:\n      - method: GET\n        name: get-news\n        description: Get news articles.\n        call: factset-streetaccount.list\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/filings\n      name: filings\n      description: Global filings.\n      operations:\n      - method: GET\n        name: get-filings\n        description: Get regulatory filings.\n        call: factset-filings.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/signals\n      name: signals\n      description: Material event signals.\n      operations:\n      - method: GET\n        name: get-signals\n        description: Get signals.\n        call: factset-signals.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Natural language search.\n      operations:\n      - method: GET\n        name: search\n        description: Search for answers.\n        call: factset-search.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n\
  \    port: 9087\n    namespace: content-intel-mcp\n    transport: http\n    description: MCP server for AI-assisted content intelligence.\n    tools:\n    - name: get-callstreet-events\n      description: Get earnings call transcripts.\n      hints:\n        readOnly: true\n      call: factset-callstreet.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-news\n      description: Get StreetAccount news.\n      hints:\n        readOnly: true\n      call: factset-streetaccount.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-filings\n      description: Get global regulatory filings.\n      hints:\n        readOnly: true\n      call: factset-filings.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-signals\n      description: Get material event signals.\n      hints:\n        readOnly: true\n      call: factset-signals.list\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: run-nlp\n      description: Run NLP analysis on text.\n      hints:\n        readOnly: true\n      call: factset-nlp.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-answers\n      description: Natural language search.\n      hints:\n        readOnly: true\n      call: factset-search.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: conversational-query\n      description: Conversational AI query.\n      hints:\n        readOnly: true\n      call: factset-conv.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

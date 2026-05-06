---
categories: []
consumed_apis: []
description: The International Trade Administration (ITA) Data Services Platform provides programmatic access to authoritative U.S. trade data including the Consolidated Screening List (CSL), Country Commercial Guides (CCG), Market Intelligence, Trade Events, and the Customs Info Tariff Database. Access requires an API subscription key issued through the ITA developer portal.
layout: capability
name: International Trade Administration Data Services API
operations:
- description: Search the Consolidated Screening List
  method: GET
  name: searchconsolidatedscreeninglist
  path: /consolidated_screening_list/v1/search
- description: List screening list sources
  method: GET
  name: listscreeningsources
  path: /consolidated_screening_list/v1/sources
- description: Search Country Commercial Guides
  method: GET
  name: searchcountrycommercialguides
  path: /CCG/v2/search
- description: Search Market Intelligence articles
  method: GET
  name: searchmarketintelligence
  path: /market_intelligence/v1/search
- description: Search Trade Events
  method: GET
  name: searchtradeevents
  path: /events/v1/search
- description: Search the Customs Info Tariff Database
  method: GET
  name: searchcustomstariff
  path: /customs_tariff/v1/search
- description: Search De Minimis values
  method: GET
  name: searchdeminimis
  path: /de_minimis/v1/search
personas: []
provider_name: International Trade Administration
provider_slug: international-trade-administration
search_terms:
- searchconsolidatedscreeninglist
- searchdeminimis
- search de minimis values
- export
- screening list
- search the consolidated screening list
- international business
- trade
- searchmarketintelligence
- trade events
- compliance
- search country commercial guides
- list screening list sources
- searchcountrycommercialguides
- api
- administration
- listscreeningsources
- customs
- international
- search market intelligence articles
- searchcustomstariff
- tariffs
- federal government
- search trade events
- trade data
- search the customs info tariff database
- searchtradeevents
slug: international-trade-administration-capability
source_filename: international-trade-administration-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: International Trade Administration Data Services API\n  description: The International Trade Administration (ITA) Data Services Platform provides programmatic access to authoritative\n    U.S. trade data including the Consolidated Screening List (CSL), Country Commercial Guides (CCG), Market Intelligence,\n    Trade Events, and the Customs Info Tariff Database. Access requires an API subscription key issued through the ITA developer\n    portal.\n  tags:\n  - International\n  - Trade\n  - Administration\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: international-trade-administration\n    baseUri: https://data.trade.gov\n    description: International Trade Administration Data Services API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: subscription-key\n      value: '{{INTERNATIONAL_TRADE_ADMINISTRATION_TOKEN}}'\n    resources:\n \
  \   - name: consolidated-screening-list-v1-search\n      path: /consolidated_screening_list/v1/search\n      operations:\n      - name: searchconsolidatedscreeninglist\n        method: GET\n        description: Search the Consolidated Screening List\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Name of the entity or individual to screen.\n        - name: fuzzy_name\n          in: query\n          type: string\n          description: Enable fuzzy name matching.\n        - name: sources\n          in: query\n          type: string\n          description: Comma-separated list of source lists to query.\n        - name: countries\n          in: query\n          type: string\n          description: Comma-separated ISO country codes to filter results.\n        - name: type\n          in: query\n          type: string\n          description: Filter by type (Entity, Individual, Vessel, Aircraft).\n        - name: size\n    \
  \      in: query\n          type: integer\n          description: Number of results per page (max 100).\n        - name: offset\n          in: query\n          type: integer\n          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consolidated-screening-list-v1-sources\n      path: /consolidated_screening_list/v1/sources\n      operations:\n      - name: listscreeningsources\n        method: GET\n        description: List screening list sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ccg-v2-search\n      path: /CCG/v2/search\n      operations:\n      - name: searchcountrycommercialguides\n        method: GET\n        description: Search Country Commercial Guides\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description:\
  \ Free-text query.\n        - name: countries\n          in: query\n          type: string\n          description: Comma-separated ISO country codes.\n        - name: industries\n          in: query\n          type: string\n          description: Comma-separated industry filter.\n        - name: size\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: market-intelligence-v1-search\n      path: /market_intelligence/v1/search\n      operations:\n      - name: searchmarketintelligence\n        method: GET\n        description: Search Market Intelligence articles\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n        - name: countries\n          in: query\n          type: string\n        - name: industries\n          in: query\n          type: string\n\
  \        - name: size\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-v1-search\n      path: /events/v1/search\n      operations:\n      - name: searchtradeevents\n        method: GET\n        description: Search Trade Events\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n        - name: event_types\n          in: query\n          type: string\n        - name: industries\n          in: query\n          type: string\n        - name: countries\n          in: query\n          type: string\n        - name: start_date\n          in: query\n          type: string\n        - name: end_date\n          in: query\n          type: string\n        - name: size\n          in: query\n          type: integer\n        - name: offset\n          in:\
  \ query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customs-tariff-v1-search\n      path: /customs_tariff/v1/search\n      operations:\n      - name: searchcustomstariff\n        method: GET\n        description: Search the Customs Info Tariff Database\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          required: true\n        - name: hs_code\n          in: query\n          type: string\n        - name: keyword\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: de-minimis-v1-search\n      path: /de_minimis/v1/search\n      operations:\n      - name: searchdeminimis\n        method: GET\n        description: Search De Minimis values\n        inputParameters:\n        - name: countries\n\
  \          in: query\n          type: string\n        - name: size\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: international-trade-administration-rest\n    description: REST adapter for International Trade Administration Data Services API.\n    resources:\n    - path: /consolidated_screening_list/v1/search\n      name: searchconsolidatedscreeninglist\n      operations:\n      - method: GET\n        name: searchconsolidatedscreeninglist\n        description: Search the Consolidated Screening List\n        call: international-trade-administration.searchconsolidatedscreeninglist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /consolidated_screening_list/v1/sources\n      name: listscreeningsources\n\
  \      operations:\n      - method: GET\n        name: listscreeningsources\n        description: List screening list sources\n        call: international-trade-administration.listscreeningsources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /CCG/v2/search\n      name: searchcountrycommercialguides\n      operations:\n      - method: GET\n        name: searchcountrycommercialguides\n        description: Search Country Commercial Guides\n        call: international-trade-administration.searchcountrycommercialguides\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /market_intelligence/v1/search\n      name: searchmarketintelligence\n      operations:\n      - method: GET\n        name: searchmarketintelligence\n        description: Search Market Intelligence articles\n        call: international-trade-administration.searchmarketintelligence\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /events/v1/search\n      name: searchtradeevents\n      operations:\n      - method: GET\n        name: searchtradeevents\n        description: Search Trade Events\n        call: international-trade-administration.searchtradeevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customs_tariff/v1/search\n      name: searchcustomstariff\n      operations:\n      - method: GET\n        name: searchcustomstariff\n        description: Search the Customs Info Tariff Database\n        call: international-trade-administration.searchcustomstariff\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /de_minimis/v1/search\n      name: searchdeminimis\n      operations:\n      - method: GET\n        name: searchdeminimis\n        description: Search De Minimis values\n        call: international-trade-administration.searchdeminimis\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \  - type: mcp\n    port: 9090\n    namespace: international-trade-administration-mcp\n    transport: http\n    description: MCP adapter for International Trade Administration Data Services API for AI agent use.\n    tools:\n    - name: searchconsolidatedscreeninglist\n      description: Search the Consolidated Screening List\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: international-trade-administration.searchconsolidatedscreeninglist\n      with:\n        name: tools.name\n        fuzzy_name: tools.fuzzy_name\n        sources: tools.sources\n        countries: tools.countries\n        type: tools.type\n        size: tools.size\n        offset: tools.offset\n      inputParameters:\n      - name: name\n        type: string\n        description: Name of the entity or individual to screen.\n      - name: fuzzy_name\n        type: string\n        description: Enable fuzzy name matching.\n      - name: sources\n        type: string\n\
  \        description: Comma-separated list of source lists to query.\n      - name: countries\n        type: string\n        description: Comma-separated ISO country codes to filter results.\n      - name: type\n        type: string\n        description: Filter by type (Entity, Individual, Vessel, Aircraft).\n      - name: size\n        type: integer\n        description: Number of results per page (max 100).\n      - name: offset\n        type: integer\n        description: Pagination offset.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listscreeningsources\n      description: List screening list sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: international-trade-administration.listscreeningsources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcountrycommercialguides\n      description: Search Country Commercial Guides\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: international-trade-administration.searchcountrycommercialguides\n      with:\n        q: tools.q\n        countries: tools.countries\n        industries: tools.industries\n        size: tools.size\n        offset: tools.offset\n      inputParameters:\n      - name: q\n        type: string\n        description: Free-text query.\n      - name: countries\n        type: string\n        description: Comma-separated ISO country codes.\n      - name: industries\n        type: string\n        description: Comma-separated industry filter.\n      - name: size\n        type: integer\n        description: size\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchmarketintelligence\n      description: Search Market Intelligence articles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: international-trade-administration.searchmarketintelligence\n      with:\n        q: tools.q\n        countries: tools.countries\n        industries: tools.industries\n        size: tools.size\n        offset: tools.offset\n      inputParameters:\n      - name: q\n        type: string\n        description: q\n      - name: countries\n        type: string\n        description: countries\n      - name: industries\n        type: string\n        description: industries\n      - name: size\n        type: integer\n        description: size\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchtradeevents\n      description: Search Trade Events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: international-trade-administration.searchtradeevents\n      with:\n        q: tools.q\n        event_types: tools.event_types\n\
  \        industries: tools.industries\n        countries: tools.countries\n        start_date: tools.start_date\n        end_date: tools.end_date\n        size: tools.size\n        offset: tools.offset\n      inputParameters:\n      - name: q\n        type: string\n        description: q\n      - name: event_types\n        type: string\n        description: event_types\n      - name: industries\n        type: string\n        description: industries\n      - name: countries\n        type: string\n        description: countries\n      - name: start_date\n        type: string\n        description: start_date\n      - name: end_date\n        type: string\n        description: end_date\n      - name: size\n        type: integer\n        description: size\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcustomstariff\n      description: Search the Customs Info Tariff Database\n   \
  \   hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: international-trade-administration.searchcustomstariff\n      with:\n        country: tools.country\n        hs_code: tools.hs_code\n        keyword: tools.keyword\n      inputParameters:\n      - name: country\n        type: string\n        description: country\n        required: true\n      - name: hs_code\n        type: string\n        description: hs_code\n      - name: keyword\n        type: string\n        description: keyword\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchdeminimis\n      description: Search De Minimis values\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: international-trade-administration.searchdeminimis\n      with:\n        countries: tools.countries\n        size: tools.size\n        offset: tools.offset\n      inputParameters:\n      - name: countries\n       \
  \ type: string\n        description: countries\n      - name: size\n        type: integer\n        description: size\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    INTERNATIONAL_TRADE_ADMINISTRATION_TOKEN: INTERNATIONAL_TRADE_ADMINISTRATION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/international-trade-administration/refs/heads/main/capabilities/international-trade-administration-capability.yaml
tags:
- International
- Trade
- Administration
- API
tools:
- description: Search the Consolidated Screening List
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchconsolidatedscreeninglist
- description: List screening list sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscreeningsources
- description: Search Country Commercial Guides
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcountrycommercialguides
- description: Search Market Intelligence articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchmarketintelligence
- description: Search Trade Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchtradeevents
- description: Search the Customs Info Tariff Database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcustomstariff
- description: Search De Minimis values
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchdeminimis
---

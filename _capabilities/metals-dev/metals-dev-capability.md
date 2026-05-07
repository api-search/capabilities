---
categories: []
consumed_apis: []
description: Metals.Dev provides a developer-friendly JSON API for spot prices of precious metals, industrial metals, and currency conversion rates. It offers real-time prices from leading authorities including LBMA, LME, MCX, and IBJA, plus 5+ years of historical data.
layout: capability
name: Metals.Dev API
operations:
- description: Get latest rates
  method: GET
  name: getlatest
  path: /latest
- description: Get spot metal price
  method: GET
  name: getmetalspot
  path: /metal/spot
- description: Get authority metal price
  method: GET
  name: getmetalauthority
  path: /metal/authority
- description: Get currency rates
  method: GET
  name: getcurrencies
  path: /currencies
- description: Get historical timeseries
  method: GET
  name: gettimeseries
  path: /timeseries
- description: Get account usage
  method: GET
  name: getusage
  path: /usage
personas: []
provider_name: Metals.Dev
provider_slug: metals-dev
search_terms:
- metals
- spot prices
- api
- get authority metal price
- precious metals
- get historical timeseries
- get spot metal price
- get latest rates
- dev
- financial data
- get account usage
- gold
- getusage
- getlatest
- getmetalspot
- gettimeseries
- silver
- getmetalauthority
- getcurrencies
- get currency rates
slug: metals-dev-capability
source_filename: metals-dev-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Metals.Dev API\n  description: Metals.Dev provides a developer-friendly JSON API for spot prices of precious metals, industrial metals, and\n    currency conversion rates. It offers real-time prices from leading authorities including LBMA, LME, MCX, and IBJA, plus\n    5+ years of historical data.\n  tags:\n  - Metals\n  - Dev\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: metals-dev\n    baseUri: https://api.metals.dev/v1\n    description: Metals.Dev API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: api_key\n      value: '{{METALS_DEV_TOKEN}}'\n    resources:\n    - name: latest\n      path: /latest\n      operations:\n      - name: getlatest\n        method: GET\n        description: Get latest rates\n        inputParameters:\n        - name: currency\n          in: query\n          type: string\n          description: Three-letter\
  \ currency code. Defaults to USD.\n        - name: unit\n          in: query\n          type: string\n          description: Unit of measure (toz, g, kg, mt). Defaults to toz for precious metals and mt for industrial.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metal-spot\n      path: /metal/spot\n      operations:\n      - name: getmetalspot\n        method: GET\n        description: Get spot metal price\n        inputParameters:\n        - name: metal\n          in: query\n          type: string\n          required: true\n          description: Metal symbol.\n        - name: currency\n          in: query\n          type: string\n          description: Three-letter currency code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metal-authority\n      path: /metal/authority\n      operations:\n      -\
  \ name: getmetalauthority\n        method: GET\n        description: Get authority metal price\n        inputParameters:\n        - name: authority\n          in: query\n          type: string\n          required: true\n          description: Authority code.\n        - name: currency\n          in: query\n          type: string\n        - name: unit\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: currencies\n      path: /currencies\n      operations:\n      - name: getcurrencies\n        method: GET\n        description: Get currency rates\n        inputParameters:\n        - name: base\n          in: query\n          type: string\n          description: Base currency for conversion.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timeseries\n      path: /timeseries\n\
  \      operations:\n      - name: gettimeseries\n        method: GET\n        description: Get historical timeseries\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          required: true\n        - name: end_date\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: usage\n      path: /usage\n      operations:\n      - name: getusage\n        method: GET\n        description: Get account usage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: metals-dev-rest\n    description: REST adapter for Metals.Dev API.\n    resources:\n    - path: /latest\n      name: getlatest\n      operations:\n      - method: GET\n        name: getlatest\n        description:\
  \ Get latest rates\n        call: metals-dev.getlatest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metal/spot\n      name: getmetalspot\n      operations:\n      - method: GET\n        name: getmetalspot\n        description: Get spot metal price\n        call: metals-dev.getmetalspot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metal/authority\n      name: getmetalauthority\n      operations:\n      - method: GET\n        name: getmetalauthority\n        description: Get authority metal price\n        call: metals-dev.getmetalauthority\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /currencies\n      name: getcurrencies\n      operations:\n      - method: GET\n        name: getcurrencies\n        description: Get currency rates\n        call: metals-dev.getcurrencies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /timeseries\n\
  \      name: gettimeseries\n      operations:\n      - method: GET\n        name: gettimeseries\n        description: Get historical timeseries\n        call: metals-dev.gettimeseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /usage\n      name: getusage\n      operations:\n      - method: GET\n        name: getusage\n        description: Get account usage\n        call: metals-dev.getusage\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: metals-dev-mcp\n    transport: http\n    description: MCP adapter for Metals.Dev API for AI agent use.\n    tools:\n    - name: getlatest\n      description: Get latest rates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-dev.getlatest\n      with:\n        currency: tools.currency\n        unit: tools.unit\n      inputParameters:\n      - name: currency\n        type: string\n\
  \        description: Three-letter currency code. Defaults to USD.\n      - name: unit\n        type: string\n        description: Unit of measure (toz, g, kg, mt). Defaults to toz for precious metals and mt for industrial.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmetalspot\n      description: Get spot metal price\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-dev.getmetalspot\n      with:\n        metal: tools.metal\n        currency: tools.currency\n      inputParameters:\n      - name: metal\n        type: string\n        description: Metal symbol.\n        required: true\n      - name: currency\n        type: string\n        description: Three-letter currency code.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmetalauthority\n      description: Get authority metal price\n      hints:\n        readOnly: true\n        destructive: false\n \
  \       idempotent: true\n      call: metals-dev.getmetalauthority\n      with:\n        authority: tools.authority\n        currency: tools.currency\n        unit: tools.unit\n      inputParameters:\n      - name: authority\n        type: string\n        description: Authority code.\n        required: true\n      - name: currency\n        type: string\n        description: currency\n      - name: unit\n        type: string\n        description: unit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcurrencies\n      description: Get currency rates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-dev.getcurrencies\n      with:\n        base: tools.base\n      inputParameters:\n      - name: base\n        type: string\n        description: Base currency for conversion.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettimeseries\n      description: Get historical\
  \ timeseries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-dev.gettimeseries\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n      inputParameters:\n      - name: start_date\n        type: string\n        description: start_date\n        required: true\n      - name: end_date\n        type: string\n        description: end_date\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getusage\n      description: Get account usage\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: metals-dev.getusage\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    METALS_DEV_TOKEN: METALS_DEV_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/metals-dev/refs/heads/main/capabilities/metals-dev-capability.yaml
tags:
- Metals
- Dev
- API
tools:
- description: Get latest rates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlatest
- description: Get spot metal price
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetalspot
- description: Get authority metal price
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetalauthority
- description: Get currency rates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrencies
- description: Get historical timeseries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettimeseries
- description: Get account usage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusage
---

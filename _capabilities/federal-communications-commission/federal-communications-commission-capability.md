---
categories: []
consumed_apis: []
description: The FCC Electronic Comment Filing System (ECFS) public API provides programmatic access to filings, proceedings, and submissions made to the Federal Communications Commission.
layout: capability
name: FCC ECFS API
operations:
- description: Search ECFS filings
  method: GET
  name: listfilings
  path: /filings
- description: Search ECFS proceedings
  method: GET
  name: listproceedings
  path: /proceedings
personas: []
provider_name: Federal Communications Commission
provider_slug: federal-communications-commission
search_terms:
- federal government
- listfilings
- commission
- api
- open data
- federal
- search ecfs proceedings
- search ecfs filings
- communications
- listproceedings
slug: federal-communications-commission-capability
source_filename: federal-communications-commission-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FCC ECFS API\n  description: The FCC Electronic Comment Filing System (ECFS) public API provides programmatic access to filings, proceedings,\n    and submissions made to the Federal Communications Commission.\n  tags:\n  - Federal\n  - Communications\n  - Commission\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: federal-communications-commission\n    baseUri: https://publicapi.fcc.gov/ecfs\n    description: FCC ECFS API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: api_key\n      value: '{{FEDERAL_COMMUNICATIONS_COMMISSION_TOKEN}}'\n    resources:\n    - name: filings\n      path: /filings\n      operations:\n      - name: listfilings\n        method: GET\n        description: Search ECFS filings\n        inputParameters:\n        - name: api_key\n          in: query\n          type: string\n          required: true\n          description:\
  \ api.data.gov API key.\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        - name: proceedings.name\n          in: query\n          type: string\n          description: Proceeding (docket) number filter.\n        - name: sort\n          in: query\n          type: string\n          description: Field name and direction (e.g. date_disseminated,DESC).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: proceedings\n      path: /proceedings\n      operations:\n      - name: listproceedings\n        method: GET\n        description: Search ECFS proceedings\n        inputParameters:\n        - name: api_key\n          in: query\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n\
  \        - name: name\n          in: query\n          type: string\n          description: Proceeding (docket) number filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: federal-communications-commission-rest\n    description: REST adapter for FCC ECFS API.\n    resources:\n    - path: /filings\n      name: listfilings\n      operations:\n      - method: GET\n        name: listfilings\n        description: Search ECFS filings\n        call: federal-communications-commission.listfilings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /proceedings\n      name: listproceedings\n      operations:\n      - method: GET\n        name: listproceedings\n        description: Search ECFS proceedings\n        call: federal-communications-commission.listproceedings\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: federal-communications-commission-mcp\n    transport: http\n    description: MCP adapter for FCC ECFS API for AI agent use.\n    tools:\n    - name: listfilings\n      description: Search ECFS filings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-communications-commission.listfilings\n      with:\n        api_key: tools.api_key\n        limit: tools.limit\n        offset: tools.offset\n        proceedings.name: tools.proceedings.name\n        sort: tools.sort\n      inputParameters:\n      - name: api_key\n        type: string\n        description: api.data.gov API key.\n        required: true\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      - name: proceedings.name\n        type: string\n        description: Proceeding (docket) number filter.\n     \
  \ - name: sort\n        type: string\n        description: Field name and direction (e.g. date_disseminated,DESC).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listproceedings\n      description: Search ECFS proceedings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-communications-commission.listproceedings\n      with:\n        api_key: tools.api_key\n        limit: tools.limit\n        offset: tools.offset\n        name: tools.name\n      inputParameters:\n      - name: api_key\n        type: string\n        description: api_key\n        required: true\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      - name: name\n        type: string\n        description: Proceeding (docket) number filter.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n\
  \  keys:\n    FEDERAL_COMMUNICATIONS_COMMISSION_TOKEN: FEDERAL_COMMUNICATIONS_COMMISSION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/federal-communications-commission/refs/heads/main/capabilities/federal-communications-commission-capability.yaml
tags:
- Federal
- Communications
- Commission
- API
tools:
- description: Search ECFS filings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfilings
- description: Search ECFS proceedings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproceedings
---

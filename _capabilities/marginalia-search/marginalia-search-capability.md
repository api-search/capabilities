---
categories: []
consumed_apis: []
description: The Marginalia Search API provides programmatic access to the Marginalia independent search engine, focused on non-commercial content. The new API is hosted at api2.marginalia-search.com; legacy endpoints at api.marginalia.nu and api.marginalia-search.com remain available but deprecated. Search results are available under CC-BY-NC-SA 4.0 for non-commercial use.
layout: capability
name: Marginalia Search API
operations:
- description: Execute a web search
  method: GET
  name: search
  path: /search
- description: List configured filters
  method: GET
  name: listfilters
  path: /filter
- description: Retrieve a filter definition
  method: GET
  name: getfilter
  path: /filter/{name}
- description: Create a named filter
  method: POST
  name: createfilter
  path: /filter/{name}
- description: Delete a filter
  method: DELETE
  name: deletefilter
  path: /filter/{name}
personas: []
provider_name: Marginalia Search
provider_slug: marginalia-search
search_terms:
- getfilter
- execute a web search
- open source
- list configured filters
- delete a filter
- search
- web search
- marginalia
- retrieve a filter definition
- api
- deletefilter
- listfilters
- create a named filter
- createfilter
slug: marginalia-search-capability
source_filename: marginalia-search-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Marginalia Search API\n  description: The Marginalia Search API provides programmatic access to the Marginalia independent search engine, focused\n    on non-commercial content. The new API is hosted at api2.marginalia-search.com; legacy endpoints at api.marginalia.nu\n    and api.marginalia-search.com remain available but deprecated. Search results are available under CC-BY-NC-SA 4.0 for\n    non-commercial use.\n  tags:\n  - Marginalia\n  - Search\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: marginalia-search\n    baseUri: https://api2.marginalia-search.com\n    description: Marginalia Search API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: API-Key\n      value: '{{MARGINALIA_SEARCH_TOKEN}}'\n    resources:\n    - name: search\n      path: /search\n      operations:\n      - name: search\n        method: GET\n        description:\
  \ Execute a web search\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search terms.\n        - name: count\n          in: query\n          type: integer\n          description: Number of results to return.\n        - name: timeout\n          in: query\n          type: integer\n          description: Maximum execution time in milliseconds.\n        - name: dc\n          in: query\n          type: integer\n          description: Maximum results per domain.\n        - name: page\n          in: query\n          type: integer\n          description: Result page (1-indexed).\n        - name: nsfw\n          in: query\n          type: integer\n          description: NSFW content filtering (experimental).\n        - name: filter\n          in: query\n          type: string\n          description: Apply a named filter previously created via /filter.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: filter\n      path: /filter\n      operations:\n      - name: listfilters\n        method: GET\n        description: List configured filters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filter-name\n      path: /filter/{name}\n      operations:\n      - name: getfilter\n        method: GET\n        description: Retrieve a filter definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfilter\n        method: POST\n        description: Create a named filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefilter\n        method: DELETE\n        description: Delete a filter\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: marginalia-search-rest\n    description: REST adapter for Marginalia Search API.\n    resources:\n    - path: /search\n      name: search\n      operations:\n      - method: GET\n        name: search\n        description: Execute a web search\n        call: marginalia-search.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /filter\n      name: listfilters\n      operations:\n      - method: GET\n        name: listfilters\n        description: List configured filters\n        call: marginalia-search.listfilters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /filter/{name}\n      name: getfilter\n      operations:\n      - method: GET\n        name: getfilter\n        description: Retrieve a filter definition\n        call: marginalia-search.getfilter\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /filter/{name}\n      name: createfilter\n      operations:\n      - method: POST\n        name: createfilter\n        description: Create a named filter\n        call: marginalia-search.createfilter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /filter/{name}\n      name: deletefilter\n      operations:\n      - method: DELETE\n        name: deletefilter\n        description: Delete a filter\n        call: marginalia-search.deletefilter\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: marginalia-search-mcp\n    transport: http\n    description: MCP adapter for Marginalia Search API for AI agent use.\n    tools:\n    - name: search\n      description: Execute a web search\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marginalia-search.search\n      with:\n \
  \       query: tools.query\n        count: tools.count\n        timeout: tools.timeout\n        dc: tools.dc\n        page: tools.page\n        nsfw: tools.nsfw\n        filter: tools.filter\n      inputParameters:\n      - name: query\n        type: string\n        description: Search terms.\n        required: true\n      - name: count\n        type: integer\n        description: Number of results to return.\n      - name: timeout\n        type: integer\n        description: Maximum execution time in milliseconds.\n      - name: dc\n        type: integer\n        description: Maximum results per domain.\n      - name: page\n        type: integer\n        description: Result page (1-indexed).\n      - name: nsfw\n        type: integer\n        description: NSFW content filtering (experimental).\n      - name: filter\n        type: string\n        description: Apply a named filter previously created via /filter.\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: listfilters\n      description: List configured filters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marginalia-search.listfilters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfilter\n      description: Retrieve a filter definition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marginalia-search.getfilter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createfilter\n      description: Create a named filter\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marginalia-search.createfilter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletefilter\n      description: Delete a filter\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: marginalia-search.deletefilter\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MARGINALIA_SEARCH_TOKEN: MARGINALIA_SEARCH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/marginalia-search/refs/heads/main/capabilities/marginalia-search-capability.yaml
tags:
- Marginalia
- Search
- API
tools:
- description: Execute a web search
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search
- description: List configured filters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfilters
- description: Retrieve a filter definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfilter
- description: Create a named filter
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfilter
- description: Delete a filter
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefilter
---

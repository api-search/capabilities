---
categories: []
consumed_apis: []
description: The Google Custom Search JSON API allows programmatic searches over a website or collection of websites. It returns metadata about the search performed, metadata about the search engine used, and the search results.
layout: capability
name: Google Custom Search JSON API
operations:
- description: Google Custom Search Custom Search
  method: GET
  name: searchcustomsearch
  path: /customsearch/v1
- description: Google Custom Search Custom Search Site Restricted
  method: GET
  name: searchsiterestrict
  path: /customsearch/v1/siterestrict
personas: []
provider_name: Google Custom Search
provider_slug: google-custom-search
search_terms:
- custom
- google custom search custom search
- searchsiterestrict
- searchcustomsearch
- image search
- search
- google
- web search
- custom search
- google custom search custom search site restricted
- api
slug: google-custom-search-capability
source_filename: google-custom-search-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Custom Search JSON API\n  description: The Google Custom Search JSON API allows programmatic searches over a website or collection of websites. It\n    returns metadata about the search performed, metadata about the search engine used, and the search results.\n  tags:\n  - Google\n  - Custom\n  - Search\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-custom-search\n    baseUri: https://customsearch.googleapis.com\n    description: Google Custom Search JSON API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{GOOGLE_CUSTOM_SEARCH_TOKEN}}'\n    resources:\n    - name: customsearch-v1\n      path: /customsearch/v1\n      operations:\n      - name: searchcustomsearch\n        method: GET\n        description: Google Custom Search Custom Search\n        inputParameters:\n        - name: key\n          in:\
  \ query\n          type: string\n          required: true\n          description: API key.\n        - name: cx\n          in: query\n          type: string\n          required: true\n          description: The Programmable Search Engine ID.\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: The search query.\n        - name: num\n          in: query\n          type: integer\n          description: Number of results to return (1-10).\n        - name: start\n          in: query\n          type: integer\n          description: The index of the first result to return.\n        - name: lr\n          in: query\n          type: string\n          description: Language restriction.\n        - name: safe\n          in: query\n          type: string\n          description: Safe search setting.\n        - name: searchType\n          in: query\n          type: string\n          description: Type of search.\n        - name: imgSize\n   \
  \       in: query\n          type: string\n          description: Image size filter.\n        - name: imgType\n          in: query\n          type: string\n          description: Image type filter.\n        - name: dateRestrict\n          in: query\n          type: string\n          description: Restrict results by date.\n        - name: sort\n          in: query\n          type: string\n          description: Sort expression.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customsearch-v1-siterestrict\n      path: /customsearch/v1/siterestrict\n      operations:\n      - name: searchsiterestrict\n        method: GET\n        description: Google Custom Search Custom Search Site Restricted\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required: true\n        - name: cx\n          in: query\n          type: string\n          required: true\n\
  \        - name: q\n          in: query\n          type: string\n          required: true\n        - name: num\n          in: query\n          type: integer\n        - name: start\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-custom-search-rest\n    description: REST adapter for Google Custom Search JSON API.\n    resources:\n    - path: /customsearch/v1\n      name: searchcustomsearch\n      operations:\n      - method: GET\n        name: searchcustomsearch\n        description: Google Custom Search Custom Search\n        call: google-custom-search.searchcustomsearch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customsearch/v1/siterestrict\n      name: searchsiterestrict\n      operations:\n      - method: GET\n        name: searchsiterestrict\n      \
  \  description: Google Custom Search Custom Search Site Restricted\n        call: google-custom-search.searchsiterestrict\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-custom-search-mcp\n    transport: http\n    description: MCP adapter for Google Custom Search JSON API for AI agent use.\n    tools:\n    - name: searchcustomsearch\n      description: Google Custom Search Custom Search\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-custom-search.searchcustomsearch\n      with:\n        key: tools.key\n        cx: tools.cx\n        q: tools.q\n        num: tools.num\n        start: tools.start\n        lr: tools.lr\n        safe: tools.safe\n        searchType: tools.searchType\n        imgSize: tools.imgSize\n        imgType: tools.imgType\n        dateRestrict: tools.dateRestrict\n        sort: tools.sort\n      inputParameters:\n      - name:\
  \ key\n        type: string\n        description: API key.\n        required: true\n      - name: cx\n        type: string\n        description: The Programmable Search Engine ID.\n        required: true\n      - name: q\n        type: string\n        description: The search query.\n        required: true\n      - name: num\n        type: integer\n        description: Number of results to return (1-10).\n      - name: start\n        type: integer\n        description: The index of the first result to return.\n      - name: lr\n        type: string\n        description: Language restriction.\n      - name: safe\n        type: string\n        description: Safe search setting.\n      - name: searchType\n        type: string\n        description: Type of search.\n      - name: imgSize\n        type: string\n        description: Image size filter.\n      - name: imgType\n        type: string\n        description: Image type filter.\n      - name: dateRestrict\n        type: string\n       \
  \ description: Restrict results by date.\n      - name: sort\n        type: string\n        description: Sort expression.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchsiterestrict\n      description: Google Custom Search Custom Search Site Restricted\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-custom-search.searchsiterestrict\n      with:\n        key: tools.key\n        cx: tools.cx\n        q: tools.q\n        num: tools.num\n        start: tools.start\n      inputParameters:\n      - name: key\n        type: string\n        description: key\n        required: true\n      - name: cx\n        type: string\n        description: cx\n        required: true\n      - name: q\n        type: string\n        description: q\n        required: true\n      - name: num\n        type: integer\n        description: num\n      - name: start\n        type: integer\n        description: start\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CUSTOM_SEARCH_TOKEN: GOOGLE_CUSTOM_SEARCH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-custom-search/refs/heads/main/capabilities/google-custom-search-capability.yaml
tags:
- Google
- Custom
- Search
- API
tools:
- description: Google Custom Search Custom Search
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcustomsearch
- description: Google Custom Search Custom Search Site Restricted
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchsiterestrict
---

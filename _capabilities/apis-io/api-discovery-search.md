---
categories: []
consumed_apis:
- apis-io-search
description: Workflow capability for searching, discovering, and submitting APIs using the APIs.io search engine. Enables developers and platform engineers to programmatically find APIs by keyword across the full APIs.io index and submit their own APIs for discovery by others. The primary personas are API developers building integrations and API producers wanting their APIs discovered.
layout: capability
name: APIs.io API Discovery and Search
operations:
- description: Search for APIs by keyword or phrase
  method: GET
  name: search-apis
  path: /v1/apis
- description: Submit a new API to the directory
  method: POST
  name: submit-api
  path: /v1/apis
personas: []
provider_name: APIs.io
provider_slug: apis-io
search_terms:
- search engine
- api directory
- api rating
- apis.json
- api aggregation
- search apis
- finding apis in the directory by keyword or topic
- a developer searching for apis to integrate into their applications
- search for apis by keyword or phrase
- submit a new api to the apis.io index by providing a valid apis.json document. the api will be reviewed and added to the searchable directory.
- api search
- an api owner or provider submitting their api for discovery in the index
- search for apis in the directory and submit new apis for indexing
- submit api
- api discovery
- search and submit apis in the directory
- API Producer
- submit a new api to the directory
- API Developer
- api indexing
- search across the apis.io directory for apis matching a keyword or phrase. returns api names, descriptions, tags, quality scores, and links.
- submitting new apis to the directory for indexing and discovery
- apis.io
slug: api-discovery-search
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"APIs.io API Discovery and Search\"\n  description: \"Workflow capability for searching, discovering, and submitting APIs using the APIs.io search engine. Enables developers and platform engineers to programmatically find APIs by keyword across the full APIs.io index and submit their own APIs for discovery by others. The primary personas are API developers building integrations and API producers wanting their APIs discovered.\"\n  tags:\n    - API Discovery\n    - API Indexing\n    - API Search\n    - APIs.io\n    - APIs.json\n    - Search Engine\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APIS_IO_API_KEY: APIS_IO_API_KEY\n\ncapability:\n  consumes:\n    - import: apis-io-search\n      location: ./shared/search-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: api-discovery-search-api\n      description: \"Unified REST API for API discovery and\
  \ submission via APIs.io.\"\n      resources:\n        - path: /v1/apis\n          name: apis\n          description: \"Search and submit APIs in the directory\"\n          operations:\n            - method: GET\n              name: search-apis\n              description: \"Search for APIs by keyword or phrase\"\n              call: \"apis-io-search.search-apis\"\n              with:\n                search: \"rest.search\"\n                limit: \"rest.limit\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: submit-api\n              description: \"Submit a new API to the directory\"\n              call: \"apis-io-search.add-api\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: api-discovery-search-mcp\n      transport: http\n      description:\
  \ \"MCP server for AI-assisted API discovery and index submission.\"\n      tools:\n        - name: search-apis\n          description: \"Search across the APIs.io directory for APIs matching a keyword or phrase. Returns API names, descriptions, tags, quality scores, and links.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"apis-io-search.search-apis\"\n          with:\n            search: \"tools.search\"\n            limit: \"tools.limit\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: submit-api\n          description: \"Submit a new API to the APIs.io index by providing a valid APIs.json document. The API will be reviewed and added to the searchable directory.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"apis-io-search.add-api\"\n          with:\n            apis_json: \"tools.apis_json\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apis-io/refs/heads/main/capabilities/api-discovery-search.yaml
tags:
- API Discovery
- API Indexing
- API Search
- APIs.io
- APIs.json
- Search Engine
tools:
- description: Search across the APIs.io directory for APIs matching a keyword or phrase. Returns API names, descriptions, tags, quality scores, and links.
  hints:
    openWorld: true
    readOnly: true
  name: search-apis
- description: Submit a new API to the APIs.io index by providing a valid APIs.json document. The API will be reviewed and added to the searchable directory.
  hints:
    openWorld: false
    readOnly: false
  name: submit-api
---

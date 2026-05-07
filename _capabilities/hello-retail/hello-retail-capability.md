---
categories: []
consumed_apis: []
description: Hello Retail provides REST APIs for personalized product recommendations, on-site search, page-driven product listings, and customer bias retrieval. Endpoints are served from the core.helloretail.com host and accept JSON request bodies. Most endpoints expect a Bearer token issued from the My Hello Retail dashboard. The API powers e-commerce personalization use cases including product discovery, behavioral tracking, and merchandising.
layout: capability
name: Hello Retail API
operations:
- description: Request product recommendations
  method: POST
  name: getrecommendations
  path: /serve/recoms
- description: Run a search query
  method: POST
  name: search
  path: /serve/search
- description: Load a configured page
  method: POST
  name: loadpage
  path: /serve/pages/{key}
- description: Retrieve customer bias data
  method: POST
  name: getcustomerbias
  path: /serve/customer/bias
personas: []
provider_name: Hello Retail
provider_slug: hello-retail
search_terms:
- e-commerce
- run a search query
- getrecommendations
- search
- load a configured page
- personalization
- retail
- retrieve customer bias data
- api
- getcustomerbias
- hello
- request product recommendations
- loadpage
- product recommendations
slug: hello-retail-capability
source_filename: hello-retail-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hello Retail API\n  description: Hello Retail provides REST APIs for personalized product recommendations, on-site search, page-driven product\n    listings, and customer bias retrieval. Endpoints are served from the core.helloretail.com host and accept JSON request\n    bodies. Most endpoints expect a Bearer token issued from the My Hello Retail dashboard. The API powers e-commerce personalization\n    use cases including product discovery, behavioral tracking, and merchandising.\n  tags:\n  - Hello\n  - Retail\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hello-retail\n    baseUri: https://core.helloretail.com\n    description: Hello Retail API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{HELLO_RETAIL_TOKEN}}'\n    resources:\n    - name: serve-recoms\n      path: /serve/recoms\n      operations:\n      - name: getrecommendations\n        method:\
  \ POST\n        description: Request product recommendations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: serve-search\n      path: /serve/search\n      operations:\n      - name: search\n        method: POST\n        description: Run a search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: serve-pages-key\n      path: /serve/pages/{key}\n      operations:\n      - name: loadpage\n        method: POST\n        description: Load a configured page\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Page configuration key from My Hello Retail.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: serve-customer-bias\n      path:\
  \ /serve/customer/bias\n      operations:\n      - name: getcustomerbias\n        method: POST\n        description: Retrieve customer bias data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hello-retail-rest\n    description: REST adapter for Hello Retail API.\n    resources:\n    - path: /serve/recoms\n      name: getrecommendations\n      operations:\n      - method: POST\n        name: getrecommendations\n        description: Request product recommendations\n        call: hello-retail.getrecommendations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /serve/search\n      name: search\n      operations:\n      - method: POST\n        name: search\n        description: Run a search query\n        call: hello-retail.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /serve/pages/{key}\n      name: loadpage\n      operations:\n      - method: POST\n        name: loadpage\n        description: Load a configured page\n        call: hello-retail.loadpage\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /serve/customer/bias\n      name: getcustomerbias\n      operations:\n      - method: POST\n        name: getcustomerbias\n        description: Retrieve customer bias data\n        call: hello-retail.getcustomerbias\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hello-retail-mcp\n    transport: http\n    description: MCP adapter for Hello Retail API for AI agent use.\n    tools:\n    - name: getrecommendations\n      description: Request product recommendations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hello-retail.getrecommendations\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: search\n      description: Run a search query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hello-retail.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loadpage\n      description: Load a configured page\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hello-retail.loadpage\n      with:\n        key: tools.key\n      inputParameters:\n      - name: key\n        type: string\n        description: Page configuration key from My Hello Retail.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcustomerbias\n      description: Retrieve customer bias data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hello-retail.getcustomerbias\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HELLO_RETAIL_TOKEN: HELLO_RETAIL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hello-retail/refs/heads/main/capabilities/hello-retail-capability.yaml
tags:
- Hello
- Retail
- API
tools:
- description: Request product recommendations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getrecommendations
- description: Run a search query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: search
- description: Load a configured page
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: loadpage
- description: Retrieve customer bias data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getcustomerbias
---

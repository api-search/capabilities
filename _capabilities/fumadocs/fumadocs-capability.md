---
categories: []
consumed_apis: []
description: The Fumadocs OpenAPI Proxy API is a server-side HTTP proxy built into the fumadocs-openapi package that enables the interactive API playground to make requests to external OpenAPI servers from the browser without encountering CORS restrictions. The proxy accepts any HTTP method, extracts a target URL from the url query parameter, forwards the request to the target server, and returns the response. Allowed origins or URL prefixes can be configured to restrict which targets may be proxied. Documentation sites using the Fumadocs OpenAPI playground integrate this proxy at a route such as /api/prox
layout: capability
name: Fumadocs OpenAPI Proxy API
operations:
- description: Fumadocs Proxy a GET request to an external API
  method: GET
  name: proxyget
  path: /api/proxy
- description: Fumadocs Proxy a POST request to an external API
  method: POST
  name: proxypost
  path: /api/proxy
- description: Fumadocs Proxy a PUT request to an external API
  method: PUT
  name: proxyput
  path: /api/proxy
- description: Fumadocs Proxy a PATCH request to an external API
  method: PATCH
  name: proxypatch
  path: /api/proxy
- description: Fumadocs Proxy a DELETE request to an external API
  method: DELETE
  name: proxydelete
  path: /api/proxy
personas: []
provider_name: Fumadocs
provider_slug: fumadocs
search_terms:
- fumadocs proxy a delete request to an external api
- react
- proxypatch
- fumadocs proxy a patch request to an external api
- next.js
- fumadocs proxy a put request to an external api
- fumadocs proxy a post request to an external api
- proxyput
- fumadocs proxy a get request to an external api
- api
- proxydelete
- proxyget
- documentation
- proxypost
- fumadocs
- framework
slug: fumadocs-capability
source_filename: fumadocs-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fumadocs OpenAPI Proxy API\n  description: The Fumadocs OpenAPI Proxy API is a server-side HTTP proxy built into the fumadocs-openapi package that enables\n    the interactive API playground to make requests to external OpenAPI servers from the browser without encountering CORS\n    restrictions. The proxy accepts any HTTP method, extracts a target URL from the url query parameter, forwards the request\n    to the target server, and returns the response. Allowed origins or URL prefixes can be configured to restrict which targets\n    may be proxied. Documentation sites using the Fumadocs OpenAPI playground integrate this proxy at a route such as /api/prox\n  tags:\n  - Fumadocs\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fumadocs\n    baseUri: http://localhost:3000\n    description: Fumadocs OpenAPI Proxy API HTTP API.\n    resources:\n    - name: api-proxy\n   \
  \   path: /api/proxy\n      operations:\n      - name: proxyget\n        method: GET\n        description: Fumadocs Proxy a GET request to an external API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: proxypost\n        method: POST\n        description: Fumadocs Proxy a POST request to an external API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: proxyput\n        method: PUT\n        description: Fumadocs Proxy a PUT request to an external API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: proxypatch\n        method: PATCH\n        description: Fumadocs Proxy a PATCH request to an external API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: proxydelete\n        method: DELETE\n        description: Fumadocs Proxy a DELETE request to an external API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fumadocs-rest\n    description: REST adapter for Fumadocs OpenAPI Proxy API.\n    resources:\n    - path: /api/proxy\n      name: proxyget\n      operations:\n      - method: GET\n        name: proxyget\n        description: Fumadocs Proxy a GET request to an external API\n        call: fumadocs.proxyget\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/proxy\n      name: proxypost\n      operations:\n      - method: POST\n        name: proxypost\n        description: Fumadocs Proxy a POST request to an external API\n        call: fumadocs.proxypost\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /api/proxy\n      name: proxyput\n      operations:\n      - method: PUT\n        name: proxyput\n        description: Fumadocs Proxy a PUT request to an external API\n        call: fumadocs.proxyput\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/proxy\n      name: proxypatch\n      operations:\n      - method: PATCH\n        name: proxypatch\n        description: Fumadocs Proxy a PATCH request to an external API\n        call: fumadocs.proxypatch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/proxy\n      name: proxydelete\n      operations:\n      - method: DELETE\n        name: proxydelete\n        description: Fumadocs Proxy a DELETE request to an external API\n        call: fumadocs.proxydelete\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fumadocs-mcp\n    transport: http\n    description: MCP adapter for\
  \ Fumadocs OpenAPI Proxy API for AI agent use.\n    tools:\n    - name: proxyget\n      description: Fumadocs Proxy a GET request to an external API\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fumadocs.proxyget\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxypost\n      description: Fumadocs Proxy a POST request to an external API\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fumadocs.proxypost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxyput\n      description: Fumadocs Proxy a PUT request to an external API\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: fumadocs.proxyput\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxypatch\n      description: Fumadocs Proxy a PATCH request to an external API\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fumadocs.proxypatch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxydelete\n      description: Fumadocs Proxy a DELETE request to an external API\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fumadocs.proxydelete\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fumadocs/refs/heads/main/capabilities/fumadocs-capability.yaml
tags:
- Fumadocs
- API
tools:
- description: Fumadocs Proxy a GET request to an external API
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: proxyget
- description: Fumadocs Proxy a POST request to an external API
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: proxypost
- description: Fumadocs Proxy a PUT request to an external API
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: proxyput
- description: Fumadocs Proxy a PATCH request to an external API
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: proxypatch
- description: Fumadocs Proxy a DELETE request to an external API
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: proxydelete
---

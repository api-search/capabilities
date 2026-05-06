---
categories: []
consumed_apis: []
description: 'A RESTful API for programmatically accessing the public-apis directory data. The API supports CORS and requires no authentication. All responses are served over HTTPS. Original source: davemachado/public-api.'
layout: capability
name: Public APIs API
operations:
- description: List entries
  method: GET
  name: listentries
  path: /entries
- description: Random entry
  method: GET
  name: getrandomentry
  path: /random
- description: List categories
  method: GET
  name: listcategories
  path: /categories
- description: Health check
  method: GET
  name: gethealth
  path: /health
personas: []
provider_name: Public APIs
provider_slug: public-apis
search_terms:
- public
- apis
- health check
- api
- list entries
- random entry
- api discovery
- api directory
- listentries
- getrandomentry
- listcategories
- list categories
- free apis
- open source
- api aggregation
- gethealth
slug: public-apis-capability
source_filename: public-apis-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Public APIs API\n  description: 'A RESTful API for programmatically accessing the public-apis directory data. The API supports CORS and requires\n    no authentication. All responses are served over HTTPS. Original source: davemachado/public-api.'\n  tags:\n  - Public\n  - Apis\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: public-apis\n    baseUri: https://api.publicapis.org\n    description: Public APIs API HTTP API.\n    resources:\n    - name: entries\n      path: /entries\n      operations:\n      - name: listentries\n        method: GET\n        description: List entries\n        inputParameters:\n        - name: title\n          in: query\n          type: string\n          description: Filter entries whose title contains the provided value.\n        - name: description\n          in: query\n          type: string\n          description: Filter entries whose description\
  \ contains the provided value.\n        - name: auth\n          in: query\n          type: string\n          description: Filter entries by authentication type.\n        - name: https\n          in: query\n          type: boolean\n          description: Filter entries by HTTPS support.\n        - name: cors\n          in: query\n          type: string\n          description: Filter entries by CORS support.\n        - name: category\n          in: query\n          type: string\n          description: Filter entries by category.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: random\n      path: /random\n      operations:\n      - name: getrandomentry\n        method: GET\n        description: Random entry\n        inputParameters:\n        - name: title\n          in: query\n          type: string\n        - name: description\n          in: query\n          type: string\n        - name: auth\n  \
  \        in: query\n          type: string\n        - name: https\n          in: query\n          type: boolean\n        - name: cors\n          in: query\n          type: string\n        - name: category\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories\n      path: /categories\n      operations:\n      - name: listcategories\n        method: GET\n        description: List categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /health\n      operations:\n      - name: gethealth\n        method: GET\n        description: Health check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: public-apis-rest\n\
  \    description: REST adapter for Public APIs API.\n    resources:\n    - path: /entries\n      name: listentries\n      operations:\n      - method: GET\n        name: listentries\n        description: List entries\n        call: public-apis.listentries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /random\n      name: getrandomentry\n      operations:\n      - method: GET\n        name: getrandomentry\n        description: Random entry\n        call: public-apis.getrandomentry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories\n      name: listcategories\n      operations:\n      - method: GET\n        name: listcategories\n        description: List categories\n        call: public-apis.listcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /health\n      name: gethealth\n      operations:\n      - method: GET\n        name: gethealth\n        description:\
  \ Health check\n        call: public-apis.gethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: public-apis-mcp\n    transport: http\n    description: MCP adapter for Public APIs API for AI agent use.\n    tools:\n    - name: listentries\n      description: List entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: public-apis.listentries\n      with:\n        title: tools.title\n        description: tools.description\n        auth: tools.auth\n        https: tools.https\n        cors: tools.cors\n        category: tools.category\n      inputParameters:\n      - name: title\n        type: string\n        description: Filter entries whose title contains the provided value.\n      - name: description\n        type: string\n        description: Filter entries whose description contains the provided value.\n      - name: auth\n        type: string\n      \
  \  description: Filter entries by authentication type.\n      - name: https\n        type: boolean\n        description: Filter entries by HTTPS support.\n      - name: cors\n        type: string\n        description: Filter entries by CORS support.\n      - name: category\n        type: string\n        description: Filter entries by category.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrandomentry\n      description: Random entry\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: public-apis.getrandomentry\n      with:\n        title: tools.title\n        description: tools.description\n        auth: tools.auth\n        https: tools.https\n        cors: tools.cors\n        category: tools.category\n      inputParameters:\n      - name: title\n        type: string\n        description: title\n      - name: description\n        type: string\n        description: description\n      - name: auth\n\
  \        type: string\n        description: auth\n      - name: https\n        type: boolean\n        description: https\n      - name: cors\n        type: string\n        description: cors\n      - name: category\n        type: string\n        description: category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcategories\n      description: List categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: public-apis.listcategories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethealth\n      description: Health check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: public-apis.gethealth\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/public-apis/refs/heads/main/capabilities/public-apis-capability.yaml
tags:
- Public
- Apis
- API
tools:
- description: List entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listentries
- description: Random entry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrandomentry
- description: List categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcategories
- description: Health check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealth
---

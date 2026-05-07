---
categories: []
consumed_apis: []
description: The Lens API provides programmatic access to the full corpus of Lens scholarly works and patents using a REST interface. The API supports rich Elasticsearch-style query DSL for searching scholarly publications and global patent records, with cursor-based pagination, sorting, and field projection. Authentication is via a bearer token issued from the Lens user profile.
layout: capability
name: Lens API
operations:
- description: Search scholarly works (GET)
  method: GET
  name: get-scholarly-search
  path: /scholarly/search
- description: Search scholarly works (POST)
  method: POST
  name: post-scholarly-search
  path: /scholarly/search
- description: Get a scholarly work by Lens ID
  method: GET
  name: get-scholarly-lens-id
  path: /scholarly/{lens_id}
- description: Search patents (GET)
  method: GET
  name: get-patent-search
  path: /patent/search
- description: Search patents (POST)
  method: POST
  name: post-patent-search
  path: /patent/search
- description: Get a patent by Lens ID
  method: GET
  name: get-patent-lens-id
  path: /patent/{lens_id}
personas: []
provider_name: Lens
provider_slug: lens
search_terms:
- search scholarly works (get)
- search patents (post)
- get a scholarly work by lens id
- api
- search patents (get)
- post patent search
- science
- search scholarly works (post)
- research
- patents
- get scholarly lens id
- get a patent by lens id
- scholarly
- get patent search
- get patent lens id
- get scholarly search
- lens
- open data
- post scholarly search
slug: lens-capability
source_filename: lens-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Lens API\n  description: The Lens API provides programmatic access to the full corpus of Lens scholarly works and patents using a REST\n    interface. The API supports rich Elasticsearch-style query DSL for searching scholarly publications and global patent\n    records, with cursor-based pagination, sorting, and field projection. Authentication is via a bearer token issued from\n    the Lens user profile.\n  tags:\n  - Lens\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lens\n    baseUri: https://api.lens.org\n    description: Lens API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LENS_TOKEN}}'\n    resources:\n    - name: scholarly-search\n      path: /scholarly/search\n      operations:\n      - name: get-scholarly-search\n        method: GET\n        description: Search scholarly works (GET)\n        inputParameters:\n        - name: query\n\
  \          in: query\n          type: string\n          required: true\n          description: Lucene-style query string (e.g. \"title:graphene AND year:2024\").\n        - name: size\n          in: query\n          type: integer\n          description: Number of records per page (max 1000 for Patents/Scholarly subject to plan).\n        - name: from\n          in: query\n          type: integer\n          description: Offset for offset/size pagination. Cannot exceed 10000 in total.\n        - name: sort\n          in: query\n          type: string\n          description: Comma-separated sort directives (e.g. \"desc(patent_citation_count)\").\n        - name: include\n          in: query\n          type: string\n          description: Comma-separated list of fields to include in the response.\n        - name: exclude\n          in: query\n          type: string\n          description: Comma-separated list of fields to exclude from the response.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: post-scholarly-search\n        method: POST\n        description: Search scholarly works (POST)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scholarly-lens-id\n      path: /scholarly/{lens_id}\n      operations:\n      - name: get-scholarly-lens-id\n        method: GET\n        description: Get a scholarly work by Lens ID\n        inputParameters:\n        - name: lens_id\n          in: path\n          type: string\n          required: true\n          description: Unique Lens identifier for the scholarly work.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patent-search\n      path: /patent/search\n      operations:\n      - name: get-patent-search\n        method: GET\n        description: Search patents (GET)\n     \
  \   inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Lucene-style query string.\n        - name: size\n          in: query\n          type: integer\n        - name: from\n          in: query\n          type: integer\n        - name: sort\n          in: query\n          type: string\n        - name: include\n          in: query\n          type: string\n        - name: exclude\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-patent-search\n        method: POST\n        description: Search patents (POST)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patent-lens-id\n      path: /patent/{lens_id}\n      operations:\n      - name: get-patent-lens-id\n        method: GET\n  \
  \      description: Get a patent by Lens ID\n        inputParameters:\n        - name: lens_id\n          in: path\n          type: string\n          required: true\n          description: Unique Lens identifier for the patent record.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lens-rest\n    description: REST adapter for Lens API.\n    resources:\n    - path: /scholarly/search\n      name: get-scholarly-search\n      operations:\n      - method: GET\n        name: get-scholarly-search\n        description: Search scholarly works (GET)\n        call: lens.get-scholarly-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scholarly/search\n      name: post-scholarly-search\n      operations:\n      - method: POST\n        name: post-scholarly-search\n        description: Search scholarly works (POST)\n  \
  \      call: lens.post-scholarly-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scholarly/{lens_id}\n      name: get-scholarly-lens-id\n      operations:\n      - method: GET\n        name: get-scholarly-lens-id\n        description: Get a scholarly work by Lens ID\n        call: lens.get-scholarly-lens-id\n        with:\n          lens_id: rest.lens_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patent/search\n      name: get-patent-search\n      operations:\n      - method: GET\n        name: get-patent-search\n        description: Search patents (GET)\n        call: lens.get-patent-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patent/search\n      name: post-patent-search\n      operations:\n      - method: POST\n        name: post-patent-search\n        description: Search patents (POST)\n        call: lens.post-patent-search\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /patent/{lens_id}\n      name: get-patent-lens-id\n      operations:\n      - method: GET\n        name: get-patent-lens-id\n        description: Get a patent by Lens ID\n        call: lens.get-patent-lens-id\n        with:\n          lens_id: rest.lens_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: lens-mcp\n    transport: http\n    description: MCP adapter for Lens API for AI agent use.\n    tools:\n    - name: get-scholarly-search\n      description: Search scholarly works (GET)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lens.get-scholarly-search\n      with:\n        query: tools.query\n        size: tools.size\n        from: tools.from\n        sort: tools.sort\n        include: tools.include\n        exclude: tools.exclude\n      inputParameters:\n      - name: query\n        type: string\n\
  \        description: Lucene-style query string (e.g. \"title:graphene AND year:2024\").\n        required: true\n      - name: size\n        type: integer\n        description: Number of records per page (max 1000 for Patents/Scholarly subject to plan).\n      - name: from\n        type: integer\n        description: Offset for offset/size pagination. Cannot exceed 10000 in total.\n      - name: sort\n        type: string\n        description: Comma-separated sort directives (e.g. \"desc(patent_citation_count)\").\n      - name: include\n        type: string\n        description: Comma-separated list of fields to include in the response.\n      - name: exclude\n        type: string\n        description: Comma-separated list of fields to exclude from the response.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-scholarly-search\n      description: Search scholarly works (POST)\n      hints:\n        readOnly: false\n        destructive: false\n   \
  \     idempotent: false\n      call: lens.post-scholarly-search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-scholarly-lens-id\n      description: Get a scholarly work by Lens ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lens.get-scholarly-lens-id\n      with:\n        lens_id: tools.lens_id\n      inputParameters:\n      - name: lens_id\n        type: string\n        description: Unique Lens identifier for the scholarly work.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-patent-search\n      description: Search patents (GET)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lens.get-patent-search\n      with:\n        query: tools.query\n        size: tools.size\n        from: tools.from\n        sort: tools.sort\n        include: tools.include\n        exclude: tools.exclude\n\
  \      inputParameters:\n      - name: query\n        type: string\n        description: Lucene-style query string.\n        required: true\n      - name: size\n        type: integer\n        description: size\n      - name: from\n        type: integer\n        description: from\n      - name: sort\n        type: string\n        description: sort\n      - name: include\n        type: string\n        description: include\n      - name: exclude\n        type: string\n        description: exclude\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-patent-search\n      description: Search patents (POST)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lens.post-patent-search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-patent-lens-id\n      description: Get a patent by Lens ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: lens.get-patent-lens-id\n      with:\n        lens_id: tools.lens_id\n      inputParameters:\n      - name: lens_id\n        type: string\n        description: Unique Lens identifier for the patent record.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LENS_TOKEN: LENS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lens/refs/heads/main/capabilities/lens-capability.yaml
tags:
- Lens
- API
tools:
- description: Search scholarly works (GET)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-scholarly-search
- description: Search scholarly works (POST)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-scholarly-search
- description: Get a scholarly work by Lens ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-scholarly-lens-id
- description: Search patents (GET)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-patent-search
- description: Search patents (POST)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-patent-search
- description: Get a patent by Lens ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-patent-lens-id
---

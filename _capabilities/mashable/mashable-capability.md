---
categories: []
consumed_apis: []
description: Mashable content is accessible via the News API, a third-party REST API that provides live headlines, articles, images, and metadata from Mashable and over 150,000 other worldwide news sources. Use the source identifier "mashable" or domain "mashable.com" to retrieve content published by Mashable.
layout: capability
name: Mashable via News API
operations:
- description: Top headlines for Mashable
  method: GET
  name: getmashabletopheadlines
  path: /top-headlines
- description: Search Mashable articles
  method: GET
  name: searchmashablearticles
  path: /everything
personas: []
provider_name: Mashable
provider_slug: mashable
search_terms:
- articles
- headlines
- top headlines for mashable
- mashable
- search mashable articles
- getmashabletopheadlines
- searchmashablearticles
- digital culture
- api
- news
- technology news
- media
slug: mashable-capability
source_filename: mashable-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mashable via News API\n  description: Mashable content is accessible via the News API, a third-party REST API that provides live headlines, articles,\n    images, and metadata from Mashable and over 150,000 other worldwide news sources. Use the source identifier \"mashable\"\n    or domain \"mashable.com\" to retrieve content published by Mashable.\n  tags:\n  - Mashable\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mashable\n    baseUri: https://newsapi.org/v2\n    description: Mashable via News API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Api-Key\n      value: '{{MASHABLE_TOKEN}}'\n    resources:\n    - name: top-headlines\n      path: /top-headlines\n      operations:\n      - name: getmashabletopheadlines\n        method: GET\n        description: Top headlines for Mashable\n        inputParameters:\n        - name: sources\n\
  \          in: query\n          type: string\n          description: Pass \"mashable\" to limit headlines to Mashable.\n        - name: q\n          in: query\n          type: string\n          description: Keywords or phrase to search within Mashable headlines.\n        - name: pageSize\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: everything\n      path: /everything\n      operations:\n      - name: searchmashablearticles\n        method: GET\n        description: Search Mashable articles\n        inputParameters:\n        - name: sources\n          in: query\n          type: string\n          description: Pass \"mashable\" to scope to Mashable's News API source.\n        - name: domains\n          in: query\n          type: string\n          description: Pass \"mashable.com\" to\
  \ scope to Mashable's domain.\n        - name: q\n          in: query\n          type: string\n          description: Keywords or phrase to search.\n        - name: from\n          in: query\n          type: string\n        - name: to\n          in: query\n          type: string\n        - name: language\n          in: query\n          type: string\n        - name: sortBy\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mashable-rest\n    description: REST adapter for Mashable via News API.\n    resources:\n    - path: /top-headlines\n      name: getmashabletopheadlines\n      operations:\n      - method: GET\n        name: getmashabletopheadlines\n        description:\
  \ Top headlines for Mashable\n        call: mashable.getmashabletopheadlines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /everything\n      name: searchmashablearticles\n      operations:\n      - method: GET\n        name: searchmashablearticles\n        description: Search Mashable articles\n        call: mashable.searchmashablearticles\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mashable-mcp\n    transport: http\n    description: MCP adapter for Mashable via News API for AI agent use.\n    tools:\n    - name: getmashabletopheadlines\n      description: Top headlines for Mashable\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mashable.getmashabletopheadlines\n      with:\n        sources: tools.sources\n        q: tools.q\n        pageSize: tools.pageSize\n        page: tools.page\n      inputParameters:\n  \
  \    - name: sources\n        type: string\n        description: Pass \"mashable\" to limit headlines to Mashable.\n      - name: q\n        type: string\n        description: Keywords or phrase to search within Mashable headlines.\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: page\n        type: integer\n        description: page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchmashablearticles\n      description: Search Mashable articles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mashable.searchmashablearticles\n      with:\n        sources: tools.sources\n        domains: tools.domains\n        q: tools.q\n        from: tools.from\n        to: tools.to\n        language: tools.language\n        sortBy: tools.sortBy\n        pageSize: tools.pageSize\n        page: tools.page\n      inputParameters:\n      - name: sources\n        type: string\n\
  \        description: Pass \"mashable\" to scope to Mashable's News API source.\n      - name: domains\n        type: string\n        description: Pass \"mashable.com\" to scope to Mashable's domain.\n      - name: q\n        type: string\n        description: Keywords or phrase to search.\n      - name: from\n        type: string\n        description: from\n      - name: to\n        type: string\n        description: to\n      - name: language\n        type: string\n        description: language\n      - name: sortBy\n        type: string\n        description: sortBy\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: page\n        type: integer\n        description: page\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MASHABLE_TOKEN: MASHABLE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mashable/refs/heads/main/capabilities/mashable-capability.yaml
tags:
- Mashable
- API
tools:
- description: Top headlines for Mashable
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmashabletopheadlines
- description: Search Mashable articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchmashablearticles
---

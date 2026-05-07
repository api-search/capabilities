---
categories: []
consumed_apis: []
description: The Google Fonts Developer API provides programmatic access to the metadata for all font families served by Google Fonts. It allows applications to query for available font families, retrieve details about variants, subsets, categories, and file URLs, and supports filtering, sorting, and variable font metadata.
layout: capability
name: Google Fonts Developer API
operations:
- description: Google Fonts Developer List Web Fonts
  method: GET
  name: listwebfonts
  path: /webfonts/v1/webfonts
personas: []
provider_name: Google Fonts Developer
provider_slug: google-fonts
search_terms:
- fonts
- google fonts
- web fonts
- google
- design
- google fonts developer list web fonts
- api
- typography
- css
- listwebfonts
slug: google-fonts-capability
source_filename: google-fonts-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Fonts Developer API\n  description: The Google Fonts Developer API provides programmatic access to the metadata for all font families served by\n    Google Fonts. It allows applications to query for available font families, retrieve details about variants, subsets, categories,\n    and file URLs, and supports filtering, sorting, and variable font metadata.\n  tags:\n  - Google\n  - Fonts\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-fonts\n    baseUri: https://www.googleapis.com\n    description: Google Fonts Developer API HTTP API.\n    resources:\n    - name: webfonts-v1-webfonts\n      path: /webfonts/v1/webfonts\n      operations:\n      - name: listwebfonts\n        method: GET\n        description: Google Fonts Developer List Web Fonts\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required:\
  \ true\n          description: API key for authentication\n        - name: sort\n          in: query\n          type: string\n          description: Sort order for the font list.\n        - name: family\n          in: query\n          type: string\n          description: Filter by font family name.\n        - name: subset\n          in: query\n          type: string\n          description: Filter by character subset (e.g., latin, greek, cyrillic).\n        - name: category\n          in: query\n          type: string\n          description: Filter by font category.\n        - name: capability\n          in: query\n          type: string\n          description: Request additional capabilities like WOFF2, variable fonts (VF), or family tags.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-fonts-rest\n    description: REST adapter for Google Fonts\
  \ Developer API.\n    resources:\n    - path: /webfonts/v1/webfonts\n      name: listwebfonts\n      operations:\n      - method: GET\n        name: listwebfonts\n        description: Google Fonts Developer List Web Fonts\n        call: google-fonts.listwebfonts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-fonts-mcp\n    transport: http\n    description: MCP adapter for Google Fonts Developer API for AI agent use.\n    tools:\n    - name: listwebfonts\n      description: Google Fonts Developer List Web Fonts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-fonts.listwebfonts\n      with:\n        key: tools.key\n        sort: tools.sort\n        family: tools.family\n        subset: tools.subset\n        category: tools.category\n        capability: tools.capability\n      inputParameters:\n      - name: key\n        type: string\n        description:\
  \ API key for authentication\n        required: true\n      - name: sort\n        type: string\n        description: Sort order for the font list.\n      - name: family\n        type: string\n        description: Filter by font family name.\n      - name: subset\n        type: string\n        description: Filter by character subset (e.g., latin, greek, cyrillic).\n      - name: category\n        type: string\n        description: Filter by font category.\n      - name: capability\n        type: string\n        description: Request additional capabilities like WOFF2, variable fonts (VF), or family tags.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-fonts/refs/heads/main/capabilities/google-fonts-capability.yaml
tags:
- Google
- Fonts
- API
tools:
- description: Google Fonts Developer List Web Fonts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwebfonts
---

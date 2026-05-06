---
categories: []
consumed_apis: []
description: Predict the age of a person based on their first name. Returns estimated age, prediction confidence (count), and supports country localization and batch requests of up to 10 names. Generated from documentation.
layout: capability
name: Agify.io API
operations:
- description: Agify.io Predict Age from Name
  method: GET
  name: predictage
  path: /
personas: []
provider_name: Agify.io
provider_slug: agify-io
search_terms:
- demographics
- name analysis
- agify.io predict age from name
- api
- io
- age prediction
- rest api
- predictage
- Developer
- agify
- statistical analysis and prediction of demographic attributes from personal data
- developers integrating age prediction into applications for demographic analysis or personalization
- predict the age of a person based on their first name, optionally localized by country
slug: agify-io-capability
source_filename: agify-io-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Agify.io API\n  description: Predict the age of a person based on their first name. Returns estimated age, prediction confidence (count),\n    and supports country localization and batch requests of up to 10 names. Generated from documentation.\n  tags:\n  - Agify\n  - Io\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: agify-io\n    baseUri: https://api.agify.io\n    description: Agify.io API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: predictage\n        method: GET\n        description: Agify.io Predict Age from Name\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: First name to predict age for. For batch requests use name[] array syntax.\n        - name: country_id\n          in: query\n          type: string\n          description: ISO 3166-1 alpha-2\
  \ country code for country-localized age prediction.\n        - name: apikey\n          in: query\n          type: string\n          description: API key for authenticated requests beyond the free tier (100 req/day).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: agify-io-rest\n    description: REST adapter for Agify.io API.\n    resources:\n    - path: /\n      name: predictage\n      operations:\n      - method: GET\n        name: predictage\n        description: Agify.io Predict Age from Name\n        call: agify-io.predictage\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: agify-io-mcp\n    transport: http\n    description: MCP adapter for Agify.io API for AI agent use.\n    tools:\n    - name: predictage\n      description: Agify.io Predict Age from Name\n      hints:\n \
  \       readOnly: true\n        destructive: false\n        idempotent: true\n      call: agify-io.predictage\n      with:\n        name: tools.name\n        country_id: tools.country_id\n        apikey: tools.apikey\n      inputParameters:\n      - name: name\n        type: string\n        description: First name to predict age for. For batch requests use name[] array syntax.\n      - name: country_id\n        type: string\n        description: ISO 3166-1 alpha-2 country code for country-localized age prediction.\n      - name: apikey\n        type: string\n        description: API key for authenticated requests beyond the free tier (100 req/day).\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/agify-io/refs/heads/main/capabilities/agify-io-capability.yaml
tags:
- Agify
- Io
- API
tools:
- description: Agify.io Predict Age from Name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: predictage
---

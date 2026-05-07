---
categories: []
consumed_apis: []
description: The FBI Most Wanted API is designed to help developers easily get information on the FBI Wanted program, including Ten Most Wanted Fugitives, Most Wanted Terrorists, kidnappings and missing persons, and seeking information cases.
layout: capability
name: FBI Most Wanted
operations:
- description: Federal Bureau of Investigation Retrieve list of FBI wanted individuals
  method: GET
  name: get-list
  path: /list
personas: []
provider_name: Federal Bureau of Investigation
provider_slug: federal-bureau-of-investigation
search_terms:
- fbi
- investigation
- bureau
- federal
- of
- get list
- federal government
- federal bureau of investigation retrieve list of fbi wanted individuals
- api
slug: federal-bureau-of-investigation-capability
source_filename: federal-bureau-of-investigation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FBI Most Wanted\n  description: The FBI Most Wanted API is designed to help developers easily get information on the FBI Wanted program, including\n    Ten Most Wanted Fugitives, Most Wanted Terrorists, kidnappings and missing persons, and seeking information cases.\n  tags:\n  - Federal\n  - Bureau\n  - Of\n  - Investigation\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: federal-bureau-of-investigation\n    baseUri: https://api.fbi.gov/wanted/v1\n    description: FBI Most Wanted HTTP API.\n    resources:\n    - name: list\n      path: /list\n      operations:\n      - name: get-list\n        method: GET\n        description: Federal Bureau of Investigation Retrieve list of FBI wanted individuals\n        inputParameters:\n        - name: field_offices\n          in: query\n          type: string\n          description: Filter by specific FBI field offices (e.g., miami,\
  \ new-york, los-angeles).\n        - name: page\n          in: query\n          type: integer\n          description: Specifies the page of results to return (used for pagination).\n        - name: sort_on\n          in: query\n          type: string\n          description: Specifies the field to sort results by (e.g., title, reward, etc.).\n        - name: sort_order\n          in: query\n          type: string\n          description: Specifies the order of the sorting (asc or desc).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: federal-bureau-of-investigation-rest\n    description: REST adapter for FBI Most Wanted.\n    resources:\n    - path: /list\n      name: get-list\n      operations:\n      - method: GET\n        name: get-list\n        description: Federal Bureau of Investigation Retrieve list of FBI wanted individuals\n        call: federal-bureau-of-investigation.get-list\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: federal-bureau-of-investigation-mcp\n    transport: http\n    description: MCP adapter for FBI Most Wanted for AI agent use.\n    tools:\n    - name: get-list\n      description: Federal Bureau of Investigation Retrieve list of FBI wanted individuals\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-bureau-of-investigation.get-list\n      with:\n        field_offices: tools.field_offices\n        page: tools.page\n        sort_on: tools.sort_on\n        sort_order: tools.sort_order\n      inputParameters:\n      - name: field_offices\n        type: string\n        description: Filter by specific FBI field offices (e.g., miami, new-york, los-angeles).\n      - name: page\n        type: integer\n        description: Specifies the page of results to return (used for pagination).\n      - name: sort_on\n    \
  \    type: string\n        description: Specifies the field to sort results by (e.g., title, reward, etc.).\n      - name: sort_order\n        type: string\n        description: Specifies the order of the sorting (asc or desc).\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/federal-bureau-of-investigation/refs/heads/main/capabilities/federal-bureau-of-investigation-capability.yaml
tags:
- Federal
- Bureau
- Of
- Investigation
- API
tools:
- description: Federal Bureau of Investigation Retrieve list of FBI wanted individuals
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-list
---

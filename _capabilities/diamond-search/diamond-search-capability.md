---
categories: []
consumed_apis: []
description: API for retrieving data report 3 in CSV format.
layout: capability
name: Diamond Search IDEX Data API - Report 3
operations:
- description: Diamond Search Retrieve Report 3 Data
  method: POST
  name: post-getreport3
  path: /getreport3
personas: []
provider_name: Diamond Search
provider_slug: diamond-search
search_terms:
- trading
- diamond
- pricing
- diamond search retrieve report 3 data
- api
- lab grown
- search
- diamonds
- post getreport3
slug: diamond-search-capability
source_filename: diamond-search-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Diamond Search IDEX Data API - Report 3\n  description: API for retrieving data report 3 in CSV format.\n  tags:\n  - Diamond\n  - Search\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: diamond-search\n    baseUri: https://api.idexonline.com/idexdataapi/api\n    description: Diamond Search IDEX Data API - Report 3 HTTP API.\n    resources:\n    - name: getreport3\n      path: /getreport3\n      operations:\n      - name: post-getreport3\n        method: POST\n        description: Diamond Search Retrieve Report 3 Data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: diamond-search-rest\n    description: REST adapter for Diamond Search IDEX Data API - Report 3.\n    resources:\n    - path: /getreport3\n      name: post-getreport3\n \
  \     operations:\n      - method: POST\n        name: post-getreport3\n        description: Diamond Search Retrieve Report 3 Data\n        call: diamond-search.post-getreport3\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: diamond-search-mcp\n    transport: http\n    description: MCP adapter for Diamond Search IDEX Data API - Report 3 for AI agent use.\n    tools:\n    - name: post-getreport3\n      description: Diamond Search Retrieve Report 3 Data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: diamond-search.post-getreport3\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/diamond-search/refs/heads/main/capabilities/diamond-search-capability.yaml
tags:
- Diamond
- Search
- API
tools:
- description: Diamond Search Retrieve Report 3 Data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-getreport3
---

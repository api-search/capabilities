---
categories: []
consumed_apis: []
description: The data API provides programmatic access to BEA published economic statistics using industry-standard methods and procedures. BEA's data API includes methods for retrieving a subset of our statistical data and the meta-data that describes it. The data API and its documentation are for programmers who are familiar with the concepts and techniques of retrieving data from Web Services.
layout: capability
name: Bureau of Economic Analysis (BEA) API
operations:
- description: Bureau of Economic Analysis Retrieve data from BEA API
  method: GET
  name: get
  path: /
personas: []
provider_name: Bureau of Economic Analysis
provider_slug: bureau-of-economic-analysis
search_terms:
- economics
- gdp
- federal government
- trade
- get
- api
- analysis
- bureau
- bureau of economic analysis retrieve data from bea api
- economic
- national accounts
- of
- statistics
slug: bureau-of-economic-analysis-capability
source_filename: bureau-of-economic-analysis-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bureau of Economic Analysis (BEA) API\n  description: The data API provides programmatic access to BEA published economic statistics using industry-standard methods\n    and procedures. BEA's data API includes methods for retrieving a subset of our statistical data and the meta-data that\n    describes it. The data API and its documentation are for programmers who are familiar with the concepts and techniques\n    of retrieving data from Web Services.\n  tags:\n  - Bureau\n  - Of\n  - Economic\n  - Analysis\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bureau-of-economic-analysis\n    baseUri: https://apps.bea.gov/api/data\n    description: Bureau of Economic Analysis (BEA) API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: get\n        method: GET\n        description: Bureau of Economic Analysis Retrieve data from\
  \ BEA API\n        inputParameters:\n        - name: UserID\n          in: query\n          type: string\n          required: true\n        - name: method\n          in: query\n          type: string\n          required: true\n        - name: DatasetName\n          in: query\n          type: string\n        - name: ParameterName\n          in: query\n          type: string\n        - name: ResultFormat\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bureau-of-economic-analysis-rest\n    description: REST adapter for Bureau of Economic Analysis (BEA) API.\n    resources:\n    - path: /\n      name: get\n      operations:\n      - method: GET\n        name: get\n        description: Bureau of Economic Analysis Retrieve data from BEA API\n        call: bureau-of-economic-analysis.get\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bureau-of-economic-analysis-mcp\n    transport: http\n    description: MCP adapter for Bureau of Economic Analysis (BEA) API for AI agent use.\n    tools:\n    - name: get\n      description: Bureau of Economic Analysis Retrieve data from BEA API\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bureau-of-economic-analysis.get\n      with:\n        UserID: tools.UserID\n        method: tools.method\n        DatasetName: tools.DatasetName\n        ParameterName: tools.ParameterName\n        ResultFormat: tools.ResultFormat\n      inputParameters:\n      - name: UserID\n        type: string\n        description: UserID\n        required: true\n      - name: method\n        type: string\n        description: method\n        required: true\n      - name: DatasetName\n        type: string\n        description: DatasetName\n      - name: ParameterName\n\
  \        type: string\n        description: ParameterName\n      - name: ResultFormat\n        type: string\n        description: ResultFormat\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bureau-of-economic-analysis/refs/heads/main/capabilities/bureau-of-economic-analysis-capability.yaml
tags:
- Bureau
- Of
- Economic
- Analysis
- API
tools:
- description: Bureau of Economic Analysis Retrieve data from BEA API
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
---

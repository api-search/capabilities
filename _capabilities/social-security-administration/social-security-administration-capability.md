---
categories: []
consumed_apis: []
description: The Social Security Administration Field Office Address API provides location data, addresses, telephone numbers, and office hours for SSA Field Offices across the United States. The data is served through the Esri ArcGIS Online platform as a RESTful Feature Service. No authentication required — all data is publicly available.
layout: capability
name: SSA Field Office Address API
operations:
- description: Query Field Offices
  method: GET
  name: queryfieldoffices
  path: /1/query
personas: []
provider_name: Social Security Administration
provider_slug: social-security-administration
search_terms:
- government api
- social
- queryfieldoffices
- social security
- query field offices
- federal government
- security
- api
- open data
- disability benefits
- oasdi
- retirement benefits
- administration
slug: social-security-administration-capability
source_filename: social-security-administration-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SSA Field Office Address API\n  description: The Social Security Administration Field Office Address API provides location data, addresses, telephone numbers,\n    and office hours for SSA Field Offices across the United States. The data is served through the Esri ArcGIS Online platform\n    as a RESTful Feature Service. No authentication required — all data is publicly available.\n  tags:\n  - Social\n  - Security\n  - Administration\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: social-security-administration\n    baseUri: https://services6.arcgis.com/zFiipv75rloRP5N4/ArcGIS/rest/services/Office_Points/FeatureServer\n    description: SSA Field Office Address API HTTP API.\n    resources:\n    - name: 1-query\n      path: /1/query\n      operations:\n      - name: queryfieldoffices\n        method: GET\n        description: Query Field Offices\n        inputParameters:\n\
  \        - name: where\n          in: query\n          type: string\n          required: true\n          description: SQL WHERE clause to filter records (use '1=1' for all records)\n        - name: outFields\n          in: query\n          type: string\n          description: Comma-separated list of fields to return, or * for all fields\n        - name: f\n          in: query\n          type: string\n          description: Response format\n        - name: resultOffset\n          in: query\n          type: integer\n          description: Offset for pagination\n        - name: resultRecordCount\n          in: query\n          type: integer\n          description: Maximum number of records to return\n        - name: orderByFields\n          in: query\n          type: string\n          description: Fields to sort results by\n        - name: geometry\n          in: query\n          type: string\n          description: Spatial filter geometry (JSON)\n        - name: geometryType\n          in:\
  \ query\n          type: string\n          description: Type of spatial geometry filter\n        - name: inSR\n          in: query\n          type: integer\n          description: Spatial reference of input geometry\n        - name: spatialRel\n          in: query\n          type: string\n          description: Spatial relationship for filtering\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: social-security-administration-rest\n    description: REST adapter for SSA Field Office Address API.\n    resources:\n    - path: /1/query\n      name: queryfieldoffices\n      operations:\n      - method: GET\n        name: queryfieldoffices\n        description: Query Field Offices\n        call: social-security-administration.queryfieldoffices\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace:\
  \ social-security-administration-mcp\n    transport: http\n    description: MCP adapter for SSA Field Office Address API for AI agent use.\n    tools:\n    - name: queryfieldoffices\n      description: Query Field Offices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: social-security-administration.queryfieldoffices\n      with:\n        where: tools.where\n        outFields: tools.outFields\n        f: tools.f\n        resultOffset: tools.resultOffset\n        resultRecordCount: tools.resultRecordCount\n        orderByFields: tools.orderByFields\n        geometry: tools.geometry\n        geometryType: tools.geometryType\n        inSR: tools.inSR\n        spatialRel: tools.spatialRel\n      inputParameters:\n      - name: where\n        type: string\n        description: SQL WHERE clause to filter records (use '1=1' for all records)\n        required: true\n      - name: outFields\n        type: string\n        description: Comma-separated\
  \ list of fields to return, or * for all fields\n      - name: f\n        type: string\n        description: Response format\n      - name: resultOffset\n        type: integer\n        description: Offset for pagination\n      - name: resultRecordCount\n        type: integer\n        description: Maximum number of records to return\n      - name: orderByFields\n        type: string\n        description: Fields to sort results by\n      - name: geometry\n        type: string\n        description: Spatial filter geometry (JSON)\n      - name: geometryType\n        type: string\n        description: Type of spatial geometry filter\n      - name: inSR\n        type: integer\n        description: Spatial reference of input geometry\n      - name: spatialRel\n        type: string\n        description: Spatial relationship for filtering\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/social-security-administration/refs/heads/main/capabilities/social-security-administration-capability.yaml
tags:
- Social
- Security
- Administration
- API
tools:
- description: Query Field Offices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: queryfieldoffices
---

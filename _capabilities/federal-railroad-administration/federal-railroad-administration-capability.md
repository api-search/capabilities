---
categories: []
consumed_apis: []
description: The FRA Public API provides access to railroad safety datasets including accidents, incidents, highway-rail grade crossings, inspections, and operational data published through the FRA Office of Safety Analysis.
layout: capability
name: Federal Railroad Administration Public API
operations:
- description: Retrieve railroad accident records
  method: GET
  name: listaccidents
  path: /accidents
- description: Retrieve railroad incident records
  method: GET
  name: listincidents
  path: /incidents
- description: Retrieve highway-rail grade crossing inventory
  method: GET
  name: listcrossings
  path: /crossings
- description: Retrieve FRA inspection records
  method: GET
  name: listinspections
  path: /inspections
- description: Retrieve railroad operational data
  method: GET
  name: listoperationaldata
  path: /operational-data
personas: []
provider_name: Federal Railroad Administration
provider_slug: federal-railroad-administration
search_terms:
- retrieve railroad incident records
- listinspections
- transportation
- listoperationaldata
- safety
- retrieve highway-rail grade crossing inventory
- federal
- retrieve railroad operational data
- retrieve railroad accident records
- listincidents
- railroads
- federal government
- listaccidents
- api
- listcrossings
- railroad
- retrieve fra inspection records
- administration
slug: federal-railroad-administration-capability
source_filename: federal-railroad-administration-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Federal Railroad Administration Public API\n  description: The FRA Public API provides access to railroad safety datasets including accidents, incidents, highway-rail\n    grade crossings, inspections, and operational data published through the FRA Office of Safety Analysis.\n  tags:\n  - Federal\n  - Railroad\n  - Administration\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: federal-railroad-administration\n    baseUri: https://safetydata.fra.dot.gov/MasterWebService/publicapi\n    description: Federal Railroad Administration Public API HTTP API.\n    resources:\n    - name: accidents\n      path: /accidents\n      operations:\n      - name: listaccidents\n        method: GET\n        description: Retrieve railroad accident records\n        inputParameters:\n        - name: year\n          in: query\n          type: integer\n        - name: railroad\n          in:\
  \ query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incidents\n      path: /incidents\n      operations:\n      - name: listincidents\n        method: GET\n        description: Retrieve railroad incident records\n        inputParameters:\n        - name: year\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crossings\n      path: /crossings\n      operations:\n      - name: listcrossings\n        method: GET\n        description: Retrieve highway-rail grade crossing inventory\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inspections\n      path: /inspections\n\
  \      operations:\n      - name: listinspections\n        method: GET\n        description: Retrieve FRA inspection records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operational-data\n      path: /operational-data\n      operations:\n      - name: listoperationaldata\n        method: GET\n        description: Retrieve railroad operational data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: federal-railroad-administration-rest\n    description: REST adapter for Federal Railroad Administration Public API.\n    resources:\n    - path: /accidents\n      name: listaccidents\n      operations:\n      - method: GET\n        name: listaccidents\n        description: Retrieve railroad accident records\n        call: federal-railroad-administration.listaccidents\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /incidents\n      name: listincidents\n      operations:\n      - method: GET\n        name: listincidents\n        description: Retrieve railroad incident records\n        call: federal-railroad-administration.listincidents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /crossings\n      name: listcrossings\n      operations:\n      - method: GET\n        name: listcrossings\n        description: Retrieve highway-rail grade crossing inventory\n        call: federal-railroad-administration.listcrossings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inspections\n      name: listinspections\n      operations:\n      - method: GET\n        name: listinspections\n        description: Retrieve FRA inspection records\n        call: federal-railroad-administration.listinspections\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /operational-data\n      name: listoperationaldata\n      operations:\n      - method: GET\n        name: listoperationaldata\n        description: Retrieve railroad operational data\n        call: federal-railroad-administration.listoperationaldata\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: federal-railroad-administration-mcp\n    transport: http\n    description: MCP adapter for Federal Railroad Administration Public API for AI agent use.\n    tools:\n    - name: listaccidents\n      description: Retrieve railroad accident records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-railroad-administration.listaccidents\n      with:\n        year: tools.year\n        railroad: tools.railroad\n      inputParameters:\n      - name: year\n        type: integer\n        description: year\n      - name: railroad\n   \
  \     type: string\n        description: railroad\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listincidents\n      description: Retrieve railroad incident records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-railroad-administration.listincidents\n      with:\n        year: tools.year\n      inputParameters:\n      - name: year\n        type: integer\n        description: year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcrossings\n      description: Retrieve highway-rail grade crossing inventory\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-railroad-administration.listcrossings\n      with:\n        state: tools.state\n      inputParameters:\n      - name: state\n        type: string\n        description: state\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: listinspections\n      description: Retrieve FRA inspection records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-railroad-administration.listinspections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listoperationaldata\n      description: Retrieve railroad operational data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-railroad-administration.listoperationaldata\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/federal-railroad-administration/refs/heads/main/capabilities/federal-railroad-administration-capability.yaml
tags:
- Federal
- Railroad
- Administration
- API
tools:
- description: Retrieve railroad accident records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccidents
- description: Retrieve railroad incident records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listincidents
- description: Retrieve highway-rail grade crossing inventory
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcrossings
- description: Retrieve FRA inspection records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinspections
- description: Retrieve railroad operational data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoperationaldata
---

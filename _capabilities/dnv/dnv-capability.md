---
categories: []
consumed_apis: []
description: DNV's Class Status API provides programmatic access to vessel classification data. Authentication uses OAuth 2.0 with Azure AD B2C as the identity provider. Access tokens are obtained from the Microsoft identity platform and are valid for approximately 20 minutes. Access requires a separate API contract with DNV. The API supports retry logic using exponential backoff for resilience.
layout: capability
name: DNV Class Status API
operations:
- description: Search vessels by classification criteria
  method: GET
  name: searchvessels
  path: /vessels
- description: Get vessel classification details
  method: GET
  name: getvessel
  path: /vessels/{imoNumber}
- description: Get vessel classification certificates
  method: GET
  name: getvesselcertificates
  path: /vessels/{imoNumber}/certificates
- description: Get vessel survey records and schedule
  method: GET
  name: getvesselsurveys
  path: /vessels/{imoNumber}/surveys
- description: Get fleet classification status
  method: GET
  name: getfleetstatus
  path: /fleets
personas: []
provider_name: DNV
provider_slug: dnv
search_terms:
- getfleetstatus
- getvessel
- searchvessels
- get vessel classification details
- getvesselcertificates
- maritime
- api
- dnv
- classification
- get vessel survey records and schedule
- vessel
- getvesselsurveys
- energy
- data platform
- get vessel classification certificates
- get fleet classification status
- search vessels by classification criteria
slug: dnv-capability
source_filename: dnv-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: DNV Class Status API\n  description: DNV's Class Status API provides programmatic access to vessel classification data. Authentication uses OAuth\n    2.0 with Azure AD B2C as the identity provider. Access tokens are obtained from the Microsoft identity platform and are\n    valid for approximately 20 minutes. Access requires a separate API contract with DNV. The API supports retry logic using\n    exponential backoff for resilience.\n  tags:\n  - Dnv\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: dnv\n    baseUri: https://maritime.dnv.com/api/cs-iacs-customer\n    description: DNV Class Status API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{DNV_TOKEN}}'\n    resources:\n    - name: vessels\n      path: /vessels\n      operations:\n      - name: searchvessels\n        method: GET\n        description: Search vessels by classification criteria\n\
  \        inputParameters:\n        - name: imoNumber\n          in: query\n          type: string\n          description: IMO vessel identification number (7 digits)\n        - name: vesselName\n          in: query\n          type: string\n          description: Vessel name (partial match supported)\n        - name: flagState\n          in: query\n          type: string\n          description: ISO 3166-1 alpha-2 country code for flag state\n        - name: shipType\n          in: query\n          type: string\n          description: DNV ship type classification code\n        - name: classStatus\n          in: query\n          type: string\n          description: Current class status filter\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessels-imonumber\n  \
  \    path: /vessels/{imoNumber}\n      operations:\n      - name: getvessel\n        method: GET\n        description: Get vessel classification details\n        inputParameters:\n        - name: imoNumber\n          in: path\n          type: string\n          required: true\n          description: IMO vessel identification number (7 digits)\n        - name: Accept\n          in: header\n          type: string\n          description: Response format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessels-imonumber-certificates\n      path: /vessels/{imoNumber}/certificates\n      operations:\n      - name: getvesselcertificates\n        method: GET\n        description: Get vessel classification certificates\n        inputParameters:\n        - name: imoNumber\n          in: path\n          type: string\n          required: true\n        - name: certificateType\n          in: query\n          type:\
  \ string\n          description: Filter by certificate type\n        - name: status\n          in: query\n          type: string\n          description: Filter by certificate validity status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessels-imonumber-surveys\n      path: /vessels/{imoNumber}/surveys\n      operations:\n      - name: getvesselsurveys\n        method: GET\n        description: Get vessel survey records and schedule\n        inputParameters:\n        - name: imoNumber\n          in: path\n          type: string\n          required: true\n        - name: surveyType\n          in: query\n          type: string\n          description: Filter by survey type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fleets\n      path: /fleets\n      operations:\n      - name: getfleetstatus\n       \
  \ method: GET\n        description: Get fleet classification status\n        inputParameters:\n        - name: imoNumbers\n          in: query\n          type: string\n          description: Comma-separated list of IMO numbers (max 100)\n        - name: includeExpiredCerts\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: dnv-rest\n    description: REST adapter for DNV Class Status API.\n    resources:\n    - path: /vessels\n      name: searchvessels\n      operations:\n      - method: GET\n        name: searchvessels\n        description: Search vessels by classification criteria\n        call: dnv.searchvessels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vessels/{imoNumber}\n      name: getvessel\n      operations:\n      - method: GET\n        name: getvessel\n\
  \        description: Get vessel classification details\n        call: dnv.getvessel\n        with:\n          imoNumber: rest.imoNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vessels/{imoNumber}/certificates\n      name: getvesselcertificates\n      operations:\n      - method: GET\n        name: getvesselcertificates\n        description: Get vessel classification certificates\n        call: dnv.getvesselcertificates\n        with:\n          imoNumber: rest.imoNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vessels/{imoNumber}/surveys\n      name: getvesselsurveys\n      operations:\n      - method: GET\n        name: getvesselsurveys\n        description: Get vessel survey records and schedule\n        call: dnv.getvesselsurveys\n        with:\n          imoNumber: rest.imoNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fleets\n      name: getfleetstatus\n\
  \      operations:\n      - method: GET\n        name: getfleetstatus\n        description: Get fleet classification status\n        call: dnv.getfleetstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: dnv-mcp\n    transport: http\n    description: MCP adapter for DNV Class Status API for AI agent use.\n    tools:\n    - name: searchvessels\n      description: Search vessels by classification criteria\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dnv.searchvessels\n      with:\n        imoNumber: tools.imoNumber\n        vesselName: tools.vesselName\n        flagState: tools.flagState\n        shipType: tools.shipType\n        classStatus: tools.classStatus\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: imoNumber\n        type: string\n        description: IMO vessel identification number (7 digits)\n \
  \     - name: vesselName\n        type: string\n        description: Vessel name (partial match supported)\n      - name: flagState\n        type: string\n        description: ISO 3166-1 alpha-2 country code for flag state\n      - name: shipType\n        type: string\n        description: DNV ship type classification code\n      - name: classStatus\n        type: string\n        description: Current class status filter\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvessel\n      description: Get vessel classification details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dnv.getvessel\n      with:\n        imoNumber: tools.imoNumber\n      inputParameters:\n      - name: imoNumber\n        type: string\n        description: IMO vessel identification\
  \ number (7 digits)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvesselcertificates\n      description: Get vessel classification certificates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dnv.getvesselcertificates\n      with:\n        imoNumber: tools.imoNumber\n        certificateType: tools.certificateType\n        status: tools.status\n      inputParameters:\n      - name: imoNumber\n        type: string\n        description: imoNumber\n        required: true\n      - name: certificateType\n        type: string\n        description: Filter by certificate type\n      - name: status\n        type: string\n        description: Filter by certificate validity status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvesselsurveys\n      description: Get vessel survey records and schedule\n      hints:\n        readOnly: true\n      \
  \  destructive: false\n        idempotent: true\n      call: dnv.getvesselsurveys\n      with:\n        imoNumber: tools.imoNumber\n        surveyType: tools.surveyType\n      inputParameters:\n      - name: imoNumber\n        type: string\n        description: imoNumber\n        required: true\n      - name: surveyType\n        type: string\n        description: Filter by survey type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfleetstatus\n      description: Get fleet classification status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dnv.getfleetstatus\n      with:\n        imoNumbers: tools.imoNumbers\n        includeExpiredCerts: tools.includeExpiredCerts\n      inputParameters:\n      - name: imoNumbers\n        type: string\n        description: Comma-separated list of IMO numbers (max 100)\n      - name: includeExpiredCerts\n        type: boolean\n        description: includeExpiredCerts\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DNV_TOKEN: DNV_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/dnv/refs/heads/main/capabilities/dnv-capability.yaml
tags:
- Dnv
- API
tools:
- description: Search vessels by classification criteria
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchvessels
- description: Get vessel classification details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvessel
- description: Get vessel classification certificates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvesselcertificates
- description: Get vessel survey records and schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvesselsurveys
- description: Get fleet classification status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfleetstatus
---

---
categories: []
consumed_apis: []
description: The FMCSA QCMobile API provides access to commercial motor carrier safety data including carriers, vehicles, drivers, inspections, and crashes. Authentication uses a WebKey passed as a query parameter on each request.
layout: capability
name: Federal Motor Carrier Safety Administration QCMobile API
operations:
- description: Get carrier by DOT number
  method: GET
  name: getcarrierbydotnumber
  path: /carriers/{dotNumber}
- description: Search carriers by name
  method: GET
  name: searchcarriersbyname
  path: /carriers/name/{name}
- description: Get cargo carried for a carrier
  method: GET
  name: getcarriercargocarried
  path: /carriers/{dotNumber}/cargo-carried
- description: Get operation classification for a carrier
  method: GET
  name: getcarrieroperationclassification
  path: /carriers/{dotNumber}/operation-classification
- description: Get out-of-service info for a carrier
  method: GET
  name: getcarrieroos
  path: /carriers/{dotNumber}/oos
- description: Get docket numbers for a carrier
  method: GET
  name: getcarrierdocketnumbers
  path: /carriers/{dotNumber}/docket-numbers
- description: Get carrier authority
  method: GET
  name: getcarrierauthority
  path: /carriers/{dotNumber}/authority
personas: []
provider_name: Federal Motor Carrier Safety Administration
provider_slug: federal-motor-carrier-safety-administration
search_terms:
- carrier
- getcarrierdocketnumbers
- get operation classification for a carrier
- getcarrieroos
- motor
- get carrier authority
- get out-of-service info for a carrier
- searchcarriersbyname
- transportation
- get cargo carried for a carrier
- api
- getcarrierauthority
- getcarriercargocarried
- administration
- safety
- getcarrierbydotnumber
- federal government
- get carrier by dot number
- getcarrieroperationclassification
- get docket numbers for a carrier
- federal
- search carriers by name
slug: federal-motor-carrier-safety-administration-capability
source_filename: federal-motor-carrier-safety-administration-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Federal Motor Carrier Safety Administration QCMobile API\n  description: The FMCSA QCMobile API provides access to commercial motor carrier safety data including carriers, vehicles,\n    drivers, inspections, and crashes. Authentication uses a WebKey passed as a query parameter on each request.\n  tags:\n  - Federal\n  - Motor\n  - Carrier\n  - Safety\n  - Administration\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: federal-motor-carrier-safety-administration\n    baseUri: https://mobile.fmcsa.dot.gov/qc/services\n    description: Federal Motor Carrier Safety Administration QCMobile API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: webKey\n      value: '{{FEDERAL_MOTOR_CARRIER_SAFETY_ADMINISTRATION_TOKEN}}'\n    resources:\n    - name: carriers-dotnumber\n      path: /carriers/{dotNumber}\n      operations:\n      - name: getcarrierbydotnumber\n\
  \        method: GET\n        description: Get carrier by DOT number\n        inputParameters:\n        - name: dotNumber\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carriers-name-name\n      path: /carriers/name/{name}\n      operations:\n      - name: searchcarriersbyname\n        method: GET\n        description: Search carriers by name\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carriers-dotnumber-cargo-carried\n      path: /carriers/{dotNumber}/cargo-carried\n      operations:\n      - name: getcarriercargocarried\n        method: GET\n        description: Get cargo carried for a carrier\n        inputParameters:\n\
  \        - name: dotNumber\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carriers-dotnumber-operation-classification\n      path: /carriers/{dotNumber}/operation-classification\n      operations:\n      - name: getcarrieroperationclassification\n        method: GET\n        description: Get operation classification for a carrier\n        inputParameters:\n        - name: dotNumber\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carriers-dotnumber-oos\n      path: /carriers/{dotNumber}/oos\n      operations:\n      - name: getcarrieroos\n        method: GET\n        description: Get out-of-service info for a carrier\n        inputParameters:\n        - name: dotNumber\n\
  \          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carriers-dotnumber-docket-numbers\n      path: /carriers/{dotNumber}/docket-numbers\n      operations:\n      - name: getcarrierdocketnumbers\n        method: GET\n        description: Get docket numbers for a carrier\n        inputParameters:\n        - name: dotNumber\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carriers-dotnumber-authority\n      path: /carriers/{dotNumber}/authority\n      operations:\n      - name: getcarrierauthority\n        method: GET\n        description: Get carrier authority\n        inputParameters:\n        - name: dotNumber\n          in: path\n          type: integer\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: federal-motor-carrier-safety-administration-rest\n    description: REST adapter for Federal Motor Carrier Safety Administration QCMobile API.\n    resources:\n    - path: /carriers/{dotNumber}\n      name: getcarrierbydotnumber\n      operations:\n      - method: GET\n        name: getcarrierbydotnumber\n        description: Get carrier by DOT number\n        call: federal-motor-carrier-safety-administration.getcarrierbydotnumber\n        with:\n          dotNumber: rest.dotNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carriers/name/{name}\n      name: searchcarriersbyname\n      operations:\n      - method: GET\n        name: searchcarriersbyname\n        description: Search carriers by name\n        call: federal-motor-carrier-safety-administration.searchcarriersbyname\n\
  \        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carriers/{dotNumber}/cargo-carried\n      name: getcarriercargocarried\n      operations:\n      - method: GET\n        name: getcarriercargocarried\n        description: Get cargo carried for a carrier\n        call: federal-motor-carrier-safety-administration.getcarriercargocarried\n        with:\n          dotNumber: rest.dotNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carriers/{dotNumber}/operation-classification\n      name: getcarrieroperationclassification\n      operations:\n      - method: GET\n        name: getcarrieroperationclassification\n        description: Get operation classification for a carrier\n        call: federal-motor-carrier-safety-administration.getcarrieroperationclassification\n        with:\n          dotNumber: rest.dotNumber\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /carriers/{dotNumber}/oos\n      name: getcarrieroos\n      operations:\n      - method: GET\n        name: getcarrieroos\n        description: Get out-of-service info for a carrier\n        call: federal-motor-carrier-safety-administration.getcarrieroos\n        with:\n          dotNumber: rest.dotNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carriers/{dotNumber}/docket-numbers\n      name: getcarrierdocketnumbers\n      operations:\n      - method: GET\n        name: getcarrierdocketnumbers\n        description: Get docket numbers for a carrier\n        call: federal-motor-carrier-safety-administration.getcarrierdocketnumbers\n        with:\n          dotNumber: rest.dotNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carriers/{dotNumber}/authority\n      name: getcarrierauthority\n      operations:\n      - method: GET\n        name: getcarrierauthority\n\
  \        description: Get carrier authority\n        call: federal-motor-carrier-safety-administration.getcarrierauthority\n        with:\n          dotNumber: rest.dotNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: federal-motor-carrier-safety-administration-mcp\n    transport: http\n    description: MCP adapter for Federal Motor Carrier Safety Administration QCMobile API for AI agent use.\n    tools:\n    - name: getcarrierbydotnumber\n      description: Get carrier by DOT number\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-motor-carrier-safety-administration.getcarrierbydotnumber\n      with:\n        dotNumber: tools.dotNumber\n      inputParameters:\n      - name: dotNumber\n        type: integer\n        description: dotNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcarriersbyname\n\
  \      description: Search carriers by name\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-motor-carrier-safety-administration.searchcarriersbyname\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcarriercargocarried\n      description: Get cargo carried for a carrier\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-motor-carrier-safety-administration.getcarriercargocarried\n      with:\n        dotNumber: tools.dotNumber\n      inputParameters:\n      - name: dotNumber\n        type: integer\n        description: dotNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcarrieroperationclassification\n      description:\
  \ Get operation classification for a carrier\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-motor-carrier-safety-administration.getcarrieroperationclassification\n      with:\n        dotNumber: tools.dotNumber\n      inputParameters:\n      - name: dotNumber\n        type: integer\n        description: dotNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcarrieroos\n      description: Get out-of-service info for a carrier\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-motor-carrier-safety-administration.getcarrieroos\n      with:\n        dotNumber: tools.dotNumber\n      inputParameters:\n      - name: dotNumber\n        type: integer\n        description: dotNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcarrierdocketnumbers\n\
  \      description: Get docket numbers for a carrier\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-motor-carrier-safety-administration.getcarrierdocketnumbers\n      with:\n        dotNumber: tools.dotNumber\n      inputParameters:\n      - name: dotNumber\n        type: integer\n        description: dotNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcarrierauthority\n      description: Get carrier authority\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-motor-carrier-safety-administration.getcarrierauthority\n      with:\n        dotNumber: tools.dotNumber\n      inputParameters:\n      - name: dotNumber\n        type: integer\n        description: dotNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n   \
  \ FEDERAL_MOTOR_CARRIER_SAFETY_ADMINISTRATION_TOKEN: FEDERAL_MOTOR_CARRIER_SAFETY_ADMINISTRATION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/federal-motor-carrier-safety-administration/refs/heads/main/capabilities/federal-motor-carrier-safety-administration-capability.yaml
tags:
- Federal
- Motor
- Carrier
- Safety
- Administration
- API
tools:
- description: Get carrier by DOT number
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcarrierbydotnumber
- description: Search carriers by name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcarriersbyname
- description: Get cargo carried for a carrier
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcarriercargocarried
- description: Get operation classification for a carrier
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcarrieroperationclassification
- description: Get out-of-service info for a carrier
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcarrieroos
- description: Get docket numbers for a carrier
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcarrierdocketnumbers
- description: Get carrier authority
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcarrierauthority
---

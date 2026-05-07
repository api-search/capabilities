---
categories: []
consumed_apis: []
description: The NHTSA Crash Data API provides public access to U.S. National Highway Traffic Safety Administration crash datasets including the Fatality Analysis Reporting System (FARS) and the Crash Report Sampling System (CRSS). The API exposes case lists, case details, and aggregated crash queries by location, vehicle, and occupant via REST endpoints that return JSON, XML, or CSV.
layout: capability
name: NHTSA Crash Data API
operations:
- description: Get FARS dataset
  method: GET
  name: getfarsdata
  path: /FARSData/GetFARSData
- description: Get case list
  method: GET
  name: getcaselist
  path: /crashes/GetCaseList
- description: Get case details
  method: GET
  name: getcasedetails
  path: /crashes/GetCaseDetails
- description: Get crashes by location
  method: GET
  name: getcrashesbylocation
  path: /crashes/GetCrashesByLocation
- description: Get crashes by vehicle
  method: GET
  name: getcrashesbyvehicle
  path: /crashes/GetCrashesByVehicle
- description: Get crashes by occupant
  method: GET
  name: getcrashesbyoccupant
  path: /crashes/GetCrashesByOccupant
personas: []
provider_name: NHTSA Crash API
provider_slug: nhtsa-crash-api
search_terms:
- traffic safety
- getcrashesbylocation
- get case details
- get case list
- api
- getcrashesbyvehicle
- get crashes by vehicle
- getfarsdata
- get crashes by location
- get crashes by occupant
- transportation
- getcaselist
- getcasedetails
- government
- nhtsa
- crash
- get fars dataset
- crash data
- getcrashesbyoccupant
slug: nhtsa-crash-api-capability
source_filename: nhtsa-crash-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NHTSA Crash Data API\n  description: The NHTSA Crash Data API provides public access to U.S. National Highway Traffic Safety Administration crash\n    datasets including the Fatality Analysis Reporting System (FARS) and the Crash Report Sampling System (CRSS). The API\n    exposes case lists, case details, and aggregated crash queries by location, vehicle, and occupant via REST endpoints that\n    return JSON, XML, or CSV.\n  tags:\n  - Nhtsa\n  - Crash\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nhtsa-crash-api\n    baseUri: https://crashviewer.nhtsa.dot.gov/CrashAPI\n    description: NHTSA Crash Data API HTTP API.\n    resources:\n    - name: farsdata-getfarsdata\n      path: /FARSData/GetFARSData\n      operations:\n      - name: getfarsdata\n        method: GET\n        description: Get FARS dataset\n        inputParameters:\n        - name: dataset\n\
  \          in: query\n          type: string\n          required: true\n          description: FARS dataset name (e.g., Accident, Vehicle, Person).\n        - name: caseYear\n          in: query\n          type: integer\n          required: true\n          description: Case year (YYYY).\n        - name: format\n          in: query\n          type: string\n          description: Response format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crashes-getcaselist\n      path: /crashes/GetCaseList\n      operations:\n      - name: getcaselist\n        method: GET\n        description: Get case list\n        inputParameters:\n        - name: states\n          in: query\n          type: string\n          required: true\n          description: State FIPS code(s), comma separated.\n        - name: fromCaseYear\n          in: query\n          type: integer\n          required: true\n          description:\
  \ Beginning case year.\n        - name: toCaseYear\n          in: query\n          type: integer\n          required: true\n          description: Ending case year.\n        - name: minNumOfVehicles\n          in: query\n          type: integer\n          description: Minimum number of vehicles involved.\n        - name: maxNumOfVehicles\n          in: query\n          type: integer\n          description: Maximum number of vehicles involved.\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crashes-getcasedetails\n      path: /crashes/GetCaseDetails\n      operations:\n      - name: getcasedetails\n        method: GET\n        description: Get case details\n        inputParameters:\n        - name: stateCase\n          in: query\n          type: string\n          required: true\n          description: State case number.\n      \
  \  - name: caseYear\n          in: query\n          type: integer\n          required: true\n        - name: state\n          in: query\n          type: integer\n          required: true\n          description: State FIPS code.\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crashes-getcrashesbylocation\n      path: /crashes/GetCrashesByLocation\n      operations:\n      - name: getcrashesbylocation\n        method: GET\n        description: Get crashes by location\n        inputParameters:\n        - name: fromCaseYear\n          in: query\n          type: integer\n          required: true\n        - name: toCaseYear\n          in: query\n          type: integer\n          required: true\n        - name: state\n          in: query\n          type: integer\n          required: true\n          description: State FIPS code.\n   \
  \     - name: county\n          in: query\n          type: integer\n          description: County FIPS code.\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crashes-getcrashesbyvehicle\n      path: /crashes/GetCrashesByVehicle\n      operations:\n      - name: getcrashesbyvehicle\n        method: GET\n        description: Get crashes by vehicle\n        inputParameters:\n        - name: fromCaseYear\n          in: query\n          type: integer\n          required: true\n        - name: toCaseYear\n          in: query\n          type: integer\n          required: true\n        - name: state\n          in: query\n          type: integer\n          required: true\n        - name: vPicMake\n          in: query\n          type: string\n        - name: vPicModel\n          in: query\n          type: string\n        - name: vPicBodyClass\n\
  \          in: query\n          type: string\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crashes-getcrashesbyoccupant\n      path: /crashes/GetCrashesByOccupant\n      operations:\n      - name: getcrashesbyoccupant\n        method: GET\n        description: Get crashes by occupant\n        inputParameters:\n        - name: fromCaseYear\n          in: query\n          type: integer\n          required: true\n        - name: toCaseYear\n          in: query\n          type: integer\n          required: true\n        - name: state\n          in: query\n          type: integer\n          required: true\n        - name: minAge\n          in: query\n          type: integer\n        - name: maxAge\n          in: query\n          type: integer\n        - name: sex\n          in: query\n          type: integer\n        - name: seatPos\n\
  \          in: query\n          type: integer\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nhtsa-crash-api-rest\n    description: REST adapter for NHTSA Crash Data API.\n    resources:\n    - path: /FARSData/GetFARSData\n      name: getfarsdata\n      operations:\n      - method: GET\n        name: getfarsdata\n        description: Get FARS dataset\n        call: nhtsa-crash-api.getfarsdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /crashes/GetCaseList\n      name: getcaselist\n      operations:\n      - method: GET\n        name: getcaselist\n        description: Get case list\n        call: nhtsa-crash-api.getcaselist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /crashes/GetCaseDetails\n   \
  \   name: getcasedetails\n      operations:\n      - method: GET\n        name: getcasedetails\n        description: Get case details\n        call: nhtsa-crash-api.getcasedetails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /crashes/GetCrashesByLocation\n      name: getcrashesbylocation\n      operations:\n      - method: GET\n        name: getcrashesbylocation\n        description: Get crashes by location\n        call: nhtsa-crash-api.getcrashesbylocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /crashes/GetCrashesByVehicle\n      name: getcrashesbyvehicle\n      operations:\n      - method: GET\n        name: getcrashesbyvehicle\n        description: Get crashes by vehicle\n        call: nhtsa-crash-api.getcrashesbyvehicle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /crashes/GetCrashesByOccupant\n      name: getcrashesbyoccupant\n      operations:\n   \
  \   - method: GET\n        name: getcrashesbyoccupant\n        description: Get crashes by occupant\n        call: nhtsa-crash-api.getcrashesbyoccupant\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nhtsa-crash-api-mcp\n    transport: http\n    description: MCP adapter for NHTSA Crash Data API for AI agent use.\n    tools:\n    - name: getfarsdata\n      description: Get FARS dataset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nhtsa-crash-api.getfarsdata\n      with:\n        dataset: tools.dataset\n        caseYear: tools.caseYear\n        format: tools.format\n      inputParameters:\n      - name: dataset\n        type: string\n        description: FARS dataset name (e.g., Accident, Vehicle, Person).\n        required: true\n      - name: caseYear\n        type: integer\n        description: Case year (YYYY).\n        required: true\n      - name: format\n\
  \        type: string\n        description: Response format.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcaselist\n      description: Get case list\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nhtsa-crash-api.getcaselist\n      with:\n        states: tools.states\n        fromCaseYear: tools.fromCaseYear\n        toCaseYear: tools.toCaseYear\n        minNumOfVehicles: tools.minNumOfVehicles\n        maxNumOfVehicles: tools.maxNumOfVehicles\n        format: tools.format\n      inputParameters:\n      - name: states\n        type: string\n        description: State FIPS code(s), comma separated.\n        required: true\n      - name: fromCaseYear\n        type: integer\n        description: Beginning case year.\n        required: true\n      - name: toCaseYear\n        type: integer\n        description: Ending case year.\n        required: true\n      - name: minNumOfVehicles\n        type:\
  \ integer\n        description: Minimum number of vehicles involved.\n      - name: maxNumOfVehicles\n        type: integer\n        description: Maximum number of vehicles involved.\n      - name: format\n        type: string\n        description: format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcasedetails\n      description: Get case details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nhtsa-crash-api.getcasedetails\n      with:\n        stateCase: tools.stateCase\n        caseYear: tools.caseYear\n        state: tools.state\n        format: tools.format\n      inputParameters:\n      - name: stateCase\n        type: string\n        description: State case number.\n        required: true\n      - name: caseYear\n        type: integer\n        description: caseYear\n        required: true\n      - name: state\n        type: integer\n        description: State FIPS code.\n        required:\
  \ true\n      - name: format\n        type: string\n        description: format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcrashesbylocation\n      description: Get crashes by location\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nhtsa-crash-api.getcrashesbylocation\n      with:\n        fromCaseYear: tools.fromCaseYear\n        toCaseYear: tools.toCaseYear\n        state: tools.state\n        county: tools.county\n        format: tools.format\n      inputParameters:\n      - name: fromCaseYear\n        type: integer\n        description: fromCaseYear\n        required: true\n      - name: toCaseYear\n        type: integer\n        description: toCaseYear\n        required: true\n      - name: state\n        type: integer\n        description: State FIPS code.\n        required: true\n      - name: county\n        type: integer\n        description: County FIPS code.\n      - name: format\n\
  \        type: string\n        description: format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcrashesbyvehicle\n      description: Get crashes by vehicle\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nhtsa-crash-api.getcrashesbyvehicle\n      with:\n        fromCaseYear: tools.fromCaseYear\n        toCaseYear: tools.toCaseYear\n        state: tools.state\n        vPicMake: tools.vPicMake\n        vPicModel: tools.vPicModel\n        vPicBodyClass: tools.vPicBodyClass\n        format: tools.format\n      inputParameters:\n      - name: fromCaseYear\n        type: integer\n        description: fromCaseYear\n        required: true\n      - name: toCaseYear\n        type: integer\n        description: toCaseYear\n        required: true\n      - name: state\n        type: integer\n        description: state\n        required: true\n      - name: vPicMake\n        type: string\n        description:\
  \ vPicMake\n      - name: vPicModel\n        type: string\n        description: vPicModel\n      - name: vPicBodyClass\n        type: string\n        description: vPicBodyClass\n      - name: format\n        type: string\n        description: format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcrashesbyoccupant\n      description: Get crashes by occupant\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nhtsa-crash-api.getcrashesbyoccupant\n      with:\n        fromCaseYear: tools.fromCaseYear\n        toCaseYear: tools.toCaseYear\n        state: tools.state\n        minAge: tools.minAge\n        maxAge: tools.maxAge\n        sex: tools.sex\n        seatPos: tools.seatPos\n        format: tools.format\n      inputParameters:\n      - name: fromCaseYear\n        type: integer\n        description: fromCaseYear\n        required: true\n      - name: toCaseYear\n        type: integer\n        description:\
  \ toCaseYear\n        required: true\n      - name: state\n        type: integer\n        description: state\n        required: true\n      - name: minAge\n        type: integer\n        description: minAge\n      - name: maxAge\n        type: integer\n        description: maxAge\n      - name: sex\n        type: integer\n        description: sex\n      - name: seatPos\n        type: integer\n        description: seatPos\n      - name: format\n        type: string\n        description: format\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nhtsa-crash-api/refs/heads/main/capabilities/nhtsa-crash-api-capability.yaml
tags:
- Nhtsa
- Crash
- Api
- API
tools:
- description: Get FARS dataset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfarsdata
- description: Get case list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcaselist
- description: Get case details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcasedetails
- description: Get crashes by location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcrashesbylocation
- description: Get crashes by vehicle
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcrashesbyvehicle
- description: Get crashes by occupant
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcrashesbyoccupant
---

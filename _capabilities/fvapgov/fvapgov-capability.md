---
categories: []
consumed_apis: []
description: The Federal Voting Assistance Program (FVAP) publishes XML feeds providing voter information by U.S. state and territory. Each jurisdiction exposes four datasets covering important info, deadline dates, ballot rules, and election offices, plus a combined electronic Voting Assistance Guide (eVAG).
layout: capability
name: FVAP.gov XML API
operations:
- description: Get important voting information for a state or territory.
  method: GET
  name: getimportantinfo
  path: /xml-api/{state}/important-info.xml
- description: Get deadline dates for a state or territory.
  method: GET
  name: getdeadlinedates
  path: /xml-api/{state}/deadline-dates.xml
- description: Get ballot rules for a state or territory.
  method: GET
  name: getballotrules
  path: /xml-api/{state}/ballot-rules.xml
- description: Get election offices for a state or territory.
  method: GET
  name: getelectionoffices
  path: /xml-api/{state}/election-offices.xml
- description: Get the combined eVAG feed for a state or territory.
  method: GET
  name: getevag
  path: /xml-api/{state}/evag.xml
- description: Get the XML schema definition for the FVAP feeds.
  method: GET
  name: getapischema
  path: /xml-api/api-schema.xsd
personas: []
provider_name: FVAP.gov
provider_slug: fvapgov
search_terms:
- getapischema
- getelectionoffices
- fvapgov
- get election offices for a state or territory.
- get deadline dates for a state or territory.
- get the combined evag feed for a state or territory.
- government
- getdeadlinedates
- api
- get important voting information for a state or territory.
- getballotrules
- getevag
- get ballot rules for a state or territory.
- getimportantinfo
- voting
- get the xml schema definition for the fvap feeds.
slug: fvapgov-capability
source_filename: fvapgov-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FVAP.gov XML API\n  description: The Federal Voting Assistance Program (FVAP) publishes XML feeds providing voter information by U.S. state\n    and territory. Each jurisdiction exposes four datasets covering important info, deadline dates, ballot rules, and election\n    offices, plus a combined electronic Voting Assistance Guide (eVAG).\n  tags:\n  - Fvapgov\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fvapgov\n    baseUri: https://www.fvap.gov\n    description: FVAP.gov XML API HTTP API.\n    resources:\n    - name: xml-api-state-important-info-xml\n      path: /xml-api/{state}/important-info.xml\n      operations:\n      - name: getimportantinfo\n        method: GET\n        description: Get important voting information for a state or territory.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: xml-api-state-deadline-dates-xml\n      path: /xml-api/{state}/deadline-dates.xml\n      operations:\n      - name: getdeadlinedates\n        method: GET\n        description: Get deadline dates for a state or territory.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xml-api-state-ballot-rules-xml\n      path: /xml-api/{state}/ballot-rules.xml\n      operations:\n      - name: getballotrules\n        method: GET\n        description: Get ballot rules for a state or territory.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xml-api-state-election-offices-xml\n      path: /xml-api/{state}/election-offices.xml\n      operations:\n      - name: getelectionoffices\n        method: GET\n        description: Get election offices for a state or territory.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xml-api-state-evag-xml\n      path: /xml-api/{state}/evag.xml\n      operations:\n      - name: getevag\n        method: GET\n        description: Get the combined eVAG feed for a state or territory.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xml-api-api-schema-xsd\n      path: /xml-api/api-schema.xsd\n      operations:\n      - name: getapischema\n        method: GET\n        description: Get the XML schema definition for the FVAP feeds.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fvapgov-rest\n    description: REST adapter for FVAP.gov XML API.\n    resources:\n    - path: /xml-api/{state}/important-info.xml\n      name: getimportantinfo\n \
  \     operations:\n      - method: GET\n        name: getimportantinfo\n        description: Get important voting information for a state or territory.\n        call: fvapgov.getimportantinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /xml-api/{state}/deadline-dates.xml\n      name: getdeadlinedates\n      operations:\n      - method: GET\n        name: getdeadlinedates\n        description: Get deadline dates for a state or territory.\n        call: fvapgov.getdeadlinedates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /xml-api/{state}/ballot-rules.xml\n      name: getballotrules\n      operations:\n      - method: GET\n        name: getballotrules\n        description: Get ballot rules for a state or territory.\n        call: fvapgov.getballotrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /xml-api/{state}/election-offices.xml\n      name: getelectionoffices\n\
  \      operations:\n      - method: GET\n        name: getelectionoffices\n        description: Get election offices for a state or territory.\n        call: fvapgov.getelectionoffices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /xml-api/{state}/evag.xml\n      name: getevag\n      operations:\n      - method: GET\n        name: getevag\n        description: Get the combined eVAG feed for a state or territory.\n        call: fvapgov.getevag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /xml-api/api-schema.xsd\n      name: getapischema\n      operations:\n      - method: GET\n        name: getapischema\n        description: Get the XML schema definition for the FVAP feeds.\n        call: fvapgov.getapischema\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fvapgov-mcp\n    transport: http\n    description: MCP adapter for FVAP.gov XML\
  \ API for AI agent use.\n    tools:\n    - name: getimportantinfo\n      description: Get important voting information for a state or territory.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fvapgov.getimportantinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdeadlinedates\n      description: Get deadline dates for a state or territory.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fvapgov.getdeadlinedates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getballotrules\n      description: Get ballot rules for a state or territory.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fvapgov.getballotrules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getelectionoffices\n      description: Get election offices for\
  \ a state or territory.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fvapgov.getelectionoffices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getevag\n      description: Get the combined eVAG feed for a state or territory.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fvapgov.getevag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapischema\n      description: Get the XML schema definition for the FVAP feeds.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fvapgov.getapischema\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fvapgov/refs/heads/main/capabilities/fvapgov-capability.yaml
tags:
- Fvapgov
- API
tools:
- description: Get important voting information for a state or territory.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimportantinfo
- description: Get deadline dates for a state or territory.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeadlinedates
- description: Get ballot rules for a state or territory.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getballotrules
- description: Get election offices for a state or territory.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getelectionoffices
- description: Get the combined eVAG feed for a state or territory.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevag
- description: Get the XML schema definition for the FVAP feeds.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapischema
---

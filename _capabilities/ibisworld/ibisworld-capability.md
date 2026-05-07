---
categories: []
consumed_apis: []
description: The IBISWorld API provides programmatic access to industry research data, market intelligence reports, business environment profiles, classification systems, and economic forecasts for thousands of industries across global markets. Authentication uses OAuth 2.0 bearer tokens.
layout: capability
name: IBISWorld API
operations:
- description: List industry reports
  method: POST
  name: listreports
  path: /industry/v3/reportlist
- description: List report sections
  method: POST
  name: listsections
  path: /industry/v3/sections
- description: Retrieve industry report
  method: POST
  name: getreport
  path: /industry/v3/report
- description: Look up company
  method: POST
  name: lookupcompany
  path: /company/v3/lookup
- description: List business environment profiles
  method: POST
  name: listenvironmentprofiles
  path: /environment/v3/profilelist
- description: List classification systems
  method: POST
  name: listclassificationsystems
  path: /classification/v3/systems
- description: List available downloads
  method: POST
  name: listdownloads
  path: /downloads/v3/list
personas: []
provider_name: IBISWorld
provider_slug: ibisworld
search_terms:
- getreport
- listdownloads
- industry data
- api
- list business environment profiles
- business intelligence
- market research
- listenvironmentprofiles
- list industry reports
- listsections
- list available downloads
- listreports
- ibisworld
- look up company
- economics
- retrieve industry report
- lookupcompany
- listclassificationsystems
- list report sections
- list classification systems
slug: ibisworld-capability
source_filename: ibisworld-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: IBISWorld API\n  description: The IBISWorld API provides programmatic access to industry research data, market intelligence reports, business\n    environment profiles, classification systems, and economic forecasts for thousands of industries across global markets.\n    Authentication uses OAuth 2.0 bearer tokens.\n  tags:\n  - Ibisworld\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ibisworld\n    baseUri: https://api.ibisworld.com/v3\n    description: IBISWorld API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{IBISWORLD_TOKEN}}'\n    resources:\n    - name: industry-v3-reportlist\n      path: /industry/v3/reportlist\n      operations:\n      - name: listreports\n        method: POST\n        description: List industry reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: industry-v3-sections\n      path: /industry/v3/sections\n      operations:\n      - name: listsections\n        method: POST\n        description: List report sections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: industry-v3-report\n      path: /industry/v3/report\n      operations:\n      - name: getreport\n        method: POST\n        description: Retrieve industry report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: company-v3-lookup\n      path: /company/v3/lookup\n      operations:\n      - name: lookupcompany\n        method: POST\n        description: Look up company\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environment-v3-profilelist\n      path: /environment/v3/profilelist\n\
  \      operations:\n      - name: listenvironmentprofiles\n        method: POST\n        description: List business environment profiles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: classification-v3-systems\n      path: /classification/v3/systems\n      operations:\n      - name: listclassificationsystems\n        method: POST\n        description: List classification systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: downloads-v3-list\n      path: /downloads/v3/list\n      operations:\n      - name: listdownloads\n        method: POST\n        description: List available downloads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ibisworld-rest\n    description:\
  \ REST adapter for IBISWorld API.\n    resources:\n    - path: /industry/v3/reportlist\n      name: listreports\n      operations:\n      - method: POST\n        name: listreports\n        description: List industry reports\n        call: ibisworld.listreports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /industry/v3/sections\n      name: listsections\n      operations:\n      - method: POST\n        name: listsections\n        description: List report sections\n        call: ibisworld.listsections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /industry/v3/report\n      name: getreport\n      operations:\n      - method: POST\n        name: getreport\n        description: Retrieve industry report\n        call: ibisworld.getreport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /company/v3/lookup\n      name: lookupcompany\n      operations:\n      - method: POST\n\
  \        name: lookupcompany\n        description: Look up company\n        call: ibisworld.lookupcompany\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environment/v3/profilelist\n      name: listenvironmentprofiles\n      operations:\n      - method: POST\n        name: listenvironmentprofiles\n        description: List business environment profiles\n        call: ibisworld.listenvironmentprofiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /classification/v3/systems\n      name: listclassificationsystems\n      operations:\n      - method: POST\n        name: listclassificationsystems\n        description: List classification systems\n        call: ibisworld.listclassificationsystems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /downloads/v3/list\n      name: listdownloads\n      operations:\n      - method: POST\n        name: listdownloads\n        description:\
  \ List available downloads\n        call: ibisworld.listdownloads\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ibisworld-mcp\n    transport: http\n    description: MCP adapter for IBISWorld API for AI agent use.\n    tools:\n    - name: listreports\n      description: List industry reports\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibisworld.listreports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsections\n      description: List report sections\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibisworld.listsections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreport\n      description: Retrieve industry report\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ ibisworld.getreport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookupcompany\n      description: Look up company\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibisworld.lookupcompany\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listenvironmentprofiles\n      description: List business environment profiles\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibisworld.listenvironmentprofiles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclassificationsystems\n      description: List classification systems\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibisworld.listclassificationsystems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdownloads\n      description: List\
  \ available downloads\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibisworld.listdownloads\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    IBISWORLD_TOKEN: IBISWORLD_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ibisworld/refs/heads/main/capabilities/ibisworld-capability.yaml
tags:
- Ibisworld
- API
tools:
- description: List industry reports
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listreports
- description: List report sections
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listsections
- description: Retrieve industry report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getreport
- description: Look up company
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lookupcompany
- description: List business environment profiles
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listenvironmentprofiles
- description: List classification systems
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listclassificationsystems
- description: List available downloads
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listdownloads
---

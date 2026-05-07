---
categories: []
consumed_apis: []
description: The Gallagher Command Centre REST API provides HTTP functions for querying the Command Centre database and integrating third-party systems with Gallagher's security platform. Supports access control, alarm monitoring, cardholder management, and site management operations.
layout: capability
name: Gallagher Command Centre REST API
operations:
- description: List Cardholders
  method: GET
  name: listcardholders
  path: /cardholders
- description: List Alarms
  method: GET
  name: listalarms
  path: /alarms
- description: List Access Groups
  method: GET
  name: listaccessgroups
  path: /access_groups
- description: List Events
  method: GET
  name: listevents
  path: /events
personas: []
provider_name: Arthur J. Gallagher
provider_slug: arthur-j-gallagher
search_terms:
- listaccessgroups
- list events
- arthur
- list cardholders
- list alarms
- brokerage
- gallagher
- insurance
- listalarms
- api
- risk management
- claims management
- listcardholders
- security
- benefits
- list access groups
- listevents
slug: arthur-j-gallagher-capability
source_filename: arthur-j-gallagher-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Gallagher Command Centre REST API\n  description: The Gallagher Command Centre REST API provides HTTP functions for querying the Command Centre database and\n    integrating third-party systems with Gallagher's security platform. Supports access control, alarm monitoring, cardholder\n    management, and site management operations.\n  tags:\n  - Arthur\n  - J\n  - Gallagher\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: arthur-j-gallagher\n    baseUri: https://localhost:8904/api\n    description: Gallagher Command Centre REST API HTTP API.\n    resources:\n    - name: cardholders\n      path: /cardholders\n      operations:\n      - name: listcardholders\n        method: GET\n        description: List Cardholders\n        inputParameters:\n        - name: top\n          in: query\n          type: integer\n          description: Maximum number of results to return.\n\
  \        - name: name\n          in: query\n          type: string\n          description: Filter by cardholder name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alarms\n      path: /alarms\n      operations:\n      - name: listalarms\n        method: GET\n        description: List Alarms\n        inputParameters:\n        - name: top\n          in: query\n          type: integer\n          description: Maximum number of results to return.\n        - name: source\n          in: query\n          type: string\n          description: Filter by alarm source.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: access-groups\n      path: /access_groups\n      operations:\n      - name: listaccessgroups\n        method: GET\n        description: List Access Groups\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      operations:\n      - name: listevents\n        method: GET\n        description: List Events\n        inputParameters:\n        - name: after\n          in: query\n          type: string\n          description: Return events after this event ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: arthur-j-gallagher-rest\n    description: REST adapter for Gallagher Command Centre REST API.\n    resources:\n    - path: /cardholders\n      name: listcardholders\n      operations:\n      - method: GET\n        name: listcardholders\n        description: List Cardholders\n        call: arthur-j-gallagher.listcardholders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alarms\n      name: listalarms\n    \
  \  operations:\n      - method: GET\n        name: listalarms\n        description: List Alarms\n        call: arthur-j-gallagher.listalarms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /access_groups\n      name: listaccessgroups\n      operations:\n      - method: GET\n        name: listaccessgroups\n        description: List Access Groups\n        call: arthur-j-gallagher.listaccessgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events\n      name: listevents\n      operations:\n      - method: GET\n        name: listevents\n        description: List Events\n        call: arthur-j-gallagher.listevents\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: arthur-j-gallagher-mcp\n    transport: http\n    description: MCP adapter for Gallagher Command Centre REST API for AI agent use.\n    tools:\n    - name: listcardholders\n     \
  \ description: List Cardholders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: arthur-j-gallagher.listcardholders\n      with:\n        top: tools.top\n        name: tools.name\n      inputParameters:\n      - name: top\n        type: integer\n        description: Maximum number of results to return.\n      - name: name\n        type: string\n        description: Filter by cardholder name.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listalarms\n      description: List Alarms\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: arthur-j-gallagher.listalarms\n      with:\n        top: tools.top\n        source: tools.source\n      inputParameters:\n      - name: top\n        type: integer\n        description: Maximum number of results to return.\n      - name: source\n        type: string\n        description: Filter by alarm source.\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listaccessgroups\n      description: List Access Groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: arthur-j-gallagher.listaccessgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listevents\n      description: List Events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: arthur-j-gallagher.listevents\n      with:\n        after: tools.after\n      inputParameters:\n      - name: after\n        type: string\n        description: Return events after this event ID.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/arthur-j-gallagher/refs/heads/main/capabilities/arthur-j-gallagher-capability.yaml
tags:
- Arthur
- J
- Gallagher
- API
tools:
- description: List Cardholders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcardholders
- description: List Alarms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalarms
- description: List Access Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccessgroups
- description: List Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevents
---

---
categories: []
consumed_apis: []
description: NAVIS N4 provides terminal operating system APIs for container port operations. APIs enable container tracking, vessel planning, berth scheduling, yard management, and gate operations for port terminals and intermodal facilities. Now operated by Kaleris, serving 650+ organizations across 95+ countries.
layout: capability
name: Navis N4 Terminal Operating System REST API
operations:
- description: Search container units
  method: GET
  name: searchunits
  path: /units
- description: Get container unit details
  method: GET
  name: getunit
  path: /units/{unitId}
- description: List vessel visits
  method: GET
  name: listvesselvisits
  path: /vessel-visits
- description: Get vessel visit details
  method: GET
  name: getvesselvisit
  path: /vessel-visits/{visitId}
- description: Get units for a vessel visit
  method: GET
  name: getvesselvisitunits
  path: /vessel-visits/{visitId}/units
- description: List gate transactions
  method: GET
  name: listgatetransactions
  path: /gate-transactions
- description: Get active work queues
  method: GET
  name: getworkqueues
  path: /work-queues
- description: List active holds on units
  method: GET
  name: listholds
  path: /holds
personas: []
provider_name: Navis (Kaleris)
provider_slug: navis
search_terms:
- logistics
- get container unit details
- listholds
- terminal
- api
- get active work queues
- list vessel visits
- get units for a vessel visit
- getworkqueues
- searchunits
- port
- list gate transactions
- list active holds on units
- container
- search container units
- getunit
- listgatetransactions
- get vessel visit details
- maritime
- getvesselvisitunits
- listvesselvisits
- getvesselvisit
- navis
slug: navis-capability
source_filename: navis-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Navis N4 Terminal Operating System REST API\n  description: NAVIS N4 provides terminal operating system APIs for container port operations. APIs enable container tracking,\n    vessel planning, berth scheduling, yard management, and gate operations for port terminals and intermodal facilities.\n    Now operated by Kaleris, serving 650+ organizations across 95+ countries.\n  tags:\n  - Navis\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: navis\n    baseUri: https://yourterminal.navis.example.com/apex/n4/api/v2\n    description: Navis N4 Terminal Operating System REST API HTTP API.\n    authentication:\n      type: basic\n      username: '{{NAVIS_USERNAME}}'\n      password: '{{NAVIS_PASSWORD}}'\n    resources:\n    - name: units\n      path: /units\n      operations:\n      - name: searchunits\n        method: GET\n        description: Search container units\n      \
  \  inputParameters:\n        - name: unitNbr\n          in: query\n          type: string\n          description: Container number (ISO 6346 format, e.g., MSCU1234567)\n        - name: equipmentType\n          in: query\n          type: string\n        - name: category\n          in: query\n          type: string\n        - name: freightKind\n          in: query\n          type: string\n        - name: positionLocType\n          in: query\n          type: string\n        - name: lineOperator\n          in: query\n          type: string\n          description: Shipping line SCAC code\n        - name: vesselVisit\n          in: query\n          type: string\n          description: Vessel visit identifier\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: units-unitid\n\
  \      path: /units/{unitId}\n      operations:\n      - name: getunit\n        method: GET\n        description: Get container unit details\n        inputParameters:\n        - name: unitId\n          in: path\n          type: string\n          required: true\n          description: N4 unit identifier or ISO 6346 container number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessel-visits\n      path: /vessel-visits\n      operations:\n      - name: listvesselvisits\n        method: GET\n        description: List vessel visits\n        inputParameters:\n        - name: vesselName\n          in: query\n          type: string\n        - name: status\n          in: query\n          type: string\n        - name: arrivalFrom\n          in: query\n          type: string\n        - name: arrivalTo\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type:\
  \ integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessel-visits-visitid\n      path: /vessel-visits/{visitId}\n      operations:\n      - name: getvesselvisit\n        method: GET\n        description: Get vessel visit details\n        inputParameters:\n        - name: visitId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessel-visits-visitid-units\n      path: /vessel-visits/{visitId}/units\n      operations:\n      - name: getvesselvisitunits\n        method: GET\n        description: Get units for a vessel visit\n        inputParameters:\n        - name: visitId\n          in: path\n          type: string\n          required: true\n        - name: category\n          in: query\n          type: string\n        - name: limit\n\
  \          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gate-transactions\n      path: /gate-transactions\n      operations:\n      - name: listgatetransactions\n        method: GET\n        description: List gate transactions\n        inputParameters:\n        - name: transactionType\n          in: query\n          type: string\n        - name: containerNbr\n          in: query\n          type: string\n        - name: truckId\n          in: query\n          type: string\n        - name: fromDate\n          in: query\n          type: string\n        - name: toDate\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: work-queues\n      path: /work-queues\n     \
  \ operations:\n      - name: getworkqueues\n        method: GET\n        description: Get active work queues\n        inputParameters:\n        - name: craneId\n          in: query\n          type: string\n        - name: status\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: holds\n      path: /holds\n      operations:\n      - name: listholds\n        method: GET\n        description: List active holds on units\n        inputParameters:\n        - name: unitNbr\n          in: query\n          type: string\n        - name: holdType\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: navis-rest\n    description:\
  \ REST adapter for Navis N4 Terminal Operating System REST API.\n    resources:\n    - path: /units\n      name: searchunits\n      operations:\n      - method: GET\n        name: searchunits\n        description: Search container units\n        call: navis.searchunits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /units/{unitId}\n      name: getunit\n      operations:\n      - method: GET\n        name: getunit\n        description: Get container unit details\n        call: navis.getunit\n        with:\n          unitId: rest.unitId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vessel-visits\n      name: listvesselvisits\n      operations:\n      - method: GET\n        name: listvesselvisits\n        description: List vessel visits\n        call: navis.listvesselvisits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vessel-visits/{visitId}\n      name: getvesselvisit\n\
  \      operations:\n      - method: GET\n        name: getvesselvisit\n        description: Get vessel visit details\n        call: navis.getvesselvisit\n        with:\n          visitId: rest.visitId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vessel-visits/{visitId}/units\n      name: getvesselvisitunits\n      operations:\n      - method: GET\n        name: getvesselvisitunits\n        description: Get units for a vessel visit\n        call: navis.getvesselvisitunits\n        with:\n          visitId: rest.visitId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gate-transactions\n      name: listgatetransactions\n      operations:\n      - method: GET\n        name: listgatetransactions\n        description: List gate transactions\n        call: navis.listgatetransactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /work-queues\n      name: getworkqueues\n \
  \     operations:\n      - method: GET\n        name: getworkqueues\n        description: Get active work queues\n        call: navis.getworkqueues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /holds\n      name: listholds\n      operations:\n      - method: GET\n        name: listholds\n        description: List active holds on units\n        call: navis.listholds\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: navis-mcp\n    transport: http\n    description: MCP adapter for Navis N4 Terminal Operating System REST API for AI agent use.\n    tools:\n    - name: searchunits\n      description: Search container units\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: navis.searchunits\n      with:\n        unitNbr: tools.unitNbr\n        equipmentType: tools.equipmentType\n        category: tools.category\n        freightKind:\
  \ tools.freightKind\n        positionLocType: tools.positionLocType\n        lineOperator: tools.lineOperator\n        vesselVisit: tools.vesselVisit\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: unitNbr\n        type: string\n        description: Container number (ISO 6346 format, e.g., MSCU1234567)\n      - name: equipmentType\n        type: string\n        description: equipmentType\n      - name: category\n        type: string\n        description: category\n      - name: freightKind\n        type: string\n        description: freightKind\n      - name: positionLocType\n        type: string\n        description: positionLocType\n      - name: lineOperator\n        type: string\n        description: Shipping line SCAC code\n      - name: vesselVisit\n        type: string\n        description: Vessel visit identifier\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n\
  \        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getunit\n      description: Get container unit details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: navis.getunit\n      with:\n        unitId: tools.unitId\n      inputParameters:\n      - name: unitId\n        type: string\n        description: N4 unit identifier or ISO 6346 container number\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvesselvisits\n      description: List vessel visits\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: navis.listvesselvisits\n      with:\n        vesselName: tools.vesselName\n        status: tools.status\n        arrivalFrom: tools.arrivalFrom\n        arrivalTo: tools.arrivalTo\n        limit: tools.limit\n      inputParameters:\n      - name: vesselName\n        type:\
  \ string\n        description: vesselName\n      - name: status\n        type: string\n        description: status\n      - name: arrivalFrom\n        type: string\n        description: arrivalFrom\n      - name: arrivalTo\n        type: string\n        description: arrivalTo\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvesselvisit\n      description: Get vessel visit details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: navis.getvesselvisit\n      with:\n        visitId: tools.visitId\n      inputParameters:\n      - name: visitId\n        type: string\n        description: visitId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvesselvisitunits\n      description: Get units for a vessel visit\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: navis.getvesselvisitunits\n      with:\n        visitId: tools.visitId\n        category: tools.category\n        limit: tools.limit\n      inputParameters:\n      - name: visitId\n        type: string\n        description: visitId\n        required: true\n      - name: category\n        type: string\n        description: category\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgatetransactions\n      description: List gate transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: navis.listgatetransactions\n      with:\n        transactionType: tools.transactionType\n        containerNbr: tools.containerNbr\n        truckId: tools.truckId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        limit: tools.limit\n      inputParameters:\n      - name: transactionType\n\
  \        type: string\n        description: transactionType\n      - name: containerNbr\n        type: string\n        description: containerNbr\n      - name: truckId\n        type: string\n        description: truckId\n      - name: fromDate\n        type: string\n        description: fromDate\n      - name: toDate\n        type: string\n        description: toDate\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkqueues\n      description: Get active work queues\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: navis.getworkqueues\n      with:\n        craneId: tools.craneId\n        status: tools.status\n      inputParameters:\n      - name: craneId\n        type: string\n        description: craneId\n      - name: status\n        type: string\n        description: status\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: listholds\n      description: List active holds on units\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: navis.listholds\n      with:\n        unitNbr: tools.unitNbr\n        holdType: tools.holdType\n        limit: tools.limit\n      inputParameters:\n      - name: unitNbr\n        type: string\n        description: unitNbr\n      - name: holdType\n        type: string\n        description: holdType\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NAVIS_USERNAME: NAVIS_USERNAME\n    NAVIS_PASSWORD: NAVIS_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/navis/refs/heads/main/capabilities/navis-capability.yaml
tags:
- Navis
- API
tools:
- description: Search container units
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchunits
- description: Get container unit details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getunit
- description: List vessel visits
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvesselvisits
- description: Get vessel visit details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvesselvisit
- description: Get units for a vessel visit
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvesselvisitunits
- description: List gate transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgatetransactions
- description: Get active work queues
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkqueues
- description: List active holds on units
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listholds
---

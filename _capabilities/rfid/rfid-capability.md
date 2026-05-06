---
categories: []
consumed_apis: []
description: The Electronic Product Code Information Services (EPCIS) 2.0 REST API, standardized by GS1, enables capture and query of supply chain visibility events associated with RFID and barcode-tagged objects. EPCIS events record the what (EPC/barcode), when (timestamp), where (read point and business location), why (business step and disposition), and how (sensor data) of tagged objects throughout their journey in the supply chain.
layout: capability
name: EPCIS 2.0 REST API
operations:
- description: Capture EPCIS Events
  method: POST
  name: captureevents
  path: /events
- description: Query EPCIS Events
  method: GET
  name: getevents
  path: /events
- description: Get Single EPCIS Event
  method: GET
  name: getevent
  path: /events/{eventID}
- description: Create Named Query
  method: POST
  name: createnamedquery
  path: /queries
- description: List Named Queries
  method: GET
  name: getnamedqueries
  path: /queries
- description: Get Named Query
  method: GET
  name: getnamedquery
  path: /queries/{queryName}
- description: Delete Named Query
  method: DELETE
  name: deletenamedquery
  path: /queries/{queryName}
- description: Execute Named Query
  method: GET
  name: executenamedquery
  path: /queries/{queryName}/events
- description: Get Service Information
  method: GET
  name: getserviceinfo
  path: /serviceInfo
personas: []
provider_name: RFID
provider_slug: rfid
search_terms:
- epcis
- get single epcis event
- executenamedquery
- get named query
- iot
- captureevents
- execute named query
- delete named query
- getnamedqueries
- asset tracking
- supply chain
- inventory management
- deletenamedquery
- api
- getevents
- rfid
- getnamedquery
- create named query
- getevent
- capture epcis events
- query epcis events
- gs1
- createnamedquery
- get service information
- getserviceinfo
- list named queries
slug: rfid-capability
source_filename: rfid-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: EPCIS 2.0 REST API\n  description: The Electronic Product Code Information Services (EPCIS) 2.0 REST API, standardized by GS1, enables capture\n    and query of supply chain visibility events associated with RFID and barcode-tagged objects. EPCIS events record the what\n    (EPC/barcode), when (timestamp), where (read point and business location), why (business step and disposition), and how\n    (sensor data) of tagged objects throughout their journey in the supply chain.\n  tags:\n  - Rfid\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: rfid\n    baseUri: https://example.com/epcis\n    description: EPCIS 2.0 REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{RFID_TOKEN}}'\n    resources:\n    - name: events\n      path: /events\n      operations:\n      - name: captureevents\n        method: POST\n        description: Capture EPCIS Events\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getevents\n        method: GET\n        description: Query EPCIS Events\n        inputParameters:\n        - name: GS1-EPCIS-Version\n          in: header\n          type: string\n        - name: eventType\n          in: query\n          type: array\n        - name: EQ_EPC\n          in: query\n          type: string\n          description: Filter by specific EPC value\n        - name: EQ_bizStep\n          in: query\n          type: string\n          description: Filter by business step URI\n        - name: EQ_disposition\n          in: query\n          type: string\n          description: Filter by disposition URI\n        - name: GE_eventTime\n          in: query\n          type: string\n          description: Events at or after this time\n        - name: LT_eventTime\n          in: query\n          type: string\n          description: Events\
  \ before this time\n        - name: EQ_readPoint\n          in: query\n          type: string\n          description: Filter by read point URI\n        - name: EQ_bizLocation\n          in: query\n          type: string\n          description: Filter by business location URI\n        - name: maxEventCount\n          in: query\n          type: integer\n          description: Maximum number of events to return\n        - name: nextPageToken\n          in: query\n          type: string\n          description: Pagination token for next page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-eventid\n      path: /events/{eventID}\n      operations:\n      - name: getevent\n        method: GET\n        description: Get Single EPCIS Event\n        inputParameters:\n        - name: eventID\n          in: path\n          type: string\n          required: true\n          description: Unique EPCIS event\
  \ identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queries\n      path: /queries\n      operations:\n      - name: createnamedquery\n        method: POST\n        description: Create Named Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getnamedqueries\n        method: GET\n        description: List Named Queries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queries-queryname\n      path: /queries/{queryName}\n      operations:\n      - name: getnamedquery\n        method: GET\n        description: Get Named Query\n        inputParameters:\n        - name: queryName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n      - name: deletenamedquery\n        method: DELETE\n        description: Delete Named Query\n        inputParameters:\n        - name: queryName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queries-queryname-events\n      path: /queries/{queryName}/events\n      operations:\n      - name: executenamedquery\n        method: GET\n        description: Execute Named Query\n        inputParameters:\n        - name: queryName\n          in: path\n          type: string\n          required: true\n        - name: nextPageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: serviceinfo\n      path: /serviceInfo\n      operations:\n\
  \      - name: getserviceinfo\n        method: GET\n        description: Get Service Information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: rfid-rest\n    description: REST adapter for EPCIS 2.0 REST API.\n    resources:\n    - path: /events\n      name: captureevents\n      operations:\n      - method: POST\n        name: captureevents\n        description: Capture EPCIS Events\n        call: rfid.captureevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events\n      name: getevents\n      operations:\n      - method: GET\n        name: getevents\n        description: Query EPCIS Events\n        call: rfid.getevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events/{eventID}\n      name: getevent\n      operations:\n      - method: GET\n        name: getevent\n\
  \        description: Get Single EPCIS Event\n        call: rfid.getevent\n        with:\n          eventID: rest.eventID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queries\n      name: createnamedquery\n      operations:\n      - method: POST\n        name: createnamedquery\n        description: Create Named Query\n        call: rfid.createnamedquery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queries\n      name: getnamedqueries\n      operations:\n      - method: GET\n        name: getnamedqueries\n        description: List Named Queries\n        call: rfid.getnamedqueries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queries/{queryName}\n      name: getnamedquery\n      operations:\n      - method: GET\n        name: getnamedquery\n        description: Get Named Query\n        call: rfid.getnamedquery\n        with:\n          queryName: rest.queryName\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queries/{queryName}\n      name: deletenamedquery\n      operations:\n      - method: DELETE\n        name: deletenamedquery\n        description: Delete Named Query\n        call: rfid.deletenamedquery\n        with:\n          queryName: rest.queryName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queries/{queryName}/events\n      name: executenamedquery\n      operations:\n      - method: GET\n        name: executenamedquery\n        description: Execute Named Query\n        call: rfid.executenamedquery\n        with:\n          queryName: rest.queryName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /serviceInfo\n      name: getserviceinfo\n      operations:\n      - method: GET\n        name: getserviceinfo\n        description: Get Service Information\n        call: rfid.getserviceinfo\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: rfid-mcp\n    transport: http\n    description: MCP adapter for EPCIS 2.0 REST API for AI agent use.\n    tools:\n    - name: captureevents\n      description: Capture EPCIS Events\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: rfid.captureevents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getevents\n      description: Query EPCIS Events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: rfid.getevents\n      with:\n        eventType: tools.eventType\n        EQ_EPC: tools.EQ_EPC\n        EQ_bizStep: tools.EQ_bizStep\n        EQ_disposition: tools.EQ_disposition\n        GE_eventTime: tools.GE_eventTime\n        LT_eventTime: tools.LT_eventTime\n        EQ_readPoint: tools.EQ_readPoint\n        EQ_bizLocation: tools.EQ_bizLocation\n        maxEventCount:\
  \ tools.maxEventCount\n        nextPageToken: tools.nextPageToken\n      inputParameters:\n      - name: eventType\n        type: array\n        description: eventType\n      - name: EQ_EPC\n        type: string\n        description: Filter by specific EPC value\n      - name: EQ_bizStep\n        type: string\n        description: Filter by business step URI\n      - name: EQ_disposition\n        type: string\n        description: Filter by disposition URI\n      - name: GE_eventTime\n        type: string\n        description: Events at or after this time\n      - name: LT_eventTime\n        type: string\n        description: Events before this time\n      - name: EQ_readPoint\n        type: string\n        description: Filter by read point URI\n      - name: EQ_bizLocation\n        type: string\n        description: Filter by business location URI\n      - name: maxEventCount\n        type: integer\n        description: Maximum number of events to return\n      - name: nextPageToken\n\
  \        type: string\n        description: Pagination token for next page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getevent\n      description: Get Single EPCIS Event\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: rfid.getevent\n      with:\n        eventID: tools.eventID\n      inputParameters:\n      - name: eventID\n        type: string\n        description: Unique EPCIS event identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamedquery\n      description: Create Named Query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: rfid.createnamedquery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnamedqueries\n      description: List Named Queries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: rfid.getnamedqueries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnamedquery\n      description: Get Named Query\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: rfid.getnamedquery\n      with:\n        queryName: tools.queryName\n      inputParameters:\n      - name: queryName\n        type: string\n        description: queryName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamedquery\n      description: Delete Named Query\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: rfid.deletenamedquery\n      with:\n        queryName: tools.queryName\n      inputParameters:\n      - name: queryName\n        type: string\n        description: queryName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executenamedquery\n\
  \      description: Execute Named Query\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: rfid.executenamedquery\n      with:\n        queryName: tools.queryName\n        nextPageToken: tools.nextPageToken\n      inputParameters:\n      - name: queryName\n        type: string\n        description: queryName\n        required: true\n      - name: nextPageToken\n        type: string\n        description: nextPageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getserviceinfo\n      description: Get Service Information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: rfid.getserviceinfo\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    RFID_TOKEN: RFID_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rfid/refs/heads/main/capabilities/rfid-capability.yaml
tags:
- Rfid
- API
tools:
- description: Capture EPCIS Events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: captureevents
- description: Query EPCIS Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevents
- description: Get Single EPCIS Event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevent
- description: Create Named Query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamedquery
- description: List Named Queries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamedqueries
- description: Get Named Query
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamedquery
- description: Delete Named Query
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamedquery
- description: Execute Named Query
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: executenamedquery
- description: Get Service Information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserviceinfo
---

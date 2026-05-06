---
categories: []
consumed_apis: []
description: MarineTraffic AIS API provides real-time vessel position data from over 13,000 AIS receivers globally. Returns vessel positions, speeds, headings, and voyage information for fleet monitoring, port operations, and supply chain visibility.
layout: capability
name: MarineTraffic AIS Vessel Tracking API
operations:
- description: Get vessel details
  method: GET
  name: getvesseldetails
  path: /exportvessel/{apikey}
- description: Get vessel position track
  method: GET
  name: getvesseltrack
  path: /exportvesseltrack/{apikey}
- description: Get expected vessel arrivals at a port
  method: GET
  name: getexpectedarrivals
  path: /getexpectedarrivals/{apikey}
- description: Get port call events
  method: GET
  name: getportcalls
  path: /getportcalls/{apikey}
- description: Get vessel positions in area
  method: GET
  name: getvesselpositions
  path: /getvesselpositions/{apikey}
personas: []
provider_name: MarineTraffic
provider_slug: marinetraffic
search_terms:
- get port call events
- get vessel positions in area
- get vessel position track
- vessel tracking
- ais
- maritime
- get vessel details
- marinetraffic
- api
- shipping
- getportcalls
- getvesseldetails
- get expected vessel arrivals at a port
- getexpectedarrivals
- getvesselpositions
- getvesseltrack
slug: marinetraffic-capability
source_filename: marinetraffic-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: MarineTraffic AIS Vessel Tracking API\n  description: MarineTraffic AIS API provides real-time vessel position data from over 13,000 AIS receivers globally. Returns\n    vessel positions, speeds, headings, and voyage information for fleet monitoring, port operations, and supply chain visibility.\n  tags:\n  - Marinetraffic\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: marinetraffic\n    baseUri: https://services.marinetraffic.com/api\n    description: MarineTraffic AIS Vessel Tracking API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: apikey\n      value: '{{MARINETRAFFIC_TOKEN}}'\n    resources:\n    - name: exportvessel-apikey\n      path: /exportvessel/{apikey}\n      operations:\n      - name: getvesseldetails\n        method: GET\n        description: Get vessel details\n        inputParameters:\n        - name: apikey\n     \
  \     in: path\n          type: string\n          required: true\n          description: Your MarineTraffic API key\n        - name: v\n          in: query\n          type: integer\n          description: API version\n        - name: MMSI\n          in: query\n          type: string\n          description: Maritime Mobile Service Identity number (9 digits)\n        - name: IMO\n          in: query\n          type: integer\n          description: International Maritime Organization number\n        - name: vessel_name\n          in: query\n          type: string\n        - name: protocol\n          in: query\n          type: string\n        - name: msgtype\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exportvesseltrack-apikey\n      path: /exportvesseltrack/{apikey}\n      operations:\n      - name: getvesseltrack\n        method: GET\n        description:\
  \ Get vessel position track\n        inputParameters:\n        - name: apikey\n          in: path\n          type: string\n          required: true\n        - name: v\n          in: query\n          type: integer\n        - name: MMSI\n          in: query\n          type: string\n          required: true\n        - name: fromdate\n          in: query\n          type: string\n          required: true\n          description: Track start time (UTC, ISO 8601)\n        - name: todate\n          in: query\n          type: string\n          required: true\n          description: Track end time (UTC, ISO 8601)\n        - name: protocol\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getexpectedarrivals-apikey\n      path: /getexpectedarrivals/{apikey}\n      operations:\n      - name: getexpectedarrivals\n        method: GET\n        description: Get expected\
  \ vessel arrivals at a port\n        inputParameters:\n        - name: apikey\n          in: path\n          type: string\n          required: true\n        - name: portid\n          in: query\n          type: integer\n          required: true\n          description: MarineTraffic port identifier\n        - name: v\n          in: query\n          type: integer\n        - name: fromdate\n          in: query\n          type: string\n        - name: todate\n          in: query\n          type: string\n        - name: protocol\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getportcalls-apikey\n      path: /getportcalls/{apikey}\n      operations:\n      - name: getportcalls\n        method: GET\n        description: Get port call events\n        inputParameters:\n        - name: apikey\n          in: path\n          type: string\n          required: true\n\
  \        - name: portid\n          in: query\n          type: integer\n        - name: MMSI\n          in: query\n          type: string\n        - name: fromdate\n          in: query\n          type: string\n        - name: todate\n          in: query\n          type: string\n        - name: v\n          in: query\n          type: integer\n        - name: protocol\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getvesselpositions-apikey\n      path: /getvesselpositions/{apikey}\n      operations:\n      - name: getvesselpositions\n        method: GET\n        description: Get vessel positions in area\n        inputParameters:\n        - name: apikey\n          in: path\n          type: string\n          required: true\n        - name: MINLAT\n          in: query\n          type: number\n          required: true\n        - name: MAXLAT\n          in:\
  \ query\n          type: number\n          required: true\n        - name: MINLON\n          in: query\n          type: number\n          required: true\n        - name: MAXLON\n          in: query\n          type: number\n          required: true\n        - name: SHIPTYPE\n          in: query\n          type: integer\n          description: AIS vessel type code filter\n        - name: v\n          in: query\n          type: integer\n        - name: protocol\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: marinetraffic-rest\n    description: REST adapter for MarineTraffic AIS Vessel Tracking API.\n    resources:\n    - path: /exportvessel/{apikey}\n      name: getvesseldetails\n      operations:\n      - method: GET\n        name: getvesseldetails\n        description: Get vessel details\n        call: marinetraffic.getvesseldetails\n\
  \        with:\n          apikey: rest.apikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /exportvesseltrack/{apikey}\n      name: getvesseltrack\n      operations:\n      - method: GET\n        name: getvesseltrack\n        description: Get vessel position track\n        call: marinetraffic.getvesseltrack\n        with:\n          apikey: rest.apikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /getexpectedarrivals/{apikey}\n      name: getexpectedarrivals\n      operations:\n      - method: GET\n        name: getexpectedarrivals\n        description: Get expected vessel arrivals at a port\n        call: marinetraffic.getexpectedarrivals\n        with:\n          apikey: rest.apikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /getportcalls/{apikey}\n      name: getportcalls\n      operations:\n      - method: GET\n        name: getportcalls\n        description:\
  \ Get port call events\n        call: marinetraffic.getportcalls\n        with:\n          apikey: rest.apikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /getvesselpositions/{apikey}\n      name: getvesselpositions\n      operations:\n      - method: GET\n        name: getvesselpositions\n        description: Get vessel positions in area\n        call: marinetraffic.getvesselpositions\n        with:\n          apikey: rest.apikey\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: marinetraffic-mcp\n    transport: http\n    description: MCP adapter for MarineTraffic AIS Vessel Tracking API for AI agent use.\n    tools:\n    - name: getvesseldetails\n      description: Get vessel details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marinetraffic.getvesseldetails\n      with:\n        apikey: tools.apikey\n        v:\
  \ tools.v\n        MMSI: tools.MMSI\n        IMO: tools.IMO\n        vessel_name: tools.vessel_name\n        protocol: tools.protocol\n        msgtype: tools.msgtype\n      inputParameters:\n      - name: apikey\n        type: string\n        description: Your MarineTraffic API key\n        required: true\n      - name: v\n        type: integer\n        description: API version\n      - name: MMSI\n        type: string\n        description: Maritime Mobile Service Identity number (9 digits)\n      - name: IMO\n        type: integer\n        description: International Maritime Organization number\n      - name: vessel_name\n        type: string\n        description: vessel_name\n      - name: protocol\n        type: string\n        description: protocol\n      - name: msgtype\n        type: string\n        description: msgtype\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvesseltrack\n      description: Get vessel position track\n      hints:\n    \
  \    readOnly: true\n        destructive: false\n        idempotent: true\n      call: marinetraffic.getvesseltrack\n      with:\n        apikey: tools.apikey\n        v: tools.v\n        MMSI: tools.MMSI\n        fromdate: tools.fromdate\n        todate: tools.todate\n        protocol: tools.protocol\n      inputParameters:\n      - name: apikey\n        type: string\n        description: apikey\n        required: true\n      - name: v\n        type: integer\n        description: v\n      - name: MMSI\n        type: string\n        description: MMSI\n        required: true\n      - name: fromdate\n        type: string\n        description: Track start time (UTC, ISO 8601)\n        required: true\n      - name: todate\n        type: string\n        description: Track end time (UTC, ISO 8601)\n        required: true\n      - name: protocol\n        type: string\n        description: protocol\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getexpectedarrivals\n\
  \      description: Get expected vessel arrivals at a port\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marinetraffic.getexpectedarrivals\n      with:\n        apikey: tools.apikey\n        portid: tools.portid\n        v: tools.v\n        fromdate: tools.fromdate\n        todate: tools.todate\n        protocol: tools.protocol\n      inputParameters:\n      - name: apikey\n        type: string\n        description: apikey\n        required: true\n      - name: portid\n        type: integer\n        description: MarineTraffic port identifier\n        required: true\n      - name: v\n        type: integer\n        description: v\n      - name: fromdate\n        type: string\n        description: fromdate\n      - name: todate\n        type: string\n        description: todate\n      - name: protocol\n        type: string\n        description: protocol\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ getportcalls\n      description: Get port call events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marinetraffic.getportcalls\n      with:\n        apikey: tools.apikey\n        portid: tools.portid\n        MMSI: tools.MMSI\n        fromdate: tools.fromdate\n        todate: tools.todate\n        v: tools.v\n        protocol: tools.protocol\n      inputParameters:\n      - name: apikey\n        type: string\n        description: apikey\n        required: true\n      - name: portid\n        type: integer\n        description: portid\n      - name: MMSI\n        type: string\n        description: MMSI\n      - name: fromdate\n        type: string\n        description: fromdate\n      - name: todate\n        type: string\n        description: todate\n      - name: v\n        type: integer\n        description: v\n      - name: protocol\n        type: string\n        description: protocol\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: getvesselpositions\n      description: Get vessel positions in area\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marinetraffic.getvesselpositions\n      with:\n        apikey: tools.apikey\n        MINLAT: tools.MINLAT\n        MAXLAT: tools.MAXLAT\n        MINLON: tools.MINLON\n        MAXLON: tools.MAXLON\n        SHIPTYPE: tools.SHIPTYPE\n        v: tools.v\n        protocol: tools.protocol\n      inputParameters:\n      - name: apikey\n        type: string\n        description: apikey\n        required: true\n      - name: MINLAT\n        type: number\n        description: MINLAT\n        required: true\n      - name: MAXLAT\n        type: number\n        description: MAXLAT\n        required: true\n      - name: MINLON\n        type: number\n        description: MINLON\n        required: true\n      - name: MAXLON\n        type: number\n        description: MAXLON\n        required:\
  \ true\n      - name: SHIPTYPE\n        type: integer\n        description: AIS vessel type code filter\n      - name: v\n        type: integer\n        description: v\n      - name: protocol\n        type: string\n        description: protocol\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MARINETRAFFIC_TOKEN: MARINETRAFFIC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/marinetraffic/refs/heads/main/capabilities/marinetraffic-capability.yaml
tags:
- Marinetraffic
- API
tools:
- description: Get vessel details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvesseldetails
- description: Get vessel position track
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvesseltrack
- description: Get expected vessel arrivals at a port
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexpectedarrivals
- description: Get port call events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getportcalls
- description: Get vessel positions in area
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvesselpositions
---

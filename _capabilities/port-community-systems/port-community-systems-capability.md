---
categories: []
consumed_apis: []
description: Portbase is the Dutch Port Community System providing APIs for customs declarations, cargo manifests, vessel call notifications, berth planning, and port logistics coordination at the Port of Rotterdam and Amsterdam, connecting shipping lines, freight forwarders, customs authorities, and terminal operators.
layout: capability
name: Portbase Port Community System API
operations:
- description: List vessel calls
  method: GET
  name: listvesselcalls
  path: /vessel-calls
- description: Submit vessel call notification
  method: POST
  name: createvesselcall
  path: /vessel-calls
- description: Get vessel call
  method: GET
  name: getvesselcall
  path: /vessel-calls/{vesselCallId}
- description: Update vessel call
  method: PUT
  name: updatevesselcall
  path: /vessel-calls/{vesselCallId}
- description: Submit cargo manifest
  method: POST
  name: submitcargomanifest
  path: /cargo-manifests
- description: Get cargo manifest
  method: GET
  name: getcargomanifest
  path: /cargo-manifests/{manifestId}
- description: Submit import customs declaration
  method: POST
  name: submitimportdeclaration
  path: /customs/import-declarations
- description: Get container status
  method: GET
  name: getcontainer
  path: /containers/{containerId}
- description: Submit hazardous goods notification
  method: POST
  name: submithazardouscargodeclaration
  path: /hazardous-cargo
personas: []
provider_name: Port Community Systems
provider_slug: port-community-systems
search_terms:
- logistics
- getvesselcall
- update vessel call
- submitcargomanifest
- listvesselcalls
- api
- getcargomanifest
- systems
- get container status
- customs
- list vessel calls
- community
- cargo
- port
- submit import customs declaration
- submitimportdeclaration
- updatevesselcall
- submit hazardous goods notification
- get cargo manifest
- get vessel call
- maritime
- shipping
- submit cargo manifest
- submit vessel call notification
- submithazardouscargodeclaration
- getcontainer
- createvesselcall
slug: port-community-systems-capability
source_filename: port-community-systems-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Portbase Port Community System API\n  description: Portbase is the Dutch Port Community System providing APIs for customs declarations, cargo manifests, vessel\n    call notifications, berth planning, and port logistics coordination at the Port of Rotterdam and Amsterdam, connecting\n    shipping lines, freight forwarders, customs authorities, and terminal operators.\n  tags:\n  - Port\n  - Community\n  - Systems\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: port-community-systems\n    baseUri: https://api.portbase.com/v1\n    description: Portbase Port Community System API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PORT_COMMUNITY_SYSTEMS_TOKEN}}'\n    resources:\n    - name: vessel-calls\n      path: /vessel-calls\n      operations:\n      - name: listvesselcalls\n        method: GET\n        description: List vessel calls\n        inputParameters:\n\
  \        - name: portCode\n          in: query\n          type: string\n          description: UN/LOCODE of the port (e.g., NLRTM for Rotterdam)\n        - name: status\n          in: query\n          type: string\n          description: Filter by vessel call status\n        - name: fromDate\n          in: query\n          type: string\n          description: Earliest expected arrival date\n        - name: toDate\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvesselcall\n        method: POST\n        description: Submit vessel call notification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessel-calls-vesselcallid\n\
  \      path: /vessel-calls/{vesselCallId}\n      operations:\n      - name: getvesselcall\n        method: GET\n        description: Get vessel call\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatevesselcall\n        method: PUT\n        description: Update vessel call\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cargo-manifests\n      path: /cargo-manifests\n      operations:\n      - name: submitcargomanifest\n        method: POST\n        description: Submit cargo manifest\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cargo-manifests-manifestid\n      path: /cargo-manifests/{manifestId}\n      operations:\n      - name: getcargomanifest\n        method: GET\n        description: Get cargo manifest\n\
  \        inputParameters:\n        - name: manifestId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customs-import-declarations\n      path: /customs/import-declarations\n      operations:\n      - name: submitimportdeclaration\n        method: POST\n        description: Submit import customs declaration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: containers-containerid\n      path: /containers/{containerId}\n      operations:\n      - name: getcontainer\n        method: GET\n        description: Get container status\n        inputParameters:\n        - name: containerId\n          in: path\n          type: string\n          required: true\n          description: Container number (ISO 6346 format, e.g. MSCU1234567)\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hazardous-cargo\n      path: /hazardous-cargo\n      operations:\n      - name: submithazardouscargodeclaration\n        method: POST\n        description: Submit hazardous goods notification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: port-community-systems-rest\n    description: REST adapter for Portbase Port Community System API.\n    resources:\n    - path: /vessel-calls\n      name: listvesselcalls\n      operations:\n      - method: GET\n        name: listvesselcalls\n        description: List vessel calls\n        call: port-community-systems.listvesselcalls\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vessel-calls\n      name: createvesselcall\n      operations:\n      - method: POST\n\
  \        name: createvesselcall\n        description: Submit vessel call notification\n        call: port-community-systems.createvesselcall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vessel-calls/{vesselCallId}\n      name: getvesselcall\n      operations:\n      - method: GET\n        name: getvesselcall\n        description: Get vessel call\n        call: port-community-systems.getvesselcall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vessel-calls/{vesselCallId}\n      name: updatevesselcall\n      operations:\n      - method: PUT\n        name: updatevesselcall\n        description: Update vessel call\n        call: port-community-systems.updatevesselcall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cargo-manifests\n      name: submitcargomanifest\n      operations:\n      - method: POST\n        name: submitcargomanifest\n        description: Submit cargo\
  \ manifest\n        call: port-community-systems.submitcargomanifest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cargo-manifests/{manifestId}\n      name: getcargomanifest\n      operations:\n      - method: GET\n        name: getcargomanifest\n        description: Get cargo manifest\n        call: port-community-systems.getcargomanifest\n        with:\n          manifestId: rest.manifestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customs/import-declarations\n      name: submitimportdeclaration\n      operations:\n      - method: POST\n        name: submitimportdeclaration\n        description: Submit import customs declaration\n        call: port-community-systems.submitimportdeclaration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /containers/{containerId}\n      name: getcontainer\n      operations:\n      - method: GET\n        name: getcontainer\n  \
  \      description: Get container status\n        call: port-community-systems.getcontainer\n        with:\n          containerId: rest.containerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hazardous-cargo\n      name: submithazardouscargodeclaration\n      operations:\n      - method: POST\n        name: submithazardouscargodeclaration\n        description: Submit hazardous goods notification\n        call: port-community-systems.submithazardouscargodeclaration\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: port-community-systems-mcp\n    transport: http\n    description: MCP adapter for Portbase Port Community System API for AI agent use.\n    tools:\n    - name: listvesselcalls\n      description: List vessel calls\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: port-community-systems.listvesselcalls\n      with:\n\
  \        portCode: tools.portCode\n        status: tools.status\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: portCode\n        type: string\n        description: UN/LOCODE of the port (e.g., NLRTM for Rotterdam)\n      - name: status\n        type: string\n        description: Filter by vessel call status\n      - name: fromDate\n        type: string\n        description: Earliest expected arrival date\n      - name: toDate\n        type: string\n        description: toDate\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createvesselcall\n      description: Submit vessel call notification\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: port-community-systems.createvesselcall\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvesselcall\n      description: Get vessel call\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: port-community-systems.getvesselcall\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatevesselcall\n      description: Update vessel call\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: port-community-systems.updatevesselcall\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitcargomanifest\n      description: Submit cargo manifest\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: port-community-systems.submitcargomanifest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcargomanifest\n      description: Get cargo manifest\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: port-community-systems.getcargomanifest\n      with:\n        manifestId: tools.manifestId\n      inputParameters:\n      - name: manifestId\n        type: string\n        description: manifestId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitimportdeclaration\n      description: Submit import customs declaration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: port-community-systems.submitimportdeclaration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontainer\n      description: Get container status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: port-community-systems.getcontainer\n      with:\n        containerId: tools.containerId\n      inputParameters:\n      - name: containerId\n\
  \        type: string\n        description: Container number (ISO 6346 format, e.g. MSCU1234567)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submithazardouscargodeclaration\n      description: Submit hazardous goods notification\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: port-community-systems.submithazardouscargodeclaration\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PORT_COMMUNITY_SYSTEMS_TOKEN: PORT_COMMUNITY_SYSTEMS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/port-community-systems/refs/heads/main/capabilities/port-community-systems-capability.yaml
tags:
- Port
- Community
- Systems
- API
tools:
- description: List vessel calls
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvesselcalls
- description: Submit vessel call notification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvesselcall
- description: Get vessel call
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvesselcall
- description: Update vessel call
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatevesselcall
- description: Submit cargo manifest
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitcargomanifest
- description: Get cargo manifest
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcargomanifest
- description: Submit import customs declaration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitimportdeclaration
- description: Get container status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontainer
- description: Submit hazardous goods notification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submithazardouscargodeclaration
---

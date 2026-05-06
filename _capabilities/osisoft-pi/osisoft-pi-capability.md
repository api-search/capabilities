---
categories: []
consumed_apis: []
description: OSIsoft PI Web API (now part of AVEVA) provides a REST interface for accessing the PI System process historian. APIs enable real-time and historical time-series data retrieval, event frame queries, asset framework hierarchy navigation, and calculated data for industrial process monitoring.
layout: capability
name: OSIsoft PI Web API
operations:
- description: List PI Data Archive servers
  method: GET
  name: listdataservers
  path: /dataservers
- description: List PI points on a server
  method: GET
  name: listpipoints
  path: /dataservers/{webId}/points
- description: Get a PI point
  method: GET
  name: getpipoint
  path: /points/{webId}
- description: Get current stream value
  method: GET
  name: getstreamvalue
  path: /streams/{webId}/value
- description: Get recorded stream values
  method: GET
  name: getstreamrecorded
  path: /streams/{webId}/recorded
- description: Get interpolated stream values
  method: GET
  name: getstreaminterpolated
  path: /streams/{webId}/interpolated
- description: Get stream summary statistics
  method: GET
  name: getstreamsummary
  path: /streams/{webId}/summary
- description: List Asset Framework servers
  method: GET
  name: listassetservers
  path: /assetservers
- description: List AF elements
  method: GET
  name: listelements
  path: /assetdatabases/{webId}/elements
- description: List element attributes
  method: GET
  name: listattributes
  path: /elements/{webId}/attributes
- description: Query event frames
  method: GET
  name: listeventframes
  path: /eventframes
- description: Execute a batch request
  method: POST
  name: executebatch
  path: /batch
personas: []
provider_name: osisoft-pi
provider_slug: osisoft-pi
search_terms:
- get a pi point
- get stream summary statistics
- listdataservers
- listassetservers
- getstreamvalue
- list asset framework servers
- listpipoints
- list pi points on a server
- getstreamsummary
- list af elements
- osisoft
- list pi data archive servers
- get recorded stream values
- query event frames
- pi
- listeventframes
- api
- getpipoint
- list element attributes
- executebatch
- getstreaminterpolated
- getstreamrecorded
- listattributes
- listelements
- get interpolated stream values
- execute a batch request
- get current stream value
slug: osisoft-pi-capability
source_filename: osisoft-pi-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OSIsoft PI Web API\n  description: OSIsoft PI Web API (now part of AVEVA) provides a REST interface for accessing the PI System process historian.\n    APIs enable real-time and historical time-series data retrieval, event frame queries, asset framework hierarchy navigation,\n    and calculated data for industrial process monitoring.\n  tags:\n  - Osisoft\n  - Pi\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: osisoft-pi\n    baseUri: https://piwebapi.example.com/piwebapi\n    description: OSIsoft PI Web API HTTP API.\n    authentication:\n      type: basic\n      username: '{{OSISOFT_PI_USERNAME}}'\n      password: '{{OSISOFT_PI_PASSWORD}}'\n    resources:\n    - name: dataservers\n      path: /dataservers\n      operations:\n      - name: listdataservers\n        method: GET\n        description: List PI Data Archive servers\n        inputParameters:\n        - name:\
  \ selectedFields\n          in: query\n          type: string\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dataservers-webid-points\n      path: /dataservers/{webId}/points\n      operations:\n      - name: listpipoints\n        method: GET\n        description: List PI points on a server\n        inputParameters:\n        - name: nameFilter\n          in: query\n          type: string\n          description: Wildcard filter for tag names (e.g. *.FLOW)\n        - name: type\n          in: query\n          type: string\n          description: Filter by point type\n        - name: maxCount\n          in: query\n          type: integer\n        - name: startIndex\n          in: query\n          type: integer\n        - name: selectedFields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: points-webid\n      path: /points/{webId}\n      operations:\n      - name: getpipoint\n        method: GET\n        description: Get a PI point\n        inputParameters:\n        - name: selectedFields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: streams-webid-value\n      path: /streams/{webId}/value\n      operations:\n      - name: getstreamvalue\n        method: GET\n        description: Get current stream value\n        inputParameters:\n        - name: desiredUnits\n          in: query\n          type: string\n          description: Unit of measure for the returned value\n        - name: selectedFields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: streams-webid-recorded\n      path: /streams/{webId}/recorded\n      operations:\n      - name: getstreamrecorded\n        method: GET\n        description: Get recorded stream values\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n          description: Start time (absolute or relative, e.g. \"*-1d\" or \"2026-03-01T00:00:00Z\")\n        - name: endTime\n          in: query\n          type: string\n          description: End time\n        - name: boundaryType\n          in: query\n          type: string\n        - name: maxCount\n          in: query\n          type: integer\n        - name: desiredUnits\n          in: query\n          type: string\n        - name: selectedFields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: streams-webid-interpolated\n      path: /streams/{webId}/interpolated\n\
  \      operations:\n      - name: getstreaminterpolated\n        method: GET\n        description: Get interpolated stream values\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n        - name: endTime\n          in: query\n          type: string\n        - name: interval\n          in: query\n          type: string\n          description: Interval between values (e.g. \"1h\", \"5m\")\n        - name: desiredUnits\n          in: query\n          type: string\n        - name: maxCount\n          in: query\n          type: integer\n        - name: selectedFields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: streams-webid-summary\n      path: /streams/{webId}/summary\n      operations:\n      - name: getstreamsummary\n        method: GET\n        description: Get stream summary statistics\n        inputParameters:\n\
  \        - name: startTime\n          in: query\n          type: string\n        - name: endTime\n          in: query\n          type: string\n        - name: summaryType\n          in: query\n          type: string\n          description: Comma-separated summary types\n        - name: calculationBasis\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assetservers\n      path: /assetservers\n      operations:\n      - name: listassetservers\n        method: GET\n        description: List Asset Framework servers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assetdatabases-webid-elements\n      path: /assetdatabases/{webId}/elements\n      operations:\n      - name: listelements\n        method: GET\n        description: List AF elements\n        inputParameters:\n\
  \        - name: nameFilter\n          in: query\n          type: string\n        - name: templateName\n          in: query\n          type: string\n        - name: maxCount\n          in: query\n          type: integer\n        - name: selectedFields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: elements-webid-attributes\n      path: /elements/{webId}/attributes\n      operations:\n      - name: listattributes\n        method: GET\n        description: List element attributes\n        inputParameters:\n        - name: nameFilter\n          in: query\n          type: string\n        - name: selectedFields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: eventframes\n      path: /eventframes\n      operations:\n    \
  \  - name: listeventframes\n        method: GET\n        description: Query event frames\n        inputParameters:\n        - name: databaseWebId\n          in: query\n          type: string\n          required: true\n          description: AF database WebId to search\n        - name: startTime\n          in: query\n          type: string\n        - name: endTime\n          in: query\n          type: string\n        - name: nameFilter\n          in: query\n          type: string\n        - name: templateName\n          in: query\n          type: string\n        - name: maxCount\n          in: query\n          type: integer\n        - name: selectedFields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch\n      path: /batch\n      operations:\n      - name: executebatch\n        method: POST\n        description: Execute a batch request\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: osisoft-pi-rest\n    description: REST adapter for OSIsoft PI Web API.\n    resources:\n    - path: /dataservers\n      name: listdataservers\n      operations:\n      - method: GET\n        name: listdataservers\n        description: List PI Data Archive servers\n        call: osisoft-pi.listdataservers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dataservers/{webId}/points\n      name: listpipoints\n      operations:\n      - method: GET\n        name: listpipoints\n        description: List PI points on a server\n        call: osisoft-pi.listpipoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /points/{webId}\n      name: getpipoint\n      operations:\n      - method: GET\n        name: getpipoint\n        description: Get a PI point\n  \
  \      call: osisoft-pi.getpipoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /streams/{webId}/value\n      name: getstreamvalue\n      operations:\n      - method: GET\n        name: getstreamvalue\n        description: Get current stream value\n        call: osisoft-pi.getstreamvalue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /streams/{webId}/recorded\n      name: getstreamrecorded\n      operations:\n      - method: GET\n        name: getstreamrecorded\n        description: Get recorded stream values\n        call: osisoft-pi.getstreamrecorded\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /streams/{webId}/interpolated\n      name: getstreaminterpolated\n      operations:\n      - method: GET\n        name: getstreaminterpolated\n        description: Get interpolated stream values\n        call: osisoft-pi.getstreaminterpolated\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /streams/{webId}/summary\n      name: getstreamsummary\n      operations:\n      - method: GET\n        name: getstreamsummary\n        description: Get stream summary statistics\n        call: osisoft-pi.getstreamsummary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assetservers\n      name: listassetservers\n      operations:\n      - method: GET\n        name: listassetservers\n        description: List Asset Framework servers\n        call: osisoft-pi.listassetservers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assetdatabases/{webId}/elements\n      name: listelements\n      operations:\n      - method: GET\n        name: listelements\n        description: List AF elements\n        call: osisoft-pi.listelements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /elements/{webId}/attributes\n      name:\
  \ listattributes\n      operations:\n      - method: GET\n        name: listattributes\n        description: List element attributes\n        call: osisoft-pi.listattributes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /eventframes\n      name: listeventframes\n      operations:\n      - method: GET\n        name: listeventframes\n        description: Query event frames\n        call: osisoft-pi.listeventframes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /batch\n      name: executebatch\n      operations:\n      - method: POST\n        name: executebatch\n        description: Execute a batch request\n        call: osisoft-pi.executebatch\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: osisoft-pi-mcp\n    transport: http\n    description: MCP adapter for OSIsoft PI Web API for AI agent use.\n    tools:\n    - name: listdataservers\n\
  \      description: List PI Data Archive servers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: osisoft-pi.listdataservers\n      with:\n        selectedFields: tools.selectedFields\n      inputParameters:\n      - name: selectedFields\n        type: string\n        description: Comma-separated list of fields to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpipoints\n      description: List PI points on a server\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: osisoft-pi.listpipoints\n      with:\n        nameFilter: tools.nameFilter\n        type: tools.type\n        maxCount: tools.maxCount\n        startIndex: tools.startIndex\n        selectedFields: tools.selectedFields\n      inputParameters:\n      - name: nameFilter\n        type: string\n        description: Wildcard filter for tag names (e.g. *.FLOW)\n      - name: type\n\
  \        type: string\n        description: Filter by point type\n      - name: maxCount\n        type: integer\n        description: maxCount\n      - name: startIndex\n        type: integer\n        description: startIndex\n      - name: selectedFields\n        type: string\n        description: selectedFields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpipoint\n      description: Get a PI point\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: osisoft-pi.getpipoint\n      with:\n        selectedFields: tools.selectedFields\n      inputParameters:\n      - name: selectedFields\n        type: string\n        description: selectedFields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstreamvalue\n      description: Get current stream value\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: osisoft-pi.getstreamvalue\n\
  \      with:\n        desiredUnits: tools.desiredUnits\n        selectedFields: tools.selectedFields\n      inputParameters:\n      - name: desiredUnits\n        type: string\n        description: Unit of measure for the returned value\n      - name: selectedFields\n        type: string\n        description: selectedFields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstreamrecorded\n      description: Get recorded stream values\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: osisoft-pi.getstreamrecorded\n      with:\n        startTime: tools.startTime\n        endTime: tools.endTime\n        boundaryType: tools.boundaryType\n        maxCount: tools.maxCount\n        desiredUnits: tools.desiredUnits\n        selectedFields: tools.selectedFields\n      inputParameters:\n      - name: startTime\n        type: string\n        description: Start time (absolute or relative, e.g. \"*-1d\" or \"2026-03-01T00:00:00Z\"\
  )\n      - name: endTime\n        type: string\n        description: End time\n      - name: boundaryType\n        type: string\n        description: boundaryType\n      - name: maxCount\n        type: integer\n        description: maxCount\n      - name: desiredUnits\n        type: string\n        description: desiredUnits\n      - name: selectedFields\n        type: string\n        description: selectedFields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstreaminterpolated\n      description: Get interpolated stream values\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: osisoft-pi.getstreaminterpolated\n      with:\n        startTime: tools.startTime\n        endTime: tools.endTime\n        interval: tools.interval\n        desiredUnits: tools.desiredUnits\n        maxCount: tools.maxCount\n        selectedFields: tools.selectedFields\n      inputParameters:\n      - name: startTime\n     \
  \   type: string\n        description: startTime\n      - name: endTime\n        type: string\n        description: endTime\n      - name: interval\n        type: string\n        description: Interval between values (e.g. \"1h\", \"5m\")\n      - name: desiredUnits\n        type: string\n        description: desiredUnits\n      - name: maxCount\n        type: integer\n        description: maxCount\n      - name: selectedFields\n        type: string\n        description: selectedFields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstreamsummary\n      description: Get stream summary statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: osisoft-pi.getstreamsummary\n      with:\n        startTime: tools.startTime\n        endTime: tools.endTime\n        summaryType: tools.summaryType\n        calculationBasis: tools.calculationBasis\n      inputParameters:\n      - name: startTime\n       \
  \ type: string\n        description: startTime\n      - name: endTime\n        type: string\n        description: endTime\n      - name: summaryType\n        type: string\n        description: Comma-separated summary types\n      - name: calculationBasis\n        type: string\n        description: calculationBasis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listassetservers\n      description: List Asset Framework servers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: osisoft-pi.listassetservers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listelements\n      description: List AF elements\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: osisoft-pi.listelements\n      with:\n        nameFilter: tools.nameFilter\n        templateName: tools.templateName\n        maxCount: tools.maxCount\n        selectedFields:\
  \ tools.selectedFields\n      inputParameters:\n      - name: nameFilter\n        type: string\n        description: nameFilter\n      - name: templateName\n        type: string\n        description: templateName\n      - name: maxCount\n        type: integer\n        description: maxCount\n      - name: selectedFields\n        type: string\n        description: selectedFields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listattributes\n      description: List element attributes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: osisoft-pi.listattributes\n      with:\n        nameFilter: tools.nameFilter\n        selectedFields: tools.selectedFields\n      inputParameters:\n      - name: nameFilter\n        type: string\n        description: nameFilter\n      - name: selectedFields\n        type: string\n        description: selectedFields\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listeventframes\n      description: Query event frames\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: osisoft-pi.listeventframes\n      with:\n        databaseWebId: tools.databaseWebId\n        startTime: tools.startTime\n        endTime: tools.endTime\n        nameFilter: tools.nameFilter\n        templateName: tools.templateName\n        maxCount: tools.maxCount\n        selectedFields: tools.selectedFields\n      inputParameters:\n      - name: databaseWebId\n        type: string\n        description: AF database WebId to search\n        required: true\n      - name: startTime\n        type: string\n        description: startTime\n      - name: endTime\n        type: string\n        description: endTime\n      - name: nameFilter\n        type: string\n        description: nameFilter\n      - name: templateName\n        type: string\n        description: templateName\n      - name: maxCount\n        type: integer\n\
  \        description: maxCount\n      - name: selectedFields\n        type: string\n        description: selectedFields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executebatch\n      description: Execute a batch request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: osisoft-pi.executebatch\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OSISOFT_PI_USERNAME: OSISOFT_PI_USERNAME\n    OSISOFT_PI_PASSWORD: OSISOFT_PI_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/osisoft-pi/refs/heads/main/capabilities/osisoft-pi-capability.yaml
tags:
- Osisoft
- Pi
- API
tools:
- description: List PI Data Archive servers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdataservers
- description: List PI points on a server
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipoints
- description: Get a PI point
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpipoint
- description: Get current stream value
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstreamvalue
- description: Get recorded stream values
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstreamrecorded
- description: Get interpolated stream values
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstreaminterpolated
- description: Get stream summary statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstreamsummary
- description: List Asset Framework servers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassetservers
- description: List AF elements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listelements
- description: List element attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listattributes
- description: Query event frames
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventframes
- description: Execute a batch request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executebatch
---

---
categories: []
consumed_apis: []
description: API providing access to public information about Capitol campus buildings, art collections, historic preservation projects, and congressional facilities.
layout: capability
name: Architect of the Capitol Data API
operations:
- description: List Capitol campus buildings
  method: GET
  name: listbuildings
  path: /buildings
- description: Get building details
  method: GET
  name: getbuilding
  path: /buildings/{buildingId}
- description: List Capitol art collection
  method: GET
  name: listartworks
  path: /artworks
- description: Get artwork details
  method: GET
  name: getartwork
  path: /artworks/{artworkId}
- description: List historic preservation projects
  method: GET
  name: listpreservationprojects
  path: /preservation-projects
- description: Get preservation project details
  method: GET
  name: getpreservationproject
  path: /preservation-projects/{projectId}
- description: Get visitor information
  method: GET
  name: getvisitorinfo
  path: /visitor-info
- description: Get accessibility information
  method: GET
  name: getaccessibilityinfo
  path: /accessibility
personas: []
provider_name: Architect of the Capitol
provider_slug: architect-of-the-capitol
search_terms:
- get preservation project details
- getartwork
- government services
- list capitol campus buildings
- get artwork details
- getaccessibilityinfo
- get visitor information
- get accessibility information
- listpreservationprojects
- capitol hill
- getpreservationproject
- getbuilding
- the
- list capitol art collection
- api
- listartworks
- of
- listbuildings
- get building details
- architect
- congress
- list historic preservation projects
- federal government
- getvisitorinfo
- capitol
- historic preservation
slug: architect-of-the-capitol-capability
source_filename: architect-of-the-capitol-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Architect of the Capitol Data API\n  description: API providing access to public information about Capitol campus buildings, art collections, historic preservation\n    projects, and congressional facilities.\n  tags:\n  - Architect\n  - Of\n  - The\n  - Capitol\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: architect-of-the-capitol\n    baseUri: https://api.aoc.gov/v1\n    description: Architect of the Capitol Data API HTTP API.\n    resources:\n    - name: buildings\n      path: /buildings\n      operations:\n      - name: listbuildings\n        method: GET\n        description: List Capitol campus buildings\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: buildings-buildingid\n      path: /buildings/{buildingId}\n      operations:\n      - name: getbuilding\n        method: GET\n        description: Get building details\n        inputParameters:\n        - name: buildingId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artworks\n      path: /artworks\n      operations:\n      - name: listartworks\n        method: GET\n        description: List Capitol art collection\n        inputParameters:\n        - name: medium\n          in: query\n          type: string\n        - name: artist\n          in: query\n          type: string\n        - name: location\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n   \
  \     - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artworks-artworkid\n      path: /artworks/{artworkId}\n      operations:\n      - name: getartwork\n        method: GET\n        description: Get artwork details\n        inputParameters:\n        - name: artworkId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: preservation-projects\n      path: /preservation-projects\n      operations:\n      - name: listpreservationprojects\n        method: GET\n        description: List historic preservation projects\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n        - name: buildingId\n          in: query\n          type: string\n  \
  \      - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: preservation-projects-projectid\n      path: /preservation-projects/{projectId}\n      operations:\n      - name: getpreservationproject\n        method: GET\n        description: Get preservation project details\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: visitor-info\n      path: /visitor-info\n      operations:\n      - name: getvisitorinfo\n        method: GET\n        description: Get visitor information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: accessibility\n      path: /accessibility\n      operations:\n      - name: getaccessibilityinfo\n        method: GET\n        description: Get accessibility information\n        inputParameters:\n        - name: buildingId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: architect-of-the-capitol-rest\n    description: REST adapter for Architect of the Capitol Data API.\n    resources:\n    - path: /buildings\n      name: listbuildings\n      operations:\n      - method: GET\n        name: listbuildings\n        description: List Capitol campus buildings\n        call: architect-of-the-capitol.listbuildings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /buildings/{buildingId}\n      name: getbuilding\n      operations:\n\
  \      - method: GET\n        name: getbuilding\n        description: Get building details\n        call: architect-of-the-capitol.getbuilding\n        with:\n          buildingId: rest.buildingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /artworks\n      name: listartworks\n      operations:\n      - method: GET\n        name: listartworks\n        description: List Capitol art collection\n        call: architect-of-the-capitol.listartworks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /artworks/{artworkId}\n      name: getartwork\n      operations:\n      - method: GET\n        name: getartwork\n        description: Get artwork details\n        call: architect-of-the-capitol.getartwork\n        with:\n          artworkId: rest.artworkId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /preservation-projects\n      name: listpreservationprojects\n      operations:\n\
  \      - method: GET\n        name: listpreservationprojects\n        description: List historic preservation projects\n        call: architect-of-the-capitol.listpreservationprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /preservation-projects/{projectId}\n      name: getpreservationproject\n      operations:\n      - method: GET\n        name: getpreservationproject\n        description: Get preservation project details\n        call: architect-of-the-capitol.getpreservationproject\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /visitor-info\n      name: getvisitorinfo\n      operations:\n      - method: GET\n        name: getvisitorinfo\n        description: Get visitor information\n        call: architect-of-the-capitol.getvisitorinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accessibility\n      name:\
  \ getaccessibilityinfo\n      operations:\n      - method: GET\n        name: getaccessibilityinfo\n        description: Get accessibility information\n        call: architect-of-the-capitol.getaccessibilityinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: architect-of-the-capitol-mcp\n    transport: http\n    description: MCP adapter for Architect of the Capitol Data API for AI agent use.\n    tools:\n    - name: listbuildings\n      description: List Capitol campus buildings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architect-of-the-capitol.listbuildings\n      with:\n        type: tools.type\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: type\n        type: string\n        description: type\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type:\
  \ integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbuilding\n      description: Get building details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architect-of-the-capitol.getbuilding\n      with:\n        buildingId: tools.buildingId\n      inputParameters:\n      - name: buildingId\n        type: string\n        description: buildingId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listartworks\n      description: List Capitol art collection\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architect-of-the-capitol.listartworks\n      with:\n        medium: tools.medium\n        artist: tools.artist\n        location: tools.location\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: medium\n       \
  \ type: string\n        description: medium\n      - name: artist\n        type: string\n        description: artist\n      - name: location\n        type: string\n        description: location\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getartwork\n      description: Get artwork details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architect-of-the-capitol.getartwork\n      with:\n        artworkId: tools.artworkId\n      inputParameters:\n      - name: artworkId\n        type: string\n        description: artworkId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpreservationprojects\n      description: List historic preservation projects\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: architect-of-the-capitol.listpreservationprojects\n      with:\n        status: tools.status\n        buildingId: tools.buildingId\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: status\n        type: string\n        description: status\n      - name: buildingId\n        type: string\n        description: buildingId\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpreservationproject\n      description: Get preservation project details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architect-of-the-capitol.getpreservationproject\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description:\
  \ projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvisitorinfo\n      description: Get visitor information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architect-of-the-capitol.getvisitorinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccessibilityinfo\n      description: Get accessibility information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architect-of-the-capitol.getaccessibilityinfo\n      with:\n        buildingId: tools.buildingId\n      inputParameters:\n      - name: buildingId\n        type: string\n        description: buildingId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/architect-of-the-capitol/refs/heads/main/capabilities/architect-of-the-capitol-capability.yaml
tags:
- Architect
- Of
- The
- Capitol
- API
tools:
- description: List Capitol campus buildings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuildings
- description: Get building details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbuilding
- description: List Capitol art collection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listartworks
- description: Get artwork details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getartwork
- description: List historic preservation projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpreservationprojects
- description: Get preservation project details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpreservationproject
- description: Get visitor information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvisitorinfo
- description: Get accessibility information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccessibilityinfo
---

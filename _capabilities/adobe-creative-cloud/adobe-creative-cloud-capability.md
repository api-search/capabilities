---
categories: []
consumed_apis: []
description: REST API for accessing and managing Creative Cloud Libraries. Libraries provide a shared repository for colors, character styles, paragraph styles, graphics, and other creative assets that synchronize across Photoshop, Illustrator, InDesign, and other Creative Cloud applications. Supports CRUD operations on libraries and library elements, and includes an Asset Browser SDK for web integration.
layout: capability
name: Adobe Creative Cloud Creative Cloud Libraries API
operations:
- description: Adobe Creative Cloud List Libraries
  method: GET
  name: getlibraries
  path: /libraries
- description: Adobe Creative Cloud Create Library
  method: POST
  name: createlibrary
  path: /libraries
- description: Adobe Creative Cloud Get Library
  method: GET
  name: getlibrary
  path: /libraries/{libraryId}
- description: Adobe Creative Cloud Delete Library
  method: DELETE
  name: deletelibrary
  path: /libraries/{libraryId}
- description: Adobe Creative Cloud List Library Elements
  method: GET
  name: getelements
  path: /libraries/{libraryId}/elements
- description: Adobe Creative Cloud Create Element
  method: POST
  name: createelement
  path: /libraries/{libraryId}/elements
- description: Adobe Creative Cloud Get Element
  method: GET
  name: getelement
  path: /libraries/{libraryId}/elements/{elementId}
- description: Adobe Creative Cloud Delete Element
  method: DELETE
  name: deleteelement
  path: /libraries/{libraryId}/elements/{elementId}
personas: []
provider_name: Adobe Creative Cloud
provider_slug: adobe-creative-cloud
search_terms:
- createelement
- adobe creative cloud get library
- getlibraries
- getlibrary
- getelements
- deleteelement
- design
- creative
- deletelibrary
- adobe creative cloud create library
- adobe creative cloud create element
- cloud
- createlibrary
- adobe creative cloud delete library
- photography
- getelement
- adobe creative cloud list library elements
- saas
- api
- adobe creative cloud delete element
- video
- adobe
- adobe creative cloud list libraries
- documents
- ai/ml
- adobe creative cloud get element
slug: adobe-creative-cloud-capability
source_filename: adobe-creative-cloud-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Creative Cloud Creative Cloud Libraries API\n  description: REST API for accessing and managing Creative Cloud Libraries. Libraries provide a shared repository for colors,\n    character styles, paragraph styles, graphics, and other creative assets that synchronize across Photoshop, Illustrator,\n    InDesign, and other Creative Cloud applications. Supports CRUD operations on libraries and library elements, and includes\n    an Asset Browser SDK for web integration.\n  tags:\n  - Adobe\n  - Creative\n  - Cloud\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: adobe-creative-cloud\n    baseUri: https://cc-libraries.adobe.io/api/v1\n    description: Adobe Creative Cloud Creative Cloud Libraries API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ADOBE_CREATIVE_CLOUD_TOKEN}}'\n    resources:\n    - name: libraries\n      path: /libraries\n      operations:\n\
  \      - name: getlibraries\n        method: GET\n        description: Adobe Creative Cloud List Libraries\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of libraries to return.\n        - name: start\n          in: query\n          type: string\n          description: Pagination cursor from a previous response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlibrary\n        method: POST\n        description: Adobe Creative Cloud Create Library\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: libraries-libraryid\n      path: /libraries/{libraryId}\n      operations:\n      - name: getlibrary\n        method: GET\n        description: Adobe Creative Cloud Get Library\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletelibrary\n        method: DELETE\n        description: Adobe Creative Cloud Delete Library\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: libraries-libraryid-elements\n      path: /libraries/{libraryId}/elements\n      operations:\n      - name: getelements\n        method: GET\n        description: Adobe Creative Cloud List Library Elements\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: start\n          in: query\n          type: string\n        - name: type\n          in: query\n          type: string\n          description: Filter by element type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createelement\n        method: POST\n        description:\
  \ Adobe Creative Cloud Create Element\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: libraries-libraryid-elements-elementid\n      path: /libraries/{libraryId}/elements/{elementId}\n      operations:\n      - name: getelement\n        method: GET\n        description: Adobe Creative Cloud Get Element\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteelement\n        method: DELETE\n        description: Adobe Creative Cloud Delete Element\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: adobe-creative-cloud-rest\n    description: REST adapter for Adobe Creative Cloud Creative Cloud Libraries API.\n    resources:\n    - path: /libraries\n      name: getlibraries\n\
  \      operations:\n      - method: GET\n        name: getlibraries\n        description: Adobe Creative Cloud List Libraries\n        call: adobe-creative-cloud.getlibraries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /libraries\n      name: createlibrary\n      operations:\n      - method: POST\n        name: createlibrary\n        description: Adobe Creative Cloud Create Library\n        call: adobe-creative-cloud.createlibrary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /libraries/{libraryId}\n      name: getlibrary\n      operations:\n      - method: GET\n        name: getlibrary\n        description: Adobe Creative Cloud Get Library\n        call: adobe-creative-cloud.getlibrary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /libraries/{libraryId}\n      name: deletelibrary\n      operations:\n      - method: DELETE\n        name: deletelibrary\n        description:\
  \ Adobe Creative Cloud Delete Library\n        call: adobe-creative-cloud.deletelibrary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /libraries/{libraryId}/elements\n      name: getelements\n      operations:\n      - method: GET\n        name: getelements\n        description: Adobe Creative Cloud List Library Elements\n        call: adobe-creative-cloud.getelements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /libraries/{libraryId}/elements\n      name: createelement\n      operations:\n      - method: POST\n        name: createelement\n        description: Adobe Creative Cloud Create Element\n        call: adobe-creative-cloud.createelement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /libraries/{libraryId}/elements/{elementId}\n      name: getelement\n      operations:\n      - method: GET\n        name: getelement\n        description: Adobe Creative Cloud\
  \ Get Element\n        call: adobe-creative-cloud.getelement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /libraries/{libraryId}/elements/{elementId}\n      name: deleteelement\n      operations:\n      - method: DELETE\n        name: deleteelement\n        description: Adobe Creative Cloud Delete Element\n        call: adobe-creative-cloud.deleteelement\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: adobe-creative-cloud-mcp\n    transport: http\n    description: MCP adapter for Adobe Creative Cloud Creative Cloud Libraries API for AI agent use.\n    tools:\n    - name: getlibraries\n      description: Adobe Creative Cloud List Libraries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-creative-cloud.getlibraries\n      with:\n        limit: tools.limit\n        start: tools.start\n      inputParameters:\n    \
  \  - name: limit\n        type: integer\n        description: Maximum number of libraries to return.\n      - name: start\n        type: string\n        description: Pagination cursor from a previous response.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlibrary\n      description: Adobe Creative Cloud Create Library\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-creative-cloud.createlibrary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlibrary\n      description: Adobe Creative Cloud Get Library\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-creative-cloud.getlibrary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletelibrary\n      description: Adobe Creative Cloud Delete Library\n      hints:\n        readOnly: false\n        destructive: true\n\
  \        idempotent: true\n      call: adobe-creative-cloud.deletelibrary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getelements\n      description: Adobe Creative Cloud List Library Elements\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-creative-cloud.getelements\n      with:\n        limit: tools.limit\n        start: tools.start\n        type: tools.type\n      inputParameters:\n      - name: limit\n        type: integer\n        description: limit\n      - name: start\n        type: string\n        description: start\n      - name: type\n        type: string\n        description: Filter by element type.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createelement\n      description: Adobe Creative Cloud Create Element\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: adobe-creative-cloud.createelement\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getelement\n      description: Adobe Creative Cloud Get Element\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: adobe-creative-cloud.getelement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteelement\n      description: Adobe Creative Cloud Delete Element\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: adobe-creative-cloud.deleteelement\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ADOBE_CREATIVE_CLOUD_TOKEN: ADOBE_CREATIVE_CLOUD_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-creative-cloud/refs/heads/main/capabilities/adobe-creative-cloud-capability.yaml
tags:
- Adobe
- Creative
- Cloud
- API
tools:
- description: Adobe Creative Cloud List Libraries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlibraries
- description: Adobe Creative Cloud Create Library
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlibrary
- description: Adobe Creative Cloud Get Library
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlibrary
- description: Adobe Creative Cloud Delete Library
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelibrary
- description: Adobe Creative Cloud List Library Elements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getelements
- description: Adobe Creative Cloud Create Element
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createelement
- description: Adobe Creative Cloud Get Element
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getelement
- description: Adobe Creative Cloud Delete Element
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteelement
---

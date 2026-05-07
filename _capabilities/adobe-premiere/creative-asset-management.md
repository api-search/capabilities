---
categories:
- content-management
consumed_apis: []
description: Workflow capability for managing shared Creative Cloud Libraries and design assets for use in Adobe Premiere Pro video editing projects. Designed for video production teams and media asset managers.
layout: capability
name: Adobe Premiere Creative Asset Management
operations:
- description: List all Creative Cloud Libraries.
  method: GET
  name: list-libraries
  path: /v1/libraries
- description: Create a new Creative Cloud Library.
  method: POST
  name: create-library
  path: /v1/libraries
- description: List elements in a library.
  method: GET
  name: list-elements
  path: /v1/libraries/{libraryId}/elements
- description: Add an element to a library.
  method: POST
  name: add-element
  path: /v1/libraries/{libraryId}/elements
personas: []
provider_name: Adobe Premiere Pro
provider_slug: adobe-premiere
search_terms:
- list all creative cloud libraries available for use in adobe premiere pro projects.
- add element
- video editing
- automation
- video production
- list library elements
- Video Producer
- asset management
- add library element
- premiere pro
- add an element to a library.
- list elements in a library.
- create a new creative cloud library for organizing video production brand assets.
- add a new design element to a creative cloud library for sharing with the premiere pro team.
- list elements
- list libraries
- Media Asset Manager
- manage creative cloud libraries and assets for premiere pro video production.
- create library
- premiere pro plugin and extension ecosystem.
- elements within a creative cloud library.
- video editor and producer using adobe premiere pro for content creation.
- creative cloud libraries for shared production assets.
- media
- list all creative cloud libraries.
- list design elements (colors, graphics, fonts, patterns, videos) within a creative cloud library.
- adobe premiere
- adobe
- manager responsible for organizing shared brand assets in creative cloud.
- creative cloud
- create a new creative cloud library.
slug: creative-asset-management
source_filename: creative-asset-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Premiere Creative Asset Management\n  description: Workflow capability for managing shared Creative Cloud Libraries and design assets for use in Adobe Premiere\n    Pro video editing projects. Designed for video production teams and media asset managers.\n  tags:\n  - Adobe Premiere\n  - Creative Cloud\n  - Asset Management\n  - Video Production\n  - Media\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_CC_ACCESS_TOKEN: ADOBE_CC_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: cc-libraries\n    baseUri: https://cc-libraries.adobe.io\n    description: Adobe Creative Cloud Libraries REST API.\n    authentication:\n      type: bearer\n      token: '{{ADOBE_CC_ACCESS_TOKEN}}'\n    resources:\n    - name: libraries\n      path: /api/v1/libraries\n      description: Creative Cloud Libraries.\n      operations:\n      - name: list-libraries\n        method: GET\n   \
  \     description: List all Creative Cloud Libraries for the authenticated user.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of libraries to return.\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Starting index for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-library\n        method: POST\n        description: Create a new Creative Cloud Library.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: library-elements\n      path: /api/v1/libraries/{libraryId}/elements\n      description: Elements within a Creative\
  \ Cloud Library.\n      operations:\n      - name: list-elements\n        method: GET\n        description: List elements in a Creative Cloud Library.\n        inputParameters:\n        - name: libraryId\n          in: path\n          type: string\n          required: true\n          description: Library ID.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of elements to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-element\n        method: POST\n        description: Add a new element to a Creative Cloud Library.\n        inputParameters:\n        - name: libraryId\n          in: path\n          type: string\n          required: true\n          description: Library ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        body:\n          type: json\n          data:\n            name: '{{tools.elementName}}'\n            type: '{{tools.elementType}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: creative-asset-management-api\n    description: Unified REST API for Creative Cloud Libraries asset management in Adobe Premiere Pro workflows.\n    resources:\n    - path: /v1/libraries\n      name: libraries\n      description: Creative Cloud Libraries for shared production assets.\n      operations:\n      - method: GET\n        name: list-libraries\n        description: List all Creative Cloud Libraries.\n        call: cc-libraries.list-libraries\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-library\n        description: Create a new Creative Cloud Library.\n        call: cc-libraries.create-library\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/libraries/{libraryId}/elements\n      name: library-elements\n      description: Elements within a Creative Cloud Library.\n      operations:\n      - method: GET\n        name: list-elements\n        description: List elements in a library.\n        call: cc-libraries.list-elements\n        with:\n          libraryId: rest.libraryId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-element\n        description: Add an element to a library.\n        call: cc-libraries.create-element\n        with:\n          libraryId: rest.libraryId\n          elementName: rest.elementName\n          elementType: rest.elementType\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: creative-asset-management-mcp\n    transport: http\n    description: MCP server for AI-assisted creative asset management in Adobe Premiere Pro — discover, organize, and manage\n\
  \      brand assets in Creative Cloud Libraries.\n    tools:\n    - name: list-libraries\n      description: List all Creative Cloud Libraries available for use in Adobe Premiere Pro projects.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cc-libraries.list-libraries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-library\n      description: Create a new Creative Cloud Library for organizing video production brand assets.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cc-libraries.create-library\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-library-elements\n      description: List design elements (colors, graphics, fonts, patterns, videos) within a Creative Cloud Library.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cc-libraries.list-elements\n     \
  \ with:\n        libraryId: tools.libraryId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-library-element\n      description: Add a new design element to a Creative Cloud Library for sharing with the Premiere Pro team.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cc-libraries.create-element\n      with:\n        libraryId: tools.libraryId\n        elementName: tools.elementName\n        elementType: tools.elementType\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-premiere/refs/heads/main/capabilities/creative-asset-management.yaml
tags:
- Adobe Premiere
- Creative Cloud
- Asset Management
- Video Production
- Media
tools:
- description: List all Creative Cloud Libraries available for use in Adobe Premiere Pro projects.
  hints:
    openWorld: true
    readOnly: true
  name: list-libraries
- description: Create a new Creative Cloud Library for organizing video production brand assets.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-library
- description: List design elements (colors, graphics, fonts, patterns, videos) within a Creative Cloud Library.
  hints:
    openWorld: true
    readOnly: true
  name: list-library-elements
- description: Add a new design element to a Creative Cloud Library for sharing with the Premiere Pro team.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-library-element
---

---
categories: []
consumed_apis: []
description: The Archbee API enables programmatic management of documentation spaces, pages, and content within the Archbee documentation platform. Manage your docs, spaces, members, and settings through RESTful API endpoints.
layout: capability
name: Archbee API
operations:
- description: Archbee List Spaces
  method: GET
  name: listspaces
  path: /spaces
- description: Archbee Create Space
  method: POST
  name: createspace
  path: /spaces
- description: Archbee Get Space
  method: GET
  name: getspace
  path: /spaces/{spaceId}
- description: Archbee Delete Space
  method: DELETE
  name: deletespace
  path: /spaces/{spaceId}
- description: Archbee List Pages
  method: GET
  name: listpages
  path: /spaces/{spaceId}/pages
- description: Archbee Create Page
  method: POST
  name: createpage
  path: /spaces/{spaceId}/pages
- description: Archbee List Space Members
  method: GET
  name: listmembers
  path: /spaces/{spaceId}/members
personas: []
provider_name: Archbee
provider_slug: archbee
search_terms:
- integrates documentation into developer workflows
- archbee delete space
- archbee list pages
- createpage
- listmembers
- archbee
- listpages
- documentation platform
- managing team access to documentation spaces
- archbee list spaces
- manages documentation spaces, members, and access
- deletespace
- archbee get space
- developer docs
- creating and organizing technical documentation
- archbee create page
- api documentation
- api
- publishing and versioning documentation content
- knowledge base
- getspace
- listspaces
- creates and manages technical documentation content
- archbee create space
- technical writing
- createspace
- archbee list space members
slug: archbee-capability
source_filename: archbee-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Archbee API\n  description: The Archbee API enables programmatic management of documentation spaces, pages, and content within the Archbee\n    documentation platform. Manage your docs, spaces, members, and settings through RESTful API endpoints.\n  tags:\n  - Archbee\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: archbee\n    baseUri: https://api.archbee.com/v1\n    description: Archbee API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Api-Key\n      value: '{{ARCHBEE_TOKEN}}'\n    resources:\n    - name: spaces\n      path: /spaces\n      operations:\n      - name: listspaces\n        method: GET\n        description: Archbee List Spaces\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Page number for pagination\n        - name: limit\n          in: query\n \
  \         type: integer\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createspace\n        method: POST\n        description: Archbee Create Space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid\n      path: /spaces/{spaceId}\n      operations:\n      - name: getspace\n        method: GET\n        description: Archbee Get Space\n        inputParameters:\n        - name: spaceId\n          in: path\n          type: string\n          required: true\n          description: Space identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletespace\n        method: DELETE\n        description: Archbee Delete Space\n        inputParameters:\n        - name:\
  \ spaceId\n          in: path\n          type: string\n          required: true\n          description: Space identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-pages\n      path: /spaces/{spaceId}/pages\n      operations:\n      - name: listpages\n        method: GET\n        description: Archbee List Pages\n        inputParameters:\n        - name: spaceId\n          in: path\n          type: string\n          required: true\n          description: Space identifier\n        - name: parentId\n          in: query\n          type: string\n          description: Filter by parent page ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpage\n        method: POST\n        description: Archbee Create Page\n        inputParameters:\n        - name: spaceId\n          in: path\n   \
  \       type: string\n          required: true\n          description: Space identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-members\n      path: /spaces/{spaceId}/members\n      operations:\n      - name: listmembers\n        method: GET\n        description: Archbee List Space Members\n        inputParameters:\n        - name: spaceId\n          in: path\n          type: string\n          required: true\n          description: Space identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: archbee-rest\n    description: REST adapter for Archbee API.\n    resources:\n    - path: /spaces\n      name: listspaces\n      operations:\n      - method: GET\n        name: listspaces\n        description: Archbee List Spaces\n        call:\
  \ archbee.listspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces\n      name: createspace\n      operations:\n      - method: POST\n        name: createspace\n        description: Archbee Create Space\n        call: archbee.createspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}\n      name: getspace\n      operations:\n      - method: GET\n        name: getspace\n        description: Archbee Get Space\n        call: archbee.getspace\n        with:\n          spaceId: rest.spaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}\n      name: deletespace\n      operations:\n      - method: DELETE\n        name: deletespace\n        description: Archbee Delete Space\n        call: archbee.deletespace\n        with:\n          spaceId: rest.spaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /spaces/{spaceId}/pages\n      name: listpages\n      operations:\n      - method: GET\n        name: listpages\n        description: Archbee List Pages\n        call: archbee.listpages\n        with:\n          spaceId: rest.spaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/pages\n      name: createpage\n      operations:\n      - method: POST\n        name: createpage\n        description: Archbee Create Page\n        call: archbee.createpage\n        with:\n          spaceId: rest.spaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/members\n      name: listmembers\n      operations:\n      - method: GET\n        name: listmembers\n        description: Archbee List Space Members\n        call: archbee.listmembers\n        with:\n          spaceId: rest.spaceId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n\
  \    port: 9090\n    namespace: archbee-mcp\n    transport: http\n    description: MCP adapter for Archbee API for AI agent use.\n    tools:\n    - name: listspaces\n      description: Archbee List Spaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archbee.listspaces\n      with:\n        page: tools.page\n        limit: tools.limit\n      inputParameters:\n      - name: page\n        type: integer\n        description: Page number for pagination\n      - name: limit\n        type: integer\n        description: Results per page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createspace\n      description: Archbee Create Space\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: archbee.createspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getspace\n      description: Archbee Get Space\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archbee.getspace\n      with:\n        spaceId: tools.spaceId\n      inputParameters:\n      - name: spaceId\n        type: string\n        description: Space identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletespace\n      description: Archbee Delete Space\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: archbee.deletespace\n      with:\n        spaceId: tools.spaceId\n      inputParameters:\n      - name: spaceId\n        type: string\n        description: Space identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpages\n      description: Archbee List Pages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archbee.listpages\n      with:\n        spaceId:\
  \ tools.spaceId\n        parentId: tools.parentId\n      inputParameters:\n      - name: spaceId\n        type: string\n        description: Space identifier\n        required: true\n      - name: parentId\n        type: string\n        description: Filter by parent page ID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpage\n      description: Archbee Create Page\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: archbee.createpage\n      with:\n        spaceId: tools.spaceId\n      inputParameters:\n      - name: spaceId\n        type: string\n        description: Space identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmembers\n      description: Archbee List Space Members\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archbee.listmembers\n      with:\n        spaceId:\
  \ tools.spaceId\n      inputParameters:\n      - name: spaceId\n        type: string\n        description: Space identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ARCHBEE_TOKEN: ARCHBEE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/archbee/refs/heads/main/capabilities/archbee-capability.yaml
tags:
- Archbee
- API
tools:
- description: Archbee List Spaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listspaces
- description: Archbee Create Space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspace
- description: Archbee Get Space
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getspace
- description: Archbee Delete Space
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletespace
- description: Archbee List Pages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpages
- description: Archbee Create Page
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpage
- description: Archbee List Space Members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmembers
---

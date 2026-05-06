---
categories: []
consumed_apis: []
description: The Segment Config API allows programmatic management of Segment workspaces, sources, destinations, and other configuration resources. It provides endpoints to list workspace sources and destinations, create or delete destinations, and manage tracking plans. As of early 2024, Segment has stopped issuing new Config API tokens and recommends migrating to the Public API for access to the latest features. The Config API remains functional for existing users but is no longer actively developed.
layout: capability
name: Segment Config API
operations:
- description: Get workspace
  method: GET
  name: getworkspace
  path: /workspaces/{workspaceName}
- description: List sources
  method: GET
  name: listsources
  path: /workspaces/{workspaceName}/sources
- description: Create source
  method: POST
  name: createsource
  path: /workspaces/{workspaceName}/sources
- description: Get source
  method: GET
  name: getsource
  path: /workspaces/{workspaceName}/sources/{sourceName}
- description: Delete source
  method: DELETE
  name: deletesource
  path: /workspaces/{workspaceName}/sources/{sourceName}
- description: List destinations
  method: GET
  name: listdestinations
  path: /workspaces/{workspaceName}/sources/{sourceName}/destinations
- description: Create destination
  method: POST
  name: createdestination
  path: /workspaces/{workspaceName}/sources/{sourceName}/destinations
- description: Get destination
  method: GET
  name: getdestination
  path: /workspaces/{workspaceName}/sources/{sourceName}/destinations/{destinationName}
- description: Update destination
  method: PATCH
  name: updatedestination
  path: /workspaces/{workspaceName}/sources/{sourceName}/destinations/{destinationName}
- description: Delete destination
  method: DELETE
  name: deletedestination
  path: /workspaces/{workspaceName}/sources/{sourceName}/destinations/{destinationName}
- description: List tracking plans
  method: GET
  name: listtrackingplans
  path: /workspaces/{workspaceName}/tracking-plans
- description: Create tracking plan
  method: POST
  name: createtrackingplan
  path: /workspaces/{workspaceName}/tracking-plans
personas: []
provider_name: segment
provider_slug: segment
search_terms:
- list sources
- createtrackingplan
- update destination
- create tracking plan
- listtrackingplans
- getworkspace
- getdestination
- deletesource
- createdestination
- get workspace
- createsource
- updatedestination
- get source
- create source
- getsource
- listsources
- listdestinations
- api
- delete destination
- list tracking plans
- segment
- list destinations
- get destination
- deletedestination
- delete source
- create destination
slug: segment-capability
source_filename: segment-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Segment Config API\n  description: The Segment Config API allows programmatic management of Segment workspaces, sources, destinations, and other\n    configuration resources. It provides endpoints to list workspace sources and destinations, create or delete destinations,\n    and manage tracking plans. As of early 2024, Segment has stopped issuing new Config API tokens and recommends migrating\n    to the Public API for access to the latest features. The Config API remains functional for existing users but is no longer\n    actively developed.\n  tags:\n  - Segment\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: segment\n    baseUri: https://platform.segmentapis.com/v1beta\n    description: Segment Config API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{SEGMENT_TOKEN}}'\n    resources:\n    - name: workspaces-workspacename\n      path: /workspaces/{workspaceName}\n\
  \      operations:\n      - name: getworkspace\n        method: GET\n        description: Get workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspacename-sources\n      path: /workspaces/{workspaceName}/sources\n      operations:\n      - name: listsources\n        method: GET\n        description: List sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsource\n        method: POST\n        description: Create source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspacename-sources-sourcename\n      path: /workspaces/{workspaceName}/sources/{sourceName}\n      operations:\n      - name: getsource\n        method: GET\n        description: Get source\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesource\n        method: DELETE\n        description: Delete source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspacename-sources-sourcename-dest\n      path: /workspaces/{workspaceName}/sources/{sourceName}/destinations\n      operations:\n      - name: listdestinations\n        method: GET\n        description: List destinations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdestination\n        method: POST\n        description: Create destination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspacename-sources-sourcename-dest\n      path: /workspaces/{workspaceName}/sources/{sourceName}/destinations/{destinationName}\n\
  \      operations:\n      - name: getdestination\n        method: GET\n        description: Get destination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedestination\n        method: PATCH\n        description: Update destination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedestination\n        method: DELETE\n        description: Delete destination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspacename-tracking-plans\n      path: /workspaces/{workspaceName}/tracking-plans\n      operations:\n      - name: listtrackingplans\n        method: GET\n        description: List tracking plans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n      - name: createtrackingplan\n        method: POST\n        description: Create tracking plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: segment-rest\n    description: REST adapter for Segment Config API.\n    resources:\n    - path: /workspaces/{workspaceName}\n      name: getworkspace\n      operations:\n      - method: GET\n        name: getworkspace\n        description: Get workspace\n        call: segment.getworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceName}/sources\n      name: listsources\n      operations:\n      - method: GET\n        name: listsources\n        description: List sources\n        call: segment.listsources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceName}/sources\n\
  \      name: createsource\n      operations:\n      - method: POST\n        name: createsource\n        description: Create source\n        call: segment.createsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceName}/sources/{sourceName}\n      name: getsource\n      operations:\n      - method: GET\n        name: getsource\n        description: Get source\n        call: segment.getsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceName}/sources/{sourceName}\n      name: deletesource\n      operations:\n      - method: DELETE\n        name: deletesource\n        description: Delete source\n        call: segment.deletesource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceName}/sources/{sourceName}/destinations\n      name: listdestinations\n      operations:\n      - method: GET\n        name: listdestinations\n\
  \        description: List destinations\n        call: segment.listdestinations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceName}/sources/{sourceName}/destinations\n      name: createdestination\n      operations:\n      - method: POST\n        name: createdestination\n        description: Create destination\n        call: segment.createdestination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceName}/sources/{sourceName}/destinations/{destinationName}\n      name: getdestination\n      operations:\n      - method: GET\n        name: getdestination\n        description: Get destination\n        call: segment.getdestination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceName}/sources/{sourceName}/destinations/{destinationName}\n      name: updatedestination\n      operations:\n      - method: PATCH\n \
  \       name: updatedestination\n        description: Update destination\n        call: segment.updatedestination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceName}/sources/{sourceName}/destinations/{destinationName}\n      name: deletedestination\n      operations:\n      - method: DELETE\n        name: deletedestination\n        description: Delete destination\n        call: segment.deletedestination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceName}/tracking-plans\n      name: listtrackingplans\n      operations:\n      - method: GET\n        name: listtrackingplans\n        description: List tracking plans\n        call: segment.listtrackingplans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceName}/tracking-plans\n      name: createtrackingplan\n      operations:\n      - method: POST\n        name:\
  \ createtrackingplan\n        description: Create tracking plan\n        call: segment.createtrackingplan\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: segment-mcp\n    transport: http\n    description: MCP adapter for Segment Config API for AI agent use.\n    tools:\n    - name: getworkspace\n      description: Get workspace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: segment.getworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsources\n      description: List sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: segment.listsources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsource\n      description: Create source\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: segment.createsource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsource\n      description: Get source\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: segment.getsource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesource\n      description: Delete source\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: segment.deletesource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdestinations\n      description: List destinations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: segment.listdestinations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdestination\n      description: Create destination\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: segment.createdestination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdestination\n      description: Get destination\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: segment.getdestination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedestination\n      description: Update destination\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: segment.updatedestination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedestination\n      description: Delete destination\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: segment.deletedestination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtrackingplans\n      description: List tracking plans\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: segment.listtrackingplans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtrackingplan\n      description: Create tracking plan\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: segment.createtrackingplan\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    SEGMENT_TOKEN: SEGMENT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/segment/refs/heads/main/capabilities/segment-capability.yaml
tags:
- Segment
- API
tools:
- description: Get workspace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkspace
- description: List sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsources
- description: Create source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsource
- description: Get source
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsource
- description: Delete source
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesource
- description: List destinations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdestinations
- description: Create destination
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdestination
- description: Get destination
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdestination
- description: Update destination
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedestination
- description: Delete destination
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedestination
- description: List tracking plans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtrackingplans
- description: Create tracking plan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtrackingplan
---

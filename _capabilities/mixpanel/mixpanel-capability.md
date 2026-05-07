---
categories: []
consumed_apis: []
description: API for creating, retrieving, updating, and deleting annotations that label specific points in time on Mixpanel charts with descriptions, useful for marking product launches, campaigns, or data anomalies.
layout: capability
name: Mixpanel Annotations API
operations:
- description: Mixpanel List annotations
  method: GET
  name: listannotations
  path: /projects/{projectId}/annotations
- description: Mixpanel Create annotation
  method: POST
  name: createannotation
  path: /projects/{projectId}/annotations
- description: Mixpanel Get annotation
  method: GET
  name: getannotation
  path: /projects/{projectId}/annotations/{annotationId}
- description: Mixpanel Update annotation
  method: PUT
  name: updateannotation
  path: /projects/{projectId}/annotations/{annotationId}
- description: Mixpanel Delete annotation
  method: DELETE
  name: deleteannotation
  path: /projects/{projectId}/annotations/{annotationId}
personas: []
provider_name: Mixpanel
provider_slug: mixpanel
search_terms:
- product analytics
- analytics
- mixpanel get annotation
- event tracking
- data analysis
- updateannotation
- mixpanel list annotations
- mixpanel
- getannotation
- createannotation
- deleteannotation
- user behavior
- listannotations
- api
- mixpanel create annotation
- mixpanel update annotation
- mixpanel delete annotation
slug: mixpanel-capability
source_filename: mixpanel-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mixpanel Annotations API\n  description: API for creating, retrieving, updating, and deleting annotations that label specific points in time on Mixpanel\n    charts with descriptions, useful for marking product launches, campaigns, or data anomalies.\n  tags:\n  - Mixpanel\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mixpanel\n    baseUri: https://mixpanel.com/api/app\n    description: Mixpanel Annotations API HTTP API.\n    authentication:\n      type: basic\n      username: '{{MIXPANEL_USERNAME}}'\n      password: '{{MIXPANEL_PASSWORD}}'\n    resources:\n    - name: projects-projectid-annotations\n      path: /projects/{projectId}/annotations\n      operations:\n      - name: listannotations\n        method: GET\n        description: Mixpanel List annotations\n        inputParameters:\n        - name: from_date\n          in: query\n          type: string\n    \
  \      description: Start date filter (YYYY-MM-DD)\n        - name: to_date\n          in: query\n          type: string\n          description: End date filter (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createannotation\n        method: POST\n        description: Mixpanel Create annotation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-annotations-annotationid\n      path: /projects/{projectId}/annotations/{annotationId}\n      operations:\n      - name: getannotation\n        method: GET\n        description: Mixpanel Get annotation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateannotation\n        method: PUT\n        description: Mixpanel Update annotation\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteannotation\n        method: DELETE\n        description: Mixpanel Delete annotation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mixpanel-rest\n    description: REST adapter for Mixpanel Annotations API.\n    resources:\n    - path: /projects/{projectId}/annotations\n      name: listannotations\n      operations:\n      - method: GET\n        name: listannotations\n        description: Mixpanel List annotations\n        call: mixpanel.listannotations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/annotations\n      name: createannotation\n      operations:\n      - method: POST\n        name: createannotation\n        description: Mixpanel Create\
  \ annotation\n        call: mixpanel.createannotation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/annotations/{annotationId}\n      name: getannotation\n      operations:\n      - method: GET\n        name: getannotation\n        description: Mixpanel Get annotation\n        call: mixpanel.getannotation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/annotations/{annotationId}\n      name: updateannotation\n      operations:\n      - method: PUT\n        name: updateannotation\n        description: Mixpanel Update annotation\n        call: mixpanel.updateannotation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/annotations/{annotationId}\n      name: deleteannotation\n      operations:\n      - method: DELETE\n        name: deleteannotation\n        description: Mixpanel Delete annotation\n        call:\
  \ mixpanel.deleteannotation\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mixpanel-mcp\n    transport: http\n    description: MCP adapter for Mixpanel Annotations API for AI agent use.\n    tools:\n    - name: listannotations\n      description: Mixpanel List annotations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mixpanel.listannotations\n      with:\n        from_date: tools.from_date\n        to_date: tools.to_date\n      inputParameters:\n      - name: from_date\n        type: string\n        description: Start date filter (YYYY-MM-DD)\n      - name: to_date\n        type: string\n        description: End date filter (YYYY-MM-DD)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createannotation\n      description: Mixpanel Create annotation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: mixpanel.createannotation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getannotation\n      description: Mixpanel Get annotation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mixpanel.getannotation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateannotation\n      description: Mixpanel Update annotation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mixpanel.updateannotation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteannotation\n      description: Mixpanel Delete annotation\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: mixpanel.deleteannotation\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MIXPANEL_USERNAME: MIXPANEL_USERNAME\n\
  \    MIXPANEL_PASSWORD: MIXPANEL_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mixpanel/refs/heads/main/capabilities/mixpanel-capability.yaml
tags:
- Mixpanel
- API
tools:
- description: Mixpanel List annotations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listannotations
- description: Mixpanel Create annotation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createannotation
- description: Mixpanel Get annotation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getannotation
- description: Mixpanel Update annotation
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateannotation
- description: Mixpanel Delete annotation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteannotation
---

---
categories: []
consumed_apis: []
description: Manages Cloud CDN resources including backend services with CDN enabled, URL maps, and cache invalidation through the Compute Engine API.
layout: capability
name: Google Cloud CDN API
operations:
- description: Google Cloud CDN List Backend Services
  method: GET
  name: listbackendservices
  path: /projects/{project}/global/backendServices
- description: Google Cloud CDN Create Backend Service
  method: POST
  name: insertbackendservice
  path: /projects/{project}/global/backendServices
- description: Google Cloud CDN Get Backend Service
  method: GET
  name: getbackendservice
  path: /projects/{project}/global/backendServices/{backendService}
- description: Google Cloud CDN Update Backend Service
  method: PATCH
  name: patchbackendservice
  path: /projects/{project}/global/backendServices/{backendService}
- description: Google Cloud CDN Delete Backend Service
  method: DELETE
  name: deletebackendservice
  path: /projects/{project}/global/backendServices/{backendService}
- description: Google Cloud CDN List URL Maps
  method: GET
  name: listurlmaps
  path: /projects/{project}/global/urlMaps
- description: Google Cloud CDN Invalidate Cache
  method: POST
  name: invalidatecache
  path: /projects/{project}/global/backendServices/{backendService}/invalidateCache
personas: []
provider_name: Google Cloud CDN
provider_slug: google-cloud-cdn
search_terms:
- networking
- invalidatecache
- google cloud cdn invalidate cache
- google cloud cdn create backend service
- google cloud cdn update backend service
- patchbackendservice
- deletebackendservice
- cloud
- google
- listbackendservices
- google cloud cdn list backend services
- getbackendservice
- google cloud cdn get backend service
- content delivery
- cdn
- api
- caching
- insertbackendservice
- google cloud cdn delete backend service
- google cloud cdn list url maps
- google cloud
- listurlmaps
slug: google-cloud-cdn-capability
source_filename: google-cloud-cdn-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud CDN API\n  description: Manages Cloud CDN resources including backend services with CDN enabled, URL maps, and cache invalidation through\n    the Compute Engine API.\n  tags:\n  - Google\n  - Cloud\n  - Cdn\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-cdn\n    baseUri: https://compute.googleapis.com/compute/v1\n    description: Google Cloud CDN API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_CDN_TOKEN}}'\n    resources:\n    - name: projects-project-global-backendservices\n      path: /projects/{project}/global/backendServices\n      operations:\n      - name: listbackendservices\n        method: GET\n        description: Google Cloud CDN List Backend Services\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertbackendservice\n        method: POST\n        description: Google Cloud CDN Create Backend Service\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-backendservices-backends\n      path: /projects/{project}/global/backendServices/{backendService}\n      operations:\n      - name: getbackendservice\n        method: GET\n        description: Google Cloud CDN Get Backend Service\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: backendService\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchbackendservice\n        method: PATCH\n        description: Google Cloud CDN Update Backend Service\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: backendService\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebackendservice\n        method: DELETE\n        description: Google Cloud CDN Delete Backend Service\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: backendService\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: projects-project-global-urlmaps\n      path: /projects/{project}/global/urlMaps\n      operations:\n      - name: listurlmaps\n        method: GET\n        description: Google Cloud CDN List URL Maps\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-backendservices-backends\n      path: /projects/{project}/global/backendServices/{backendService}/invalidateCache\n      operations:\n      - name: invalidatecache\n        method: POST\n        description: Google Cloud CDN Invalidate Cache\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: backendService\n          in: path\n          type: string\n          required: true\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-cdn-rest\n    description: REST adapter for Google Cloud CDN API.\n    resources:\n    - path: /projects/{project}/global/backendServices\n      name: listbackendservices\n      operations:\n      - method: GET\n        name: listbackendservices\n        description: Google Cloud CDN List Backend Services\n        call: google-cloud-cdn.listbackendservices\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/backendServices\n      name: insertbackendservice\n      operations:\n      - method: POST\n        name: insertbackendservice\n        description: Google Cloud CDN Create Backend Service\n        call: google-cloud-cdn.insertbackendservice\n        with:\n          project: rest.project\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/backendServices/{backendService}\n      name: getbackendservice\n      operations:\n      - method: GET\n        name: getbackendservice\n        description: Google Cloud CDN Get Backend Service\n        call: google-cloud-cdn.getbackendservice\n        with:\n          project: rest.project\n          backendService: rest.backendService\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/backendServices/{backendService}\n      name: patchbackendservice\n      operations:\n      - method: PATCH\n        name: patchbackendservice\n        description: Google Cloud CDN Update Backend Service\n        call: google-cloud-cdn.patchbackendservice\n        with:\n          project: rest.project\n          backendService: rest.backendService\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /projects/{project}/global/backendServices/{backendService}\n      name: deletebackendservice\n      operations:\n      - method: DELETE\n        name: deletebackendservice\n        description: Google Cloud CDN Delete Backend Service\n        call: google-cloud-cdn.deletebackendservice\n        with:\n          project: rest.project\n          backendService: rest.backendService\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/urlMaps\n      name: listurlmaps\n      operations:\n      - method: GET\n        name: listurlmaps\n        description: Google Cloud CDN List URL Maps\n        call: google-cloud-cdn.listurlmaps\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/backendServices/{backendService}/invalidateCache\n      name: invalidatecache\n      operations:\n      - method: POST\n        name:\
  \ invalidatecache\n        description: Google Cloud CDN Invalidate Cache\n        call: google-cloud-cdn.invalidatecache\n        with:\n          project: rest.project\n          backendService: rest.backendService\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-cdn-mcp\n    transport: http\n    description: MCP adapter for Google Cloud CDN API for AI agent use.\n    tools:\n    - name: listbackendservices\n      description: Google Cloud CDN List Backend Services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-cdn.listbackendservices\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertbackendservice\n      description: Google Cloud\
  \ CDN Create Backend Service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-cdn.insertbackendservice\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbackendservice\n      description: Google Cloud CDN Get Backend Service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-cdn.getbackendservice\n      with:\n        project: tools.project\n        backendService: tools.backendService\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: backendService\n        type: string\n        description: backendService\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: patchbackendservice\n      description: Google Cloud CDN Update Backend Service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-cdn.patchbackendservice\n      with:\n        project: tools.project\n        backendService: tools.backendService\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: backendService\n        type: string\n        description: backendService\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebackendservice\n      description: Google Cloud CDN Delete Backend Service\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-cdn.deletebackendservice\n      with:\n        project: tools.project\n        backendService: tools.backendService\n      inputParameters:\n\
  \      - name: project\n        type: string\n        description: project\n        required: true\n      - name: backendService\n        type: string\n        description: backendService\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listurlmaps\n      description: Google Cloud CDN List URL Maps\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-cdn.listurlmaps\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: invalidatecache\n      description: Google Cloud CDN Invalidate Cache\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-cdn.invalidatecache\n      with:\n        project: tools.project\n    \
  \    backendService: tools.backendService\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: backendService\n        type: string\n        description: backendService\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_CDN_TOKEN: GOOGLE_CLOUD_CDN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-cdn/refs/heads/main/capabilities/google-cloud-cdn-capability.yaml
tags:
- Google
- Cloud
- Cdn
- API
tools:
- description: Google Cloud CDN List Backend Services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbackendservices
- description: Google Cloud CDN Create Backend Service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertbackendservice
- description: Google Cloud CDN Get Backend Service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbackendservice
- description: Google Cloud CDN Update Backend Service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchbackendservice
- description: Google Cloud CDN Delete Backend Service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebackendservice
- description: Google Cloud CDN List URL Maps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listurlmaps
- description: Google Cloud CDN Invalidate Cache
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invalidatecache
---

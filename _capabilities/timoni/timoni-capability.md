---
categories: []
consumed_apis: []
description: Timoni is a package manager for Kubernetes powered by CUE that provides type-safe alternatives to Helm charts. Timoni modules are distributed as OCI artifacts in container registries. This API describes the OCI registry operations used for module distribution, versioning, and artifact management within the Timoni ecosystem.
layout: capability
name: Timoni Module Registry API
operations:
- description: List Module Tags
  method: GET
  name: listmoduletags
  path: /v2/{registry}/{module}/tags/list
- description: Get Module Manifest
  method: GET
  name: getmodulemanifest
  path: /v2/{registry}/{module}/manifests/{reference}
- description: Get Module Blob
  method: GET
  name: getmoduleblob
  path: /v2/{registry}/{module}/blobs/{digest}
personas: []
provider_name: Timoni
provider_slug: timoni
search_terms:
- get module manifest
- package manager
- containers
- cue
- kubernetes
- list module tags
- listmoduletags
- api
- getmoduleblob
- getmodulemanifest
- timoni
- get module blob
slug: timoni-capability
source_filename: timoni-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Timoni Module Registry API\n  description: Timoni is a package manager for Kubernetes powered by CUE that provides type-safe alternatives to Helm charts.\n    Timoni modules are distributed as OCI artifacts in container registries. This API describes the OCI registry operations\n    used for module distribution, versioning, and artifact management within the Timoni ecosystem.\n  tags:\n  - Timoni\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: timoni\n    baseUri: https://ghcr.io\n    description: Timoni Module Registry API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{TIMONI_TOKEN}}'\n    resources:\n    - name: v2-registry-module-tags-list\n      path: /v2/{registry}/{module}/tags/list\n      operations:\n      - name: listmoduletags\n        method: GET\n        description: List Module Tags\n        inputParameters:\n        - name: registry\n\
  \          in: path\n          type: string\n          required: true\n          description: Registry namespace or organization\n        - name: module\n          in: path\n          type: string\n          required: true\n          description: Module name\n        - name: n\n          in: query\n          type: integer\n          description: Maximum number of tags to return\n        - name: last\n          in: query\n          type: string\n          description: Last tag for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-registry-module-manifests-reference\n      path: /v2/{registry}/{module}/manifests/{reference}\n      operations:\n      - name: getmodulemanifest\n        method: GET\n        description: Get Module Manifest\n        inputParameters:\n        - name: registry\n          in: path\n          type: string\n          required: true\n        - name: module\n   \
  \       in: path\n          type: string\n          required: true\n        - name: reference\n          in: path\n          type: string\n          required: true\n          description: Tag (e.g., v1.0.0) or digest (sha256:...)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-registry-module-blobs-digest\n      path: /v2/{registry}/{module}/blobs/{digest}\n      operations:\n      - name: getmoduleblob\n        method: GET\n        description: Get Module Blob\n        inputParameters:\n        - name: registry\n          in: path\n          type: string\n          required: true\n        - name: module\n          in: path\n          type: string\n          required: true\n        - name: digest\n          in: path\n          type: string\n          required: true\n          description: Blob digest in format sha256:<hash>\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: timoni-rest\n    description: REST adapter for Timoni Module Registry API.\n    resources:\n    - path: /v2/{registry}/{module}/tags/list\n      name: listmoduletags\n      operations:\n      - method: GET\n        name: listmoduletags\n        description: List Module Tags\n        call: timoni.listmoduletags\n        with:\n          registry: rest.registry\n          module: rest.module\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{registry}/{module}/manifests/{reference}\n      name: getmodulemanifest\n      operations:\n      - method: GET\n        name: getmodulemanifest\n        description: Get Module Manifest\n        call: timoni.getmodulemanifest\n        with:\n          registry: rest.registry\n          module: rest.module\n          reference: rest.reference\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v2/{registry}/{module}/blobs/{digest}\n      name: getmoduleblob\n      operations:\n      - method: GET\n        name: getmoduleblob\n        description: Get Module Blob\n        call: timoni.getmoduleblob\n        with:\n          registry: rest.registry\n          module: rest.module\n          digest: rest.digest\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: timoni-mcp\n    transport: http\n    description: MCP adapter for Timoni Module Registry API for AI agent use.\n    tools:\n    - name: listmoduletags\n      description: List Module Tags\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: timoni.listmoduletags\n      with:\n        registry: tools.registry\n        module: tools.module\n        n: tools.n\n        last: tools.last\n      inputParameters:\n      - name: registry\n        type: string\n        description:\
  \ Registry namespace or organization\n        required: true\n      - name: module\n        type: string\n        description: Module name\n        required: true\n      - name: n\n        type: integer\n        description: Maximum number of tags to return\n      - name: last\n        type: string\n        description: Last tag for pagination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmodulemanifest\n      description: Get Module Manifest\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: timoni.getmodulemanifest\n      with:\n        registry: tools.registry\n        module: tools.module\n        reference: tools.reference\n      inputParameters:\n      - name: registry\n        type: string\n        description: registry\n        required: true\n      - name: module\n        type: string\n        description: module\n        required: true\n      - name: reference\n        type: string\n \
  \       description: Tag (e.g., v1.0.0) or digest (sha256:...)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmoduleblob\n      description: Get Module Blob\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: timoni.getmoduleblob\n      with:\n        registry: tools.registry\n        module: tools.module\n        digest: tools.digest\n      inputParameters:\n      - name: registry\n        type: string\n        description: registry\n        required: true\n      - name: module\n        type: string\n        description: module\n        required: true\n      - name: digest\n        type: string\n        description: Blob digest in format sha256:<hash>\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    TIMONI_TOKEN: TIMONI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/timoni/refs/heads/main/capabilities/timoni-capability.yaml
tags:
- Timoni
- API
tools:
- description: List Module Tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmoduletags
- description: Get Module Manifest
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmodulemanifest
- description: Get Module Blob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmoduleblob
---

---
categories: []
consumed_apis: []
description: The Container Registry API provides access to store, manage, and secure Docker container images. It supports pushing and pulling images, managing image tags, and integrating with vulnerability scanning and binary authorization services.
layout: capability
name: Google Cloud Container Registry API
operations:
- description: Google Cloud Container Registry List Image Tags
  method: GET
  name: listtags
  path: /v2/{name}/tags/list
- description: Google Cloud Container Registry Get Image Manifest
  method: GET
  name: getmanifest
  path: /v2/{name}/manifests/{reference}
- description: Google Cloud Container Registry Push Image Manifest
  method: PUT
  name: putmanifest
  path: /v2/{name}/manifests/{reference}
- description: Google Cloud Container Registry Delete Image Manifest
  method: DELETE
  name: deletemanifest
  path: /v2/{name}/manifests/{reference}
- description: Google Cloud Container Registry List Repositories
  method: GET
  name: listcatalog
  path: /v2/_catalog
- description: Google Cloud Container Registry Get Image Blob
  method: GET
  name: getblob
  path: /v2/{name}/blobs/{digest}
personas: []
provider_name: Google Cloud Container Registry
provider_slug: google-cloud-container-registry
search_terms:
- google cloud container registry get image manifest
- containers
- listcatalog
- google cloud container registry delete image manifest
- ci/cd
- api
- getmanifest
- deletemanifest
- registry
- google cloud container registry push image manifest
- google
- registries
- listtags
- getblob
- container
- google cloud container registry list repositories
- putmanifest
- cloud
- storage
- images
- google cloud container registry get image blob
- google cloud container registry list image tags
- google cloud
- docker
slug: google-cloud-container-registry-capability
source_filename: google-cloud-container-registry-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Container Registry API\n  description: The Container Registry API provides access to store, manage, and secure Docker container images. It supports\n    pushing and pulling images, managing image tags, and integrating with vulnerability scanning and binary authorization\n    services.\n  tags:\n  - Google\n  - Cloud\n  - Container\n  - Registry\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-container-registry\n    baseUri: https://containerregistry.googleapis.com\n    description: Google Cloud Container Registry API HTTP API.\n    resources:\n    - name: v2-name-tags-list\n      path: /v2/{name}/tags/list\n      operations:\n      - name: listtags\n        method: GET\n        description: Google Cloud Container Registry List Image Tags\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required:\
  \ true\n          description: The name of the image.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-name-manifests-reference\n      path: /v2/{name}/manifests/{reference}\n      operations:\n      - name: getmanifest\n        method: GET\n        description: Google Cloud Container Registry Get Image Manifest\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: reference\n          in: path\n          type: string\n          required: true\n          description: The tag or digest of the image.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putmanifest\n        method: PUT\n        description: Google Cloud Container Registry Push Image Manifest\n        inputParameters:\n        - name: name\n          in: path\n  \
  \        type: string\n          required: true\n        - name: reference\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemanifest\n        method: DELETE\n        description: Google Cloud Container Registry Delete Image Manifest\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: reference\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-catalog\n      path: /v2/_catalog\n      operations:\n      - name: listcatalog\n        method: GET\n        description: Google Cloud Container Registry List Repositories\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: v2-name-blobs-digest\n      path: /v2/{name}/blobs/{digest}\n      operations:\n      - name: getblob\n        method: GET\n        description: Google Cloud Container Registry Get Image Blob\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: digest\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-container-registry-rest\n    description: REST adapter for Google Cloud Container Registry API.\n    resources:\n    - path: /v2/{name}/tags/list\n      name: listtags\n      operations:\n      - method: GET\n        name: listtags\n        description: Google Cloud Container Registry List Image Tags\n        call: google-cloud-container-registry.listtags\n\
  \        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/manifests/{reference}\n      name: getmanifest\n      operations:\n      - method: GET\n        name: getmanifest\n        description: Google Cloud Container Registry Get Image Manifest\n        call: google-cloud-container-registry.getmanifest\n        with:\n          name: rest.name\n          reference: rest.reference\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/manifests/{reference}\n      name: putmanifest\n      operations:\n      - method: PUT\n        name: putmanifest\n        description: Google Cloud Container Registry Push Image Manifest\n        call: google-cloud-container-registry.putmanifest\n        with:\n          name: rest.name\n          reference: rest.reference\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/manifests/{reference}\n\
  \      name: deletemanifest\n      operations:\n      - method: DELETE\n        name: deletemanifest\n        description: Google Cloud Container Registry Delete Image Manifest\n        call: google-cloud-container-registry.deletemanifest\n        with:\n          name: rest.name\n          reference: rest.reference\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/_catalog\n      name: listcatalog\n      operations:\n      - method: GET\n        name: listcatalog\n        description: Google Cloud Container Registry List Repositories\n        call: google-cloud-container-registry.listcatalog\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/blobs/{digest}\n      name: getblob\n      operations:\n      - method: GET\n        name: getblob\n        description: Google Cloud Container Registry Get Image Blob\n        call: google-cloud-container-registry.getblob\n        with:\n          name: rest.name\n\
  \          digest: rest.digest\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-container-registry-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Container Registry API for AI agent use.\n    tools:\n    - name: listtags\n      description: Google Cloud Container Registry List Image Tags\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-container-registry.listtags\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: The name of the image.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmanifest\n      description: Google Cloud Container Registry Get Image Manifest\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-container-registry.getmanifest\n\
  \      with:\n        name: tools.name\n        reference: tools.reference\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: reference\n        type: string\n        description: The tag or digest of the image.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putmanifest\n      description: Google Cloud Container Registry Push Image Manifest\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-cloud-container-registry.putmanifest\n      with:\n        name: tools.name\n        reference: tools.reference\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: reference\n        type: string\n        description: reference\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: deletemanifest\n      description: Google Cloud Container Registry Delete Image Manifest\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-container-registry.deletemanifest\n      with:\n        name: tools.name\n        reference: tools.reference\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: reference\n        type: string\n        description: reference\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcatalog\n      description: Google Cloud Container Registry List Repositories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-container-registry.listcatalog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getblob\n      description: Google Cloud Container Registry Get\
  \ Image Blob\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-container-registry.getblob\n      with:\n        name: tools.name\n        digest: tools.digest\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: digest\n        type: string\n        description: digest\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-container-registry/refs/heads/main/capabilities/google-cloud-container-registry-capability.yaml
tags:
- Google
- Cloud
- Container
- Registry
- API
tools:
- description: Google Cloud Container Registry List Image Tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtags
- description: Google Cloud Container Registry Get Image Manifest
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmanifest
- description: Google Cloud Container Registry Push Image Manifest
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmanifest
- description: Google Cloud Container Registry Delete Image Manifest
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemanifest
- description: Google Cloud Container Registry List Repositories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcatalog
- description: Google Cloud Container Registry Get Image Blob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblob
---

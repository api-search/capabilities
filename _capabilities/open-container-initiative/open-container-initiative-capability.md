---
categories: []
consumed_apis: []
description: The Open Container Initiative Distribution Specification standardizes the HTTP API for distributing container images and other content. Registries that implement this specification expose endpoints for managing blobs, manifests, tags, and referrers under the /v2/ namespace.
layout: capability
name: OCI Distribution Specification
operations:
- description: API version check
  method: GET
  name: checkversion
  path: /v2/
- description: Retrieve a blob
  method: GET
  name: getblob
  path: /v2/{name}/blobs/{digest}
- description: Delete a blob
  method: DELETE
  name: deleteblob
  path: /v2/{name}/blobs/{digest}
- description: Initiate a blob upload
  method: POST
  name: initiateblobupload
  path: /v2/{name}/blobs/uploads/
- description: Get blob upload status
  method: GET
  name: getblobuploadstatus
  path: /v2/{name}/blobs/uploads/{reference}
- description: Upload a blob chunk
  method: PATCH
  name: uploadblobchunk
  path: /v2/{name}/blobs/uploads/{reference}
- description: Complete a blob upload
  method: PUT
  name: completeblobupload
  path: /v2/{name}/blobs/uploads/{reference}
- description: Cancel a blob upload
  method: DELETE
  name: cancelblobupload
  path: /v2/{name}/blobs/uploads/{reference}
- description: Retrieve a manifest
  method: GET
  name: getmanifest
  path: /v2/{name}/manifests/{reference}
- description: Push a manifest
  method: PUT
  name: putmanifest
  path: /v2/{name}/manifests/{reference}
- description: Delete a manifest
  method: DELETE
  name: deletemanifest
  path: /v2/{name}/manifests/{reference}
- description: List tags in a repository
  method: GET
  name: listtags
  path: /v2/{name}/tags/list
- description: List referrers for a manifest
  method: GET
  name: listreferrers
  path: /v2/{name}/referrers/{digest}
personas: []
provider_name: Open Container Initiative
provider_slug: open-container-initiative
search_terms:
- listtags
- open
- list tags in a repository
- listreferrers
- deletemanifest
- container
- delete a manifest
- getblobuploadstatus
- containers
- deleteblob
- cloud native
- standards
- api version check
- open source
- list referrers for a manifest
- push a manifest
- api
- initiateblobupload
- complete a blob upload
- cancel a blob upload
- putmanifest
- delete a blob
- getmanifest
- completeblobupload
- checkversion
- uploadblobchunk
- cancelblobupload
- retrieve a manifest
- initiative
- retrieve a blob
- oci
- get blob upload status
- getblob
- initiate a blob upload
- upload a blob chunk
slug: open-container-initiative-capability
source_filename: open-container-initiative-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OCI Distribution Specification\n  description: The Open Container Initiative Distribution Specification standardizes the HTTP API for distributing container\n    images and other content. Registries that implement this specification expose endpoints for managing blobs, manifests,\n    tags, and referrers under the /v2/ namespace.\n  tags:\n  - Open\n  - Container\n  - Initiative\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: open-container-initiative\n    baseUri: https://registry.example.com\n    description: OCI Distribution Specification HTTP API.\n    resources:\n    - name: v2\n      path: /v2/\n      operations:\n      - name: checkversion\n        method: GET\n        description: API version check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-name-blobs-digest\n\
  \      path: /v2/{name}/blobs/{digest}\n      operations:\n      - name: getblob\n        method: GET\n        description: Retrieve a blob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteblob\n        method: DELETE\n        description: Delete a blob\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-name-blobs-uploads\n      path: /v2/{name}/blobs/uploads/\n      operations:\n      - name: initiateblobupload\n        method: POST\n        description: Initiate a blob upload\n        inputParameters:\n        - name: digest\n          in: query\n          type: string\n          description: When supplied, performs a monolithic upload with this digest.\n        - name: mount\n          in: query\n          type: string\n          description: Digest of a blob to mount from another repository.\n\
  \        - name: from\n          in: query\n          type: string\n          description: Source repository name to mount the blob from.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-name-blobs-uploads-reference\n      path: /v2/{name}/blobs/uploads/{reference}\n      operations:\n      - name: getblobuploadstatus\n        method: GET\n        description: Get blob upload status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadblobchunk\n        method: PATCH\n        description: Upload a blob chunk\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: completeblobupload\n        method: PUT\n        description: Complete a blob upload\n        inputParameters:\n        - name: digest\n          in: query\n\
  \          type: string\n          required: true\n          description: The digest of the completed blob.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancelblobupload\n        method: DELETE\n        description: Cancel a blob upload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-name-manifests-reference\n      path: /v2/{name}/manifests/{reference}\n      operations:\n      - name: getmanifest\n        method: GET\n        description: Retrieve a manifest\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putmanifest\n        method: PUT\n        description: Push a manifest\n        inputParameters:\n        - name: tag\n          in: query\n          type: array\n          description: Optional tags to\
  \ assign when pushing by digest.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemanifest\n        method: DELETE\n        description: Delete a manifest\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-name-tags-list\n      path: /v2/{name}/tags/list\n      operations:\n      - name: listtags\n        method: GET\n        description: List tags in a repository\n        inputParameters:\n        - name: n\n          in: query\n          type: integer\n          description: Maximum number of tags to return.\n        - name: last\n          in: query\n          type: string\n          description: Tag name to start listing after, for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-name-referrers-digest\n\
  \      path: /v2/{name}/referrers/{digest}\n      operations:\n      - name: listreferrers\n        method: GET\n        description: List referrers for a manifest\n        inputParameters:\n        - name: artifactType\n          in: query\n          type: string\n          description: Filter referrers by artifact type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: open-container-initiative-rest\n    description: REST adapter for OCI Distribution Specification.\n    resources:\n    - path: /v2/\n      name: checkversion\n      operations:\n      - method: GET\n        name: checkversion\n        description: API version check\n        call: open-container-initiative.checkversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/blobs/{digest}\n      name: getblob\n      operations:\n      - method:\
  \ GET\n        name: getblob\n        description: Retrieve a blob\n        call: open-container-initiative.getblob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/blobs/{digest}\n      name: deleteblob\n      operations:\n      - method: DELETE\n        name: deleteblob\n        description: Delete a blob\n        call: open-container-initiative.deleteblob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/blobs/uploads/\n      name: initiateblobupload\n      operations:\n      - method: POST\n        name: initiateblobupload\n        description: Initiate a blob upload\n        call: open-container-initiative.initiateblobupload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/blobs/uploads/{reference}\n      name: getblobuploadstatus\n      operations:\n      - method: GET\n        name: getblobuploadstatus\n        description: Get blob upload\
  \ status\n        call: open-container-initiative.getblobuploadstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/blobs/uploads/{reference}\n      name: uploadblobchunk\n      operations:\n      - method: PATCH\n        name: uploadblobchunk\n        description: Upload a blob chunk\n        call: open-container-initiative.uploadblobchunk\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/blobs/uploads/{reference}\n      name: completeblobupload\n      operations:\n      - method: PUT\n        name: completeblobupload\n        description: Complete a blob upload\n        call: open-container-initiative.completeblobupload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/blobs/uploads/{reference}\n      name: cancelblobupload\n      operations:\n      - method: DELETE\n        name: cancelblobupload\n        description: Cancel a blob upload\n\
  \        call: open-container-initiative.cancelblobupload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/manifests/{reference}\n      name: getmanifest\n      operations:\n      - method: GET\n        name: getmanifest\n        description: Retrieve a manifest\n        call: open-container-initiative.getmanifest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/manifests/{reference}\n      name: putmanifest\n      operations:\n      - method: PUT\n        name: putmanifest\n        description: Push a manifest\n        call: open-container-initiative.putmanifest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/manifests/{reference}\n      name: deletemanifest\n      operations:\n      - method: DELETE\n        name: deletemanifest\n        description: Delete a manifest\n        call: open-container-initiative.deletemanifest\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v2/{name}/tags/list\n      name: listtags\n      operations:\n      - method: GET\n        name: listtags\n        description: List tags in a repository\n        call: open-container-initiative.listtags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{name}/referrers/{digest}\n      name: listreferrers\n      operations:\n      - method: GET\n        name: listreferrers\n        description: List referrers for a manifest\n        call: open-container-initiative.listreferrers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: open-container-initiative-mcp\n    transport: http\n    description: MCP adapter for OCI Distribution Specification for AI agent use.\n    tools:\n    - name: checkversion\n      description: API version check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: open-container-initiative.checkversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getblob\n      description: Retrieve a blob\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-container-initiative.getblob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteblob\n      description: Delete a blob\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: open-container-initiative.deleteblob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiateblobupload\n      description: Initiate a blob upload\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: open-container-initiative.initiateblobupload\n      with:\n        digest: tools.digest\n        mount: tools.mount\n        from: tools.from\n      inputParameters:\n\
  \      - name: digest\n        type: string\n        description: When supplied, performs a monolithic upload with this digest.\n      - name: mount\n        type: string\n        description: Digest of a blob to mount from another repository.\n      - name: from\n        type: string\n        description: Source repository name to mount the blob from.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getblobuploadstatus\n      description: Get blob upload status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-container-initiative.getblobuploadstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadblobchunk\n      description: Upload a blob chunk\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: open-container-initiative.uploadblobchunk\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: completeblobupload\n      description: Complete a blob upload\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: open-container-initiative.completeblobupload\n      with:\n        digest: tools.digest\n      inputParameters:\n      - name: digest\n        type: string\n        description: The digest of the completed blob.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelblobupload\n      description: Cancel a blob upload\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: open-container-initiative.cancelblobupload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmanifest\n      description: Retrieve a manifest\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-container-initiative.getmanifest\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: putmanifest\n      description: Push a manifest\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: open-container-initiative.putmanifest\n      with:\n        tag: tools.tag\n      inputParameters:\n      - name: tag\n        type: array\n        description: Optional tags to assign when pushing by digest.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemanifest\n      description: Delete a manifest\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: open-container-initiative.deletemanifest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtags\n      description: List tags in a repository\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-container-initiative.listtags\n      with:\n        n:\
  \ tools.n\n        last: tools.last\n      inputParameters:\n      - name: n\n        type: integer\n        description: Maximum number of tags to return.\n      - name: last\n        type: string\n        description: Tag name to start listing after, for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreferrers\n      description: List referrers for a manifest\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-container-initiative.listreferrers\n      with:\n        artifactType: tools.artifactType\n      inputParameters:\n      - name: artifactType\n        type: string\n        description: Filter referrers by artifact type.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/open-container-initiative/refs/heads/main/capabilities/open-container-initiative-capability.yaml
tags:
- Open
- Container
- Initiative
- API
tools:
- description: API version check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: checkversion
- description: Retrieve a blob
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblob
- description: Delete a blob
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteblob
- description: Initiate a blob upload
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initiateblobupload
- description: Get blob upload status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblobuploadstatus
- description: Upload a blob chunk
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadblobchunk
- description: Complete a blob upload
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: completeblobupload
- description: Cancel a blob upload
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancelblobupload
- description: Retrieve a manifest
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmanifest
- description: Push a manifest
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmanifest
- description: Delete a manifest
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemanifest
- description: List tags in a repository
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtags
- description: List referrers for a manifest
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreferrers
---

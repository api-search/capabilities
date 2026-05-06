---
categories: []
consumed_apis: []
description: Unified capability for cloud-native storage orchestration on Kubernetes using Rook. Combines Ceph object storage management with S3-compatible access patterns for platform engineers, DevOps teams, and application developers managing persistent storage in Kubernetes clusters.
layout: capability
name: Rook Storage Orchestration
operations:
- description: List all S3 buckets in the Ceph Object Storage gateway
  method: GET
  name: list-buckets
  path: /v1/buckets
- description: Create a new S3 bucket in Ceph Object Storage
  method: POST
  name: create-bucket
  path: /v1/buckets
- description: Check bucket existence and access permissions
  method: GET
  name: check-bucket
  path: /v1/buckets/{bucket}
- description: Delete an empty S3 bucket
  method: DELETE
  name: delete-bucket
  path: /v1/buckets/{bucket}
- description: List objects in a bucket with optional prefix and pagination
  method: GET
  name: list-objects
  path: /v1/buckets/{bucket}/objects
- description: Download an object from Ceph object storage
  method: GET
  name: get-object
  path: /v1/buckets/{bucket}/objects/{key}
- description: Upload an object to Ceph object storage
  method: PUT
  name: put-object
  path: /v1/buckets/{bucket}/objects/{key}
- description: Delete an object from Ceph object storage
  method: DELETE
  name: delete-object
  path: /v1/buckets/{bucket}/objects/{key}
- description: Retrieve object metadata without downloading
  method: HEAD
  name: head-object
  path: /v1/buckets/{bucket}/objects/{key}
personas: []
provider_name: Rook
provider_slug: rook
search_terms:
- delete an object from ceph object storage
- file storage
- delete an object from rook ceph object storage
- storage
- object storage
- create a new s3 bucket in ceph object storage
- list buckets
- put object
- list objects in a bucket with optional prefix and pagination
- delete an empty s3 bucket
- single object operations
- manage s3-compatible buckets in ceph object storage
- retrieve metadata of a ceph object without downloading the content
- get object metadata
- list objects
- cloud native
- block storage
- check bucket
- kubernetes
- list all s3 buckets in the ceph object storage gateway managed by rook
- manage objects within a ceph bucket
- list objects in a rook ceph bucket with optional prefix filter and pagination
- orchestration
- retrieve object metadata without downloading
- upload an object to ceph object storage
- download an object from ceph object storage
- upload an object to rook ceph object storage
- cncf
- create a new s3-compatible bucket in rook ceph object storage
- delete an empty ceph bucket managed by rook
- get object
- check bucket existence and access permissions
- delete object
- download an object from rook ceph object storage
- list all s3 buckets in the ceph object storage gateway
- head object
- create bucket
- single bucket operations
- graduated
- delete bucket
- ceph
slug: storage-orchestration
source_filename: storage-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rook Storage Orchestration\n  description: Unified capability for cloud-native storage orchestration on Kubernetes using Rook. Combines Ceph object storage\n    management with S3-compatible access patterns for platform engineers, DevOps teams, and application developers managing\n    persistent storage in Kubernetes clusters.\n  tags:\n  - Block Storage\n  - CNCF\n  - Ceph\n  - Cloud Native\n  - File Storage\n  - Kubernetes\n  - Object Storage\n  - Storage\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ROOK_S3_ACCESS_KEY: ROOK_S3_ACCESS_KEY\n    ROOK_S3_SECRET_KEY: ROOK_S3_SECRET_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ceph-object-storage\n    baseUri: http://rook-ceph-rgw-my-store.rook-ceph.svc\n    description: S3-compatible Ceph Object Storage gateway managed by Rook\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{ROOK_S3_ACCESS_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: buckets\n      path: /\n      description: S3 bucket management operations\n      operations:\n      - name: list-buckets\n        method: GET\n        description: List all buckets owned by the authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-bucket\n        method: PUT\n        description: Create a new S3 bucket\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Name of the bucket to create\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-bucket\n        method: DELETE\n        description: Delete an empty S3 bucket\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required:\
  \ true\n          description: Name of the bucket to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: head-bucket\n        method: HEAD\n        description: Check bucket existence and access permissions\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Name of the bucket to check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: objects\n      path: /{bucket}\n      description: S3 object operations within a bucket\n      operations:\n      - name: list-objects\n        method: GET\n        description: List objects in a bucket with optional prefix and pagination\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket\
  \ name\n        - name: prefix\n          in: query\n          type: string\n          required: false\n          description: Filter objects by key prefix\n        - name: max-keys\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of keys to return\n        - name: list-type\n          in: query\n          type: integer\n          required: false\n          description: Use 2 for List Objects V2\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-object\n        method: PUT\n        description: Upload an object to a bucket\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Object key\n        body:\n          type:\
  \ binary\n          data:\n            content: '{{tools.object_data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-object\n        method: GET\n        description: Download an object from a bucket\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Object key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-object\n        method: DELETE\n        description: Delete an object from a bucket\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        - name: key\n     \
  \     in: path\n          type: string\n          required: true\n          description: Object key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: head-object\n        method: HEAD\n        description: Retrieve object metadata without downloading content\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Object key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: rook-storage-api\n    description: Unified REST API for Rook cloud-native storage orchestration on Kubernetes.\n    resources:\n    - path: /v1/buckets\n      name: buckets\n     \
  \ description: Manage S3-compatible buckets in Ceph Object Storage\n      operations:\n      - method: GET\n        name: list-buckets\n        description: List all S3 buckets in the Ceph Object Storage gateway\n        call: ceph-object-storage.list-buckets\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-bucket\n        description: Create a new S3 bucket in Ceph Object Storage\n        call: ceph-object-storage.create-bucket\n        with:\n          bucket: rest.bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucket}\n      name: bucket\n      description: Single bucket operations\n      operations:\n      - method: GET\n        name: check-bucket\n        description: Check bucket existence and access permissions\n        call: ceph-object-storage.head-bucket\n        with:\n          bucket: rest.bucket\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: DELETE\n        name: delete-bucket\n        description: Delete an empty S3 bucket\n        call: ceph-object-storage.delete-bucket\n        with:\n          bucket: rest.bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucket}/objects\n      name: objects\n      description: Manage objects within a Ceph bucket\n      operations:\n      - method: GET\n        name: list-objects\n        description: List objects in a bucket with optional prefix and pagination\n        call: ceph-object-storage.list-objects\n        with:\n          bucket: rest.bucket\n          prefix: rest.prefix\n          max-keys: rest.max_keys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucket}/objects/{key}\n      name: object\n      description: Single object operations\n      operations:\n      - method: GET\n        name: get-object\n        description: Download\
  \ an object from Ceph object storage\n        call: ceph-object-storage.get-object\n        with:\n          bucket: rest.bucket\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: put-object\n        description: Upload an object to Ceph object storage\n        call: ceph-object-storage.put-object\n        with:\n          bucket: rest.bucket\n          key: rest.key\n          object_data: rest.body\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-object\n        description: Delete an object from Ceph object storage\n        call: ceph-object-storage.delete-object\n        with:\n          bucket: rest.bucket\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: HEAD\n        name: head-object\n        description: Retrieve object metadata without downloading\n        call:\
  \ ceph-object-storage.head-object\n        with:\n          bucket: rest.bucket\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: rook-storage-mcp\n    transport: http\n    description: MCP server for AI-assisted Rook cloud-native storage orchestration on Kubernetes.\n    tools:\n    - name: list-buckets\n      description: List all S3 buckets in the Ceph Object Storage gateway managed by Rook\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ceph-object-storage.list-buckets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bucket\n      description: Create a new S3-compatible bucket in Rook Ceph Object Storage\n      hints:\n        readOnly: false\n        openWorld: false\n      call: ceph-object-storage.create-bucket\n      with:\n        bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: delete-bucket\n      description: Delete an empty Ceph bucket managed by Rook\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ceph-object-storage.delete-bucket\n      with:\n        bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-objects\n      description: List objects in a Rook Ceph bucket with optional prefix filter and pagination\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ceph-object-storage.list-objects\n      with:\n        bucket: tools.bucket\n        prefix: tools.prefix\n        max-keys: tools.max_keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-object\n      description: Download an object from Rook Ceph object storage\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ceph-object-storage.get-object\n      with:\n        bucket: tools.bucket\n\
  \        key: tools.key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-object\n      description: Upload an object to Rook Ceph object storage\n      hints:\n        readOnly: false\n        openWorld: false\n      call: ceph-object-storage.put-object\n      with:\n        bucket: tools.bucket\n        key: tools.key\n        object_data: tools.object_data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-object\n      description: Delete an object from Rook Ceph object storage\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ceph-object-storage.delete-object\n      with:\n        bucket: tools.bucket\n        key: tools.key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-object-metadata\n      description: Retrieve metadata of a Ceph object without downloading the content\n      hints:\n        readOnly: true\n       \
  \ openWorld: false\n      call: ceph-object-storage.head-object\n      with:\n        bucket: tools.bucket\n        key: tools.key\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rook/refs/heads/main/capabilities/storage-orchestration.yaml
tags:
- Block Storage
- CNCF
- Ceph
- Cloud Native
- File Storage
- Kubernetes
- Object Storage
- Storage
tools:
- description: List all S3 buckets in the Ceph Object Storage gateway managed by Rook
  hints:
    openWorld: false
    readOnly: true
  name: list-buckets
- description: Create a new S3-compatible bucket in Rook Ceph Object Storage
  hints:
    openWorld: false
    readOnly: false
  name: create-bucket
- description: Delete an empty Ceph bucket managed by Rook
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-bucket
- description: List objects in a Rook Ceph bucket with optional prefix filter and pagination
  hints:
    openWorld: false
    readOnly: true
  name: list-objects
- description: Download an object from Rook Ceph object storage
  hints:
    openWorld: false
    readOnly: true
  name: get-object
- description: Upload an object to Rook Ceph object storage
  hints:
    openWorld: false
    readOnly: false
  name: put-object
- description: Delete an object from Rook Ceph object storage
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-object
- description: Retrieve metadata of a Ceph object without downloading the content
  hints:
    openWorld: false
    readOnly: true
  name: get-object-metadata
---

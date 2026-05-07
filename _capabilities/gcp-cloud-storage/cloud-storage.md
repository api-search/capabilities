---
categories:
- object-storage
consumed_apis: []
description: Unified workflow for managing cloud storage buckets, objects, access controls, and IAM policies. Used by cloud engineers and data platform teams.
layout: capability
name: Google Cloud Storage Management
operations:
- description: List buckets.
  method: GET
  name: list-buckets
  path: /v1/buckets
- description: Create a bucket.
  method: POST
  name: create-bucket
  path: /v1/buckets
- description: Get bucket details.
  method: GET
  name: get-bucket
  path: /v1/buckets/{id}
- description: Update a bucket.
  method: PUT
  name: update-bucket
  path: /v1/buckets/{id}
- description: Delete a bucket.
  method: DELETE
  name: delete-bucket
  path: /v1/buckets/{id}
- description: Get IAM policy.
  method: GET
  name: get-bucket-iam-policy
  path: /v1/buckets/{id}/iam
- description: Set IAM policy.
  method: PUT
  name: set-bucket-iam-policy
  path: /v1/buckets/{id}/iam
- description: List objects.
  method: GET
  name: list-objects
  path: /v1/buckets/{bucketId}/objects
- description: Get object metadata.
  method: GET
  name: get-object
  path: /v1/buckets/{bucketId}/objects/{objectId}
- description: Update object metadata.
  method: PUT
  name: update-object
  path: /v1/buckets/{bucketId}/objects/{objectId}
- description: Delete an object.
  method: DELETE
  name: delete-object
  path: /v1/buckets/{bucketId}/objects/{objectId}
personas: []
provider_name: Google Cloud Storage
provider_slug: gcp-cloud-storage
search_terms:
- update a bucket.
- update object
- individual bucket management.
- blob storage
- list buckets
- list storage buckets in a project.
- update object metadata.
- delete object
- set bucket iam policy.
- get iam policy.
- get object metadata.
- update bucket
- list objects in a bucket.
- get object
- cloud storage
- get bucket iam policy.
- set iam policy.
- data management
- bucket management.
- object management.
- compose objects
- copy object
- create a new storage bucket.
- archival
- list objects.
- get bucket details.
- create bucket
- delete an object.
- backup
- object storage
- file storage
- individual object management.
- set bucket iam policy
- compose multiple objects into one.
- delete bucket
- delete a storage bucket.
- delete a bucket.
- storage
- list buckets.
- get bucket iam policy
- create a bucket.
- get bucket
- copy an object to another location.
- data
- google cloud
- list objects
- bucket iam management.
slug: cloud-storage
source_filename: cloud-storage.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Storage Management\n  description: Unified workflow for managing cloud storage buckets, objects, access controls, and IAM policies. Used by cloud\n    engineers and data platform teams.\n  tags:\n  - Google Cloud\n  - Cloud Storage\n  - Object Storage\n  - Data Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GCP_OAUTH2_TOKEN: GCP_OAUTH2_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: cloud-storage\n    baseUri: https://storage.googleapis.com/storage/v1\n    description: Google Cloud Storage JSON API for bucket and object management.\n    authentication:\n      type: bearer\n      token: '{{GCP_OAUTH2_TOKEN}}'\n    resources:\n    - name: buckets\n      path: /b\n      description: Bucket management.\n      operations:\n      - name: list-buckets\n        method: GET\n        description: List buckets for a project.\n        inputParameters:\n        - name:\
  \ project\n          in: query\n          type: string\n          required: true\n          description: Project ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-bucket\n        method: POST\n        description: Create a new bucket.\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          required: true\n          description: Project ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: bucket-details\n      path: /b/{bucket}\n      description: Individual bucket management.\n      operations:\n      - name: get-bucket\n        method: GET\n        description: Get bucket metadata.\n        inputParameters:\n        - name: bucket\n          in: path\n   \
  \       type: string\n          required: true\n          description: Bucket name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-bucket\n        method: PUT\n        description: Update bucket metadata.\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-bucket\n        method: DELETE\n        description: Delete a bucket.\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: bucket-iam\n      path: /b/{bucket}/iam\n      description: Bucket IAM policy management.\n      operations:\n      - name: get-bucket-iam-policy\n        method: GET\n        description: Get bucket IAM policy.\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-bucket-iam-policy\n        method: PUT\n        description: Set bucket IAM policy.\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            bindings: '{{tools.bindings}}'\n    - name: objects\n      path: /b/{bucket}/o\n      description: Object management.\n      operations:\n      - name: list-objects\n        method: GET\n        description: List objects in a bucket.\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: object-details\n      path: /b/{bucket}/o/{object}\n      description: Individual object management.\n      operations:\n      - name: get-object\n        method: GET\n        description: Get object metadata.\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        - name: object\n          in: path\n          type: string\n          required:\
  \ true\n          description: Object name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-object\n        method: PUT\n        description: Update object metadata.\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        - name: object\n          in: path\n          type: string\n          required: true\n          description: Object name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            metadata: '{{tools.metadata}}'\n      - name: delete-object\n        method: DELETE\n        description: Delete an object.\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n     \
  \     description: Bucket name.\n        - name: object\n          in: path\n          type: string\n          required: true\n          description: Object name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: object-copy\n      path: /b/{bucket}/o/{object}/copyTo/b/{destinationBucket}/o/{destinationObject}\n      description: Object copy operations.\n      operations:\n      - name: copy-object\n        method: POST\n        description: Copy an object to another location.\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Source bucket.\n        - name: object\n          in: path\n          type: string\n          required: true\n          description: Source object.\n        - name: destinationBucket\n          in: path\n          type: string\n          required: true\n          description: Destination\
  \ bucket.\n        - name: destinationObject\n          in: path\n          type: string\n          required: true\n          description: Destination object.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: object-compose\n      path: /b/{bucket}/o/{object}/compose\n      description: Object composition.\n      operations:\n      - name: compose-objects\n        method: POST\n        description: Compose multiple objects into one.\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Destination bucket.\n        - name: object\n          in: path\n          type: string\n          required: true\n          description: Destination object.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n     \
  \     data:\n            sourceObjects: '{{tools.sourceObjects}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cloud-storage-api\n    description: Unified REST API for Google Cloud Storage management.\n    resources:\n    - path: /v1/buckets\n      name: buckets\n      description: Bucket management.\n      operations:\n      - method: GET\n        name: list-buckets\n        description: List buckets.\n        call: cloud-storage.list-buckets\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-bucket\n        description: Create a bucket.\n        call: cloud-storage.create-bucket\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{id}\n      name: bucket-details\n      description: Individual bucket management.\n      operations:\n      - method: GET\n        name:\
  \ get-bucket\n        description: Get bucket details.\n        call: cloud-storage.get-bucket\n        with:\n          bucket: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-bucket\n        description: Update a bucket.\n        call: cloud-storage.update-bucket\n        with:\n          bucket: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-bucket\n        description: Delete a bucket.\n        call: cloud-storage.delete-bucket\n        with:\n          bucket: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{id}/iam\n      name: bucket-iam\n      description: Bucket IAM management.\n      operations:\n      - method: GET\n        name: get-bucket-iam-policy\n        description: Get IAM policy.\n        call: cloud-storage.get-bucket-iam-policy\n        with:\n      \
  \    bucket: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: set-bucket-iam-policy\n        description: Set IAM policy.\n        call: cloud-storage.set-bucket-iam-policy\n        with:\n          bucket: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucketId}/objects\n      name: objects\n      description: Object management.\n      operations:\n      - method: GET\n        name: list-objects\n        description: List objects.\n        call: cloud-storage.list-objects\n        with:\n          bucket: rest.bucketId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucketId}/objects/{objectId}\n      name: object-details\n      description: Individual object management.\n      operations:\n      - method: GET\n        name: get-object\n        description: Get object metadata.\n        call: cloud-storage.get-object\n\
  \        with:\n          bucket: rest.bucketId\n          object: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-object\n        description: Update object metadata.\n        call: cloud-storage.update-object\n        with:\n          bucket: rest.bucketId\n          object: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-object\n        description: Delete an object.\n        call: cloud-storage.delete-object\n        with:\n          bucket: rest.bucketId\n          object: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cloud-storage-mcp\n    transport: http\n    description: MCP server for AI-assisted cloud storage management.\n    tools:\n    - name: list-buckets\n      description: List storage buckets in a project.\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: cloud-storage.list-buckets\n      with:\n        project: tools.project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bucket\n      description: Get bucket details.\n      hints:\n        readOnly: true\n      call: cloud-storage.get-bucket\n      with:\n        bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bucket\n      description: Create a new storage bucket.\n      hints:\n        readOnly: false\n      call: cloud-storage.create-bucket\n      with:\n        project: tools.project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-bucket\n      description: Delete a storage bucket.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: cloud-storage.delete-bucket\n      with:\n        bucket: tools.bucket\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: list-objects\n      description: List objects in a bucket.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloud-storage.list-objects\n      with:\n        bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-object\n      description: Get object metadata.\n      hints:\n        readOnly: true\n      call: cloud-storage.get-object\n      with:\n        bucket: tools.bucket\n        object: tools.object\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-object\n      description: Delete an object.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: cloud-storage.delete-object\n      with:\n        bucket: tools.bucket\n        object: tools.object\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copy-object\n      description: Copy an\
  \ object to another location.\n      hints:\n        readOnly: false\n      call: cloud-storage.copy-object\n      with:\n        bucket: tools.sourceBucket\n        object: tools.sourceObject\n        destinationBucket: tools.destinationBucket\n        destinationObject: tools.destinationObject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: compose-objects\n      description: Compose multiple objects into one.\n      hints:\n        readOnly: false\n      call: cloud-storage.compose-objects\n      with:\n        bucket: tools.bucket\n        object: tools.destinationObject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bucket-iam-policy\n      description: Get bucket IAM policy.\n      hints:\n        readOnly: true\n      call: cloud-storage.get-bucket-iam-policy\n      with:\n        bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-bucket-iam-policy\n    \
  \  description: Set bucket IAM policy.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloud-storage.set-bucket-iam-policy\n      with:\n        bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/gcp-cloud-storage/refs/heads/main/capabilities/cloud-storage.yaml
tags:
- Google Cloud
- Cloud Storage
- Object Storage
- Data Management
tools:
- description: List storage buckets in a project.
  hints:
    openWorld: true
    readOnly: true
  name: list-buckets
- description: Get bucket details.
  hints:
    readOnly: true
  name: get-bucket
- description: Create a new storage bucket.
  hints:
    readOnly: false
  name: create-bucket
- description: Delete a storage bucket.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-bucket
- description: List objects in a bucket.
  hints:
    openWorld: true
    readOnly: true
  name: list-objects
- description: Get object metadata.
  hints:
    readOnly: true
  name: get-object
- description: Delete an object.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-object
- description: Copy an object to another location.
  hints:
    readOnly: false
  name: copy-object
- description: Compose multiple objects into one.
  hints:
    readOnly: false
  name: compose-objects
- description: Get bucket IAM policy.
  hints:
    readOnly: true
  name: get-bucket-iam-policy
- description: Set bucket IAM policy.
  hints:
    idempotent: true
    readOnly: false
  name: set-bucket-iam-policy
---

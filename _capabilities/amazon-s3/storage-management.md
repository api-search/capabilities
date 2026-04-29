---
categories:
- object-storage
consumed_apis:
- s3-rest
- s3-control
- s3-tables
description: Unified capability for Amazon S3 storage management combining object storage operations, account-level controls, and tabular data management. Used by cloud engineers, data engineers, and platform teams.
layout: capability
name: Amazon S3 Storage Management
operations:
- description: List all S3 buckets
  method: GET
  name: list-buckets
  path: /v1/buckets
- description: Create an S3 bucket
  method: POST
  name: create-bucket
  path: /v1/buckets
- description: Check if a bucket exists
  method: HEAD
  name: head-bucket
  path: /v1/buckets/{bucket}
- description: Delete an S3 bucket
  method: DELETE
  name: delete-bucket
  path: /v1/buckets/{bucket}
- description: List objects in a bucket
  method: GET
  name: list-objects
  path: /v1/buckets/{bucket}/objects
- description: Get an object
  method: GET
  name: get-object
  path: /v1/buckets/{bucket}/objects/{key}
- description: Upload an object
  method: PUT
  name: put-object
  path: /v1/buckets/{bucket}/objects/{key}
- description: Delete an object
  method: DELETE
  name: delete-object
  path: /v1/buckets/{bucket}/objects/{key}
- description: List S3 access points
  method: GET
  name: list-access-points
  path: /v1/access-points
- description: Get an access point
  method: GET
  name: get-access-point
  path: /v1/access-points/{name}
- description: List Batch Operations jobs
  method: GET
  name: list-jobs
  path: /v1/batch-jobs
- description: Create a Batch Operations job
  method: POST
  name: create-job
  path: /v1/batch-jobs
- description: Get details of a Batch Operations job
  method: GET
  name: describe-job
  path: /v1/batch-jobs/{id}
- description: List Storage Lens configurations
  method: GET
  name: list-storage-lens
  path: /v1/storage-lens
- description: List S3 table buckets
  method: GET
  name: list-table-buckets
  path: /v1/table-buckets
- description: List tables in a namespace
  method: GET
  name: list-tables
  path: /v1/table-buckets/{arn}/tables
personas: []
provider_name: Amazon S3
provider_slug: amazon-s3
search_terms:
- get bucket encryption
- get table bucket
- s3 buckets
- get versioning configuration for an s3 bucket
- delete objects
- list objects
- tables in a table bucket
- s3
- create bucket
- list all s3 buckets owned by the account
- list s3 batch operations jobs
- get an access point
- create job
- check if a bucket exists
- single access point
- create a batch operations job
- describe job
- create a new s3 bucket
- s3 table buckets
- objects in a bucket
- get lifecycle configuration for an s3 bucket
- s3 access points
- retrieve an object from s3
- list access points
- copy an object within s3
- delete object
- list batch operations jobs
- get details of a batch operations job
- get table
- put object
- list s3 table buckets
- get bucket versioning
- list s3 access points
- head bucket
- get object
- list tables in a namespace
- scalable storage
- list objects in a bucket
- storage management
- delete an s3 bucket
- single batch operations job
- copy object
- single s3 bucket
- get configuration of an s3 access point
- list storage lens
- get an object
- get public access block settings for the account
- backup
- data storage
- list table buckets
- s3 batch operations jobs
- describe batch job
- delete an object
- get encryption configuration for an s3 bucket
- list storage lens configs
- delete an object from s3
- list tables
- aws
- get public access block
- archive
- list all s3 buckets
- list namespaces
- list batch jobs
- list jobs
- create an s3 bucket
- cloud storage
- upload an object to s3
- delete multiple objects from an s3 bucket
- storage lens configurations
- list namespaces in a table bucket
- get details of a table
- get access point
- upload an object
- amazon
- list storage lens configurations
- list buckets
- list s3 storage lens configurations
- get bucket lifecycle
- object storage
- single object
- list s3 access points for the account
- delete bucket
- get details of an s3 table bucket
- list objects in an s3 bucket
slug: storage-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon S3 Storage Management\"\n  description: \"Unified capability for Amazon S3 storage management combining object storage operations, account-level controls, and tabular data management. Used by cloud engineers, data engineers, and platform teams.\"\n  tags:\n    - Amazon\n    - AWS\n    - S3\n    - Storage Management\n    - Cloud Storage\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: s3-rest\n      location: ./shared/s3-rest.yaml\n    - import: s3-control\n      location: ./shared/s3-control.yaml\n    - import: s3-tables\n      location: ./shared/s3-tables.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: storage-management-api\n      description: \"Unified REST API for Amazon S3 storage management.\"\n      resources:\n\
  \        - path: /v1/buckets\n          name: buckets\n          description: \"S3 buckets\"\n          operations:\n            - method: GET\n              name: list-buckets\n              description: \"List all S3 buckets\"\n              call: \"s3-rest.list-buckets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-bucket\n              description: \"Create an S3 bucket\"\n              call: \"s3-rest.create-bucket\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/buckets/{bucket}\n          name: bucket\n          description: \"Single S3 bucket\"\n          operations:\n            - method: HEAD\n              name: head-bucket\n              description: \"Check if a bucket exists\"\n              call: \"s3-rest.head-bucket\"\n              with:\n                Bucket: \"rest.bucket\"\n      \
  \        outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-bucket\n              description: \"Delete an S3 bucket\"\n              call: \"s3-rest.delete-bucket\"\n              with:\n                Bucket: \"rest.bucket\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/buckets/{bucket}/objects\n          name: objects\n          description: \"Objects in a bucket\"\n          operations:\n            - method: GET\n              name: list-objects\n              description: \"List objects in a bucket\"\n              call: \"s3-rest.list-objects-v2\"\n              with:\n                Bucket: \"rest.bucket\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/buckets/{bucket}/objects/{key}\n          name: object\n          description: \"Single\
  \ object\"\n          operations:\n            - method: GET\n              name: get-object\n              description: \"Get an object\"\n              call: \"s3-rest.get-object\"\n              with:\n                Bucket: \"rest.bucket\"\n                Key: \"rest.key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: put-object\n              description: \"Upload an object\"\n              call: \"s3-rest.put-object\"\n              with:\n                Bucket: \"rest.bucket\"\n                Key: \"rest.key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-object\n              description: \"Delete an object\"\n              call: \"s3-rest.delete-object\"\n              with:\n                Bucket: \"rest.bucket\"\n                Key: \"rest.key\"\n           \
  \   outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/access-points\n          name: access-points\n          description: \"S3 access points\"\n          operations:\n            - method: GET\n              name: list-access-points\n              description: \"List S3 access points\"\n              call: \"s3-control.list-access-points\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/access-points/{name}\n          name: access-point\n          description: \"Single access point\"\n          operations:\n            - method: GET\n              name: get-access-point\n              description: \"Get an access point\"\n              call: \"s3-control.get-access-point\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/batch-jobs\n\
  \          name: batch-jobs\n          description: \"S3 Batch Operations jobs\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List Batch Operations jobs\"\n              call: \"s3-control.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-job\n              description: \"Create a Batch Operations job\"\n              call: \"s3-control.create-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/batch-jobs/{id}\n          name: batch-job\n          description: \"Single Batch Operations job\"\n          operations:\n            - method: GET\n              name: describe-job\n              description: \"Get details of a Batch Operations job\"\n              call: \"s3-control.describe-job\"\n              with:\n                id:\
  \ \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/storage-lens\n          name: storage-lens\n          description: \"Storage Lens configurations\"\n          operations:\n            - method: GET\n              name: list-storage-lens\n              description: \"List Storage Lens configurations\"\n              call: \"s3-control.list-storage-lens-configurations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/table-buckets\n          name: table-buckets\n          description: \"S3 table buckets\"\n          operations:\n            - method: GET\n              name: list-table-buckets\n              description: \"List S3 table buckets\"\n              call: \"s3-tables.list-table-buckets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/table-buckets/{arn}/tables\n\
  \          name: tables\n          description: \"Tables in a table bucket\"\n          operations:\n            - method: GET\n              name: list-tables\n              description: \"List tables in a namespace\"\n              call: \"s3-tables.list-tables\"\n              with:\n                tableBucketARN: \"rest.arn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: storage-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon S3 storage management.\"\n      tools:\n        - name: list-buckets\n          description: \"List all S3 buckets owned by the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"s3-rest.list-buckets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bucket\n          description: \"Create a new\
  \ S3 bucket\"\n          hints:\n            readOnly: false\n          call: \"s3-rest.create-bucket\"\n          with:\n            Bucket: \"tools.bucket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-bucket\n          description: \"Delete an S3 bucket\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"s3-rest.delete-bucket\"\n          with:\n            Bucket: \"tools.bucket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-objects\n          description: \"List objects in an S3 bucket\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"s3-rest.list-objects-v2\"\n          with:\n            Bucket: \"tools.bucket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-object\n          description: \"Retrieve\
  \ an object from S3\"\n          hints:\n            readOnly: true\n          call: \"s3-rest.get-object\"\n          with:\n            Bucket: \"tools.bucket\"\n            Key: \"tools.key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: put-object\n          description: \"Upload an object to S3\"\n          hints:\n            readOnly: false\n          call: \"s3-rest.put-object\"\n          with:\n            Bucket: \"tools.bucket\"\n            Key: \"tools.key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-object\n          description: \"Delete an object from S3\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"s3-rest.delete-object\"\n          with:\n            Bucket: \"tools.bucket\"\n            Key: \"tools.key\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: copy-object\n          description: \"Copy an object within S3\"\n          hints:\n            readOnly: false\n          call: \"s3-rest.copy-object\"\n          with:\n            Bucket: \"tools.bucket\"\n            Key: \"tools.key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-objects\n          description: \"Delete multiple objects from an S3 bucket\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"s3-rest.delete-objects\"\n          with:\n            Bucket: \"tools.bucket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-bucket-versioning\n          description: \"Get versioning configuration for an S3 bucket\"\n          hints:\n            readOnly: true\n          call: \"s3-rest.get-bucket-versioning\"\n          with:\n            Bucket: \"tools.bucket\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-bucket-encryption\n          description: \"Get encryption configuration for an S3 bucket\"\n          hints:\n            readOnly: true\n          call: \"s3-rest.get-bucket-encryption\"\n          with:\n            Bucket: \"tools.bucket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-bucket-lifecycle\n          description: \"Get lifecycle configuration for an S3 bucket\"\n          hints:\n            readOnly: true\n          call: \"s3-rest.get-bucket-lifecycle-configuration\"\n          with:\n            Bucket: \"tools.bucket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-access-points\n          description: \"List S3 access points for the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"s3-control.list-access-points\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-access-point\n          description: \"Get configuration of an S3 access point\"\n          hints:\n            readOnly: true\n          call: \"s3-control.get-access-point\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-batch-jobs\n          description: \"List S3 Batch Operations jobs\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"s3-control.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-batch-job\n          description: \"Get details of a Batch Operations job\"\n          hints:\n            readOnly: true\n          call: \"s3-control.describe-job\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.\"\n        - name: list-storage-lens-configs\n          description: \"List S3 Storage Lens configurations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"s3-control.list-storage-lens-configurations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-public-access-block\n          description: \"Get public access block settings for the account\"\n          hints:\n            readOnly: true\n          call: \"s3-control.get-public-access-block\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-table-buckets\n          description: \"List S3 table buckets\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"s3-tables.list-table-buckets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n     \
  \   - name: get-table-bucket\n          description: \"Get details of an S3 table bucket\"\n          hints:\n            readOnly: true\n          call: \"s3-tables.get-table-bucket\"\n          with:\n            tableBucketARN: \"tools.table_bucket_arn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-namespaces\n          description: \"List namespaces in a table bucket\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"s3-tables.list-namespaces\"\n          with:\n            tableBucketARN: \"tools.table_bucket_arn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tables\n          description: \"List tables in a namespace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"s3-tables.list-tables\"\n          with:\n            tableBucketARN: \"tools.table_bucket_arn\"\n\
  \            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-table\n          description: \"Get details of a table\"\n          hints:\n            readOnly: true\n          call: \"s3-tables.get-table\"\n          with:\n            tableBucketARN: \"tools.table_bucket_arn\"\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-s3/refs/heads/main/capabilities/storage-management.yaml
tags:
- Amazon
- AWS
- S3
- Storage Management
- Cloud Storage
tools:
- description: List all S3 buckets owned by the account
  hints:
    openWorld: true
    readOnly: true
  name: list-buckets
- description: Create a new S3 bucket
  hints:
    readOnly: false
  name: create-bucket
- description: Delete an S3 bucket
  hints:
    destructive: true
    readOnly: false
  name: delete-bucket
- description: List objects in an S3 bucket
  hints:
    openWorld: true
    readOnly: true
  name: list-objects
- description: Retrieve an object from S3
  hints:
    readOnly: true
  name: get-object
- description: Upload an object to S3
  hints:
    readOnly: false
  name: put-object
- description: Delete an object from S3
  hints:
    destructive: true
    readOnly: false
  name: delete-object
- description: Copy an object within S3
  hints:
    readOnly: false
  name: copy-object
- description: Delete multiple objects from an S3 bucket
  hints:
    destructive: true
    readOnly: false
  name: delete-objects
- description: Get versioning configuration for an S3 bucket
  hints:
    readOnly: true
  name: get-bucket-versioning
- description: Get encryption configuration for an S3 bucket
  hints:
    readOnly: true
  name: get-bucket-encryption
- description: Get lifecycle configuration for an S3 bucket
  hints:
    readOnly: true
  name: get-bucket-lifecycle
- description: List S3 access points for the account
  hints:
    openWorld: true
    readOnly: true
  name: list-access-points
- description: Get configuration of an S3 access point
  hints:
    readOnly: true
  name: get-access-point
- description: List S3 Batch Operations jobs
  hints:
    openWorld: true
    readOnly: true
  name: list-batch-jobs
- description: Get details of a Batch Operations job
  hints:
    readOnly: true
  name: describe-batch-job
- description: List S3 Storage Lens configurations
  hints:
    openWorld: true
    readOnly: true
  name: list-storage-lens-configs
- description: Get public access block settings for the account
  hints:
    readOnly: true
  name: get-public-access-block
- description: List S3 table buckets
  hints:
    openWorld: true
    readOnly: true
  name: list-table-buckets
- description: Get details of an S3 table bucket
  hints:
    readOnly: true
  name: get-table-bucket
- description: List namespaces in a table bucket
  hints:
    openWorld: true
    readOnly: true
  name: list-namespaces
- description: List tables in a namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-tables
- description: Get details of a table
  hints:
    readOnly: true
  name: get-table
---

---
categories:
- object-storage
consumed_apis: []
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
- delete object
- list objects in an s3 bucket
- get object
- delete objects
- single s3 bucket
- get table bucket
- list storage lens
- list s3 batch operations jobs
- get bucket encryption
- describe job
- create bucket
- data storage
- retrieve an object from s3
- scalable storage
- list all s3 buckets owned by the account
- single access point
- get public access block settings for the account
- get an object
- list objects in a bucket
- archive
- list namespaces in a table bucket
- create a new s3 bucket
- list s3 access points for the account
- copy an object within s3
- list batch jobs
- create job
- upload an object to s3
- objects in a bucket
- cloud storage
- single batch operations job
- list access points
- check if a bucket exists
- get details of a table
- single object
- head bucket
- get bucket lifecycle
- get encryption configuration for an s3 bucket
- backup
- get bucket versioning
- object storage
- list s3 table buckets
- list all s3 buckets
- list namespaces
- list s3 access points
- upload an object
- list storage lens configurations
- list table buckets
- get an access point
- s3 access points
- get access point
- list storage lens configs
- delete an object
- get configuration of an s3 access point
- list tables
- get versioning configuration for an s3 bucket
- create a batch operations job
- get table
- delete bucket
- list jobs
- put object
- aws
- list objects
- get lifecycle configuration for an s3 bucket
- get details of a batch operations job
- delete an object from s3
- create an s3 bucket
- get details of an s3 table bucket
- s3 table buckets
- s3 batch operations jobs
- list buckets
- list s3 storage lens configurations
- storage lens configurations
- get public access block
- s3
- amazon
- tables in a table bucket
- copy object
- delete multiple objects from an s3 bucket
- list batch operations jobs
- list tables in a namespace
- delete an s3 bucket
- storage management
- describe batch job
- s3 buckets
slug: storage-management
source_filename: storage-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon S3 Storage Management\n  description: Unified capability for Amazon S3 storage management combining object storage operations, account-level controls,\n    and tabular data management. Used by cloud engineers, data engineers, and platform teams.\n  tags:\n  - Amazon\n  - AWS\n  - S3\n  - Storage Management\n  - Cloud Storage\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: s3-rest\n    baseUri: https://s3.us-east-1.amazonaws.com\n    description: Amazon S3 REST API for object storage\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: buckets\n      path: /\n      description: S3 bucket operations\n      operations:\n      - name: list-buckets\n\
  \        method: GET\n        description: List all buckets owned by the authenticated user\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-bucket\n        method: PUT\n        description: Create a new S3 bucket\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Name of the bucket to create\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-bucket\n        method: DELETE\n        description: Delete an S3 bucket\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Name of the bucket to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n      - name: head-bucket\n        method: HEAD\n        description: Check if a bucket exists and you have access\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Name of the bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: objects\n      path: /\n      description: S3 object operations\n      operations:\n      - name: list-objects-v2\n        method: GET\n        description: List objects in a bucket using v2 listing\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        - name: prefix\n          in: query\n          type: string\n          required: false\n          description: Prefix filter for object keys\n        - name: max-keys\n        \
  \  in: query\n          type: integer\n          required: false\n          description: Maximum number of keys to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-object\n        method: GET\n        description: Retrieve an object from S3\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        - name: Key\n          in: path\n          type: string\n          required: true\n          description: Object key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-object\n        method: PUT\n        description: Upload an object to S3\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n\
  \        - name: Key\n          in: path\n          type: string\n          required: true\n          description: Object key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-object\n        method: DELETE\n        description: Delete an object from S3\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        - name: Key\n          in: path\n          type: string\n          required: true\n          description: Object key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: head-object\n        method: HEAD\n        description: Get object metadata without the object body\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n \
  \         description: Bucket name\n        - name: Key\n          in: path\n          type: string\n          required: true\n          description: Object key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: copy-object\n        method: PUT\n        description: Copy an object within S3\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Destination bucket\n        - name: Key\n          in: path\n          type: string\n          required: true\n          description: Destination key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-objects\n        method: POST\n        description: Delete multiple objects from a bucket\n        inputParameters:\n        - name: Bucket\n          in: path\n          type:\
  \ string\n          required: true\n          description: Bucket name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket-config\n      path: /\n      description: Bucket configuration operations\n      operations:\n      - name: get-bucket-acl\n        method: GET\n        description: Get bucket access control list\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-bucket-acl\n        method: PUT\n        description: Set bucket access control list\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-bucket-versioning\n        method: GET\n        description: Get bucket versioning configuration\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-bucket-versioning\n        method: PUT\n        description: Set bucket versioning configuration\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-bucket-encryption\n        method: GET\n        description: Get bucket encryption configuration\n        inputParameters:\n\
  \        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-bucket-encryption\n        method: PUT\n        description: Set bucket encryption configuration\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-bucket-lifecycle-configuration\n        method: GET\n        description: Get bucket lifecycle configuration\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: put-bucket-lifecycle-configuration\n        method: PUT\n        description: Set bucket lifecycle configuration\n        inputParameters:\n        - name: Bucket\n          in: path\n          type: string\n          required: true\n          description: Bucket name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: s3-control\n    baseUri: https://s3-control.us-east-1.amazonaws.com\n    description: Amazon S3 Control API for account-level management\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: access-points\n      path: /v20180820\n      description: S3 access point management\n      operations:\n      - name: list-access-points\n        method: GET\n        description: List access\
  \ points for an account\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-access-point\n        method: GET\n        description: Get access point configuration\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Access point name or ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-access-point\n        method: PUT\n        description: Create an access point\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Access point name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-access-point\n\
  \        method: DELETE\n        description: Delete an access point\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Access point name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch-operations\n      path: /v20180820\n      description: S3 Batch Operations job management\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List Batch Operations jobs\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-job\n        method: POST\n        description: Create a Batch Operations job\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: describe-job\n        method: GET\n        description: Get details of a Batch Operations job\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-job-priority\n        method: POST\n        description: Update priority of a Batch Operations job\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-job-status\n        method: POST\n        description: Update status of a Batch Operations job\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n\
  \          description: Job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: storage-lens\n      path: /v20180820\n      description: S3 Storage Lens configuration management\n      operations:\n      - name: list-storage-lens-configurations\n        method: GET\n        description: List Storage Lens configurations\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-storage-lens-configuration\n        method: GET\n        description: Get a Storage Lens configuration\n        inputParameters:\n        - name: storagelensid\n          in: path\n          type: string\n          required: true\n          description: Storage Lens configuration ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: put-storage-lens-configuration\n        method: PUT\n        description: Create or update a Storage Lens configuration\n        inputParameters:\n        - name: storagelensid\n          in: path\n          type: string\n          required: true\n          description: Storage Lens configuration ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-storage-lens-configuration\n        method: DELETE\n        description: Delete a Storage Lens configuration\n        inputParameters:\n        - name: storagelensid\n          in: path\n          type: string\n          required: true\n          description: Storage Lens configuration ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: public-access-block\n      path: /v20180820\n      description: Public access block settings\n      operations:\n\
  \      - name: get-public-access-block\n        method: GET\n        description: Get public access block configuration\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-public-access-block\n        method: PUT\n        description: Set public access block configuration\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-public-access-block\n        method: DELETE\n        description: Delete public access block configuration\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: s3-tables\n    baseUri: https://s3tables.us-east-1.amazonaws.com\n    description: Amazon S3 Tables API for tabular data storage\n\
  \    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: table-buckets\n      path: /buckets\n      description: S3 table bucket management\n      operations:\n      - name: list-table-buckets\n        method: GET\n        description: List table buckets for your account\n        inputParameters:\n        - name: prefix\n          in: query\n          type: string\n          required: false\n          description: Prefix filter for table buckets\n        - name: maxBuckets\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of buckets to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-table-bucket\n        method: PUT\n        description: Create a table bucket\n        inputParameters: []\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: get-table-bucket\n        method: GET\n        description: Get table bucket details\n        inputParameters:\n        - name: tableBucketARN\n          in: path\n          type: string\n          required: true\n          description: Table bucket ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-table-bucket\n        method: DELETE\n        description: Delete a table bucket\n        inputParameters:\n        - name: tableBucketARN\n          in: path\n          type: string\n          required: true\n          description: Table bucket ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces\n\
  \      path: /namespaces\n      description: Namespace management within table buckets\n      operations:\n      - name: list-namespaces\n        method: GET\n        description: List namespaces in a table bucket\n        inputParameters:\n        - name: tableBucketARN\n          in: path\n          type: string\n          required: true\n          description: Table bucket ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-namespace\n        method: PUT\n        description: Create a namespace\n        inputParameters:\n        - name: tableBucketARN\n          in: path\n          type: string\n          required: true\n          description: Table bucket ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            namespace: '{{tools.namespace}}'\n\
  \      - name: get-namespace\n        method: GET\n        description: Get namespace details\n        inputParameters:\n        - name: tableBucketARN\n          in: path\n          type: string\n          required: true\n          description: Table bucket ARN\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-namespace\n        method: DELETE\n        description: Delete a namespace\n        inputParameters:\n        - name: tableBucketARN\n          in: path\n          type: string\n          required: true\n          description: Table bucket ARN\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: tables\n      path: /tables\n      description: Table management within namespaces\n      operations:\n      - name: list-tables\n        method: GET\n        description: List tables in a namespace\n        inputParameters:\n        - name: tableBucketARN\n          in: path\n          type: string\n          required: true\n          description: Table bucket ARN\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-table\n        method: PUT\n        description: Create a table\n        inputParameters:\n        - name: tableBucketARN\n          in: path\n          type: string\n          required: true\n          description: Table bucket ARN\n        - name: namespace\n          in: path\n\
  \          type: string\n          required: true\n          description: Namespace name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-table\n        method: GET\n        description: Get table details\n        inputParameters:\n        - name: tableBucketARN\n          in: path\n          type: string\n          required: true\n          description: Table bucket ARN\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Table name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-table\n        method: DELETE\n        description: Delete a table\n        inputParameters:\n        - name: tableBucketARN\n\
  \          in: path\n          type: string\n          required: true\n          description: Table bucket ARN\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Table name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: rename-table\n        method: PUT\n        description: Rename a table\n        inputParameters:\n        - name: tableBucketARN\n          in: path\n          type: string\n          required: true\n          description: Table bucket ARN\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        - name: name\n          in: path\n          type: string\n          required: true\n          description:\
  \ Current table name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: storage-management-api\n    description: Unified REST API for Amazon S3 storage management.\n    resources:\n    - path: /v1/buckets\n      name: buckets\n      description: S3 buckets\n      operations:\n      - method: GET\n        name: list-buckets\n        description: List all S3 buckets\n        call: s3-rest.list-buckets\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-bucket\n        description: Create an S3 bucket\n        call: s3-rest.create-bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucket}\n      name: bucket\n      description: Single S3 bucket\n      operations:\n      - method: HEAD\n        name: head-bucket\n        description: Check\
  \ if a bucket exists\n        call: s3-rest.head-bucket\n        with:\n          Bucket: rest.bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-bucket\n        description: Delete an S3 bucket\n        call: s3-rest.delete-bucket\n        with:\n          Bucket: rest.bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucket}/objects\n      name: objects\n      description: Objects in a bucket\n      operations:\n      - method: GET\n        name: list-objects\n        description: List objects in a bucket\n        call: s3-rest.list-objects-v2\n        with:\n          Bucket: rest.bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucket}/objects/{key}\n      name: object\n      description: Single object\n      operations:\n      - method: GET\n        name: get-object\n        description: Get an\
  \ object\n        call: s3-rest.get-object\n        with:\n          Bucket: rest.bucket\n          Key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: put-object\n        description: Upload an object\n        call: s3-rest.put-object\n        with:\n          Bucket: rest.bucket\n          Key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-object\n        description: Delete an object\n        call: s3-rest.delete-object\n        with:\n          Bucket: rest.bucket\n          Key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/access-points\n      name: access-points\n      description: S3 access points\n      operations:\n      - method: GET\n        name: list-access-points\n        description: List S3 access points\n        call: s3-control.list-access-points\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/access-points/{name}\n      name: access-point\n      description: Single access point\n      operations:\n      - method: GET\n        name: get-access-point\n        description: Get an access point\n        call: s3-control.get-access-point\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batch-jobs\n      name: batch-jobs\n      description: S3 Batch Operations jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List Batch Operations jobs\n        call: s3-control.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-job\n        description: Create a Batch Operations job\n        call: s3-control.create-job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batch-jobs/{id}\n      name:\
  \ batch-job\n      description: Single Batch Operations job\n      operations:\n      - method: GET\n        name: describe-job\n        description: Get details of a Batch Operations job\n        call: s3-control.describe-job\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/storage-lens\n      name: storage-lens\n      description: Storage Lens configurations\n      operations:\n      - method: GET\n        name: list-storage-lens\n        description: List Storage Lens configurations\n        call: s3-control.list-storage-lens-configurations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/table-buckets\n      name: table-buckets\n      description: S3 table buckets\n      operations:\n      - method: GET\n        name: list-table-buckets\n        description: List S3 table buckets\n        call: s3-tables.list-table-buckets\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/table-buckets/{arn}/tables\n      name: tables\n      description: Tables in a table bucket\n      operations:\n      - method: GET\n        name: list-tables\n        description: List tables in a namespace\n        call: s3-tables.list-tables\n        with:\n          tableBucketARN: rest.arn\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: storage-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon S3 storage management.\n    tools:\n    - name: list-buckets\n      description: List all S3 buckets owned by the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: s3-rest.list-buckets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bucket\n      description: Create a new S3 bucket\n      hints:\n        readOnly: false\n      call: s3-rest.create-bucket\n     \
  \ with:\n        Bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-bucket\n      description: Delete an S3 bucket\n      hints:\n        readOnly: false\n        destructive: true\n      call: s3-rest.delete-bucket\n      with:\n        Bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-objects\n      description: List objects in an S3 bucket\n      hints:\n        readOnly: true\n        openWorld: true\n      call: s3-rest.list-objects-v2\n      with:\n        Bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-object\n      description: Retrieve an object from S3\n      hints:\n        readOnly: true\n      call: s3-rest.get-object\n      with:\n        Bucket: tools.bucket\n        Key: tools.key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-object\n      description: Upload an\
  \ object to S3\n      hints:\n        readOnly: false\n      call: s3-rest.put-object\n      with:\n        Bucket: tools.bucket\n        Key: tools.key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-object\n      description: Delete an object from S3\n      hints:\n        readOnly: false\n        destructive: true\n      call: s3-rest.delete-object\n      with:\n        Bucket: tools.bucket\n        Key: tools.key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copy-object\n      description: Copy an object within S3\n      hints:\n        readOnly: false\n      call: s3-rest.copy-object\n      with:\n        Bucket: tools.bucket\n        Key: tools.key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-objects\n      description: Delete multiple objects from an S3 bucket\n      hints:\n        readOnly: false\n        destructive: true\n      call: s3-rest.delete-objects\n\
  \      with:\n        Bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bucket-versioning\n      description: Get versioning configuration for an S3 bucket\n      hints:\n        readOnly: true\n      call: s3-rest.get-bucket-versioning\n      with:\n        Bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bucket-encryption\n      description: Get encryption configuration for an S3 bucket\n      hints:\n        readOnly: true\n      call: s3-rest.get-bucket-encryption\n      with:\n        Bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bucket-lifecycle\n      description: Get lifecycle configuration for an S3 bucket\n      hints:\n        readOnly: true\n      call: s3-rest.get-bucket-lifecycle-configuration\n      with:\n        Bucket: tools.bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: list-access-points\n      description: List S3 access points for the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: s3-control.list-access-points\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-access-point\n      description: Get configuration of an S3 access point\n      hints:\n        readOnly: true\n      call: s3-control.get-access-point\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-batch-jobs\n      description: List S3 Batch Operations jobs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: s3-control.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-batch-job\n      description: Get details of a Batch Operations job\n      hints:\n        readOnly: true\n      call: s3-control.describe-job\n      with:\n        id: tools.id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-storage-lens-configs\n      description: List S3 Storage Lens configurations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: s3-control.list-storage-lens-configurations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-public-access-block\n      description: Get public access block settings for the account\n      hints:\n        readOnly: true\n      call: s3-control.get-public-access-block\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-table-buckets\n      description: List S3 table buckets\n      hints:\n        readOnly: true\n        openWorld: true\n      call: s3-tables.list-table-buckets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-table-bucket\n      description: Get details of an S3\n\n# --- truncated at 32 KB (33 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/amazon-s3/refs/heads/main/capabilities/storage-management.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-s3/refs/heads/main/capabilities/storage-management.yaml
tags:
- Amazon
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

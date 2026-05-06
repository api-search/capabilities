---
categories: []
consumed_apis: []
description: The Google Cloud Storage JSON API allows applications to store and retrieve data on Google's infrastructure. It provides RESTful access to Cloud Storage buckets and objects, supporting upload, download, metadata management, and access control operations.
layout: capability
name: Google Cloud Storage JSON API
operations:
- description: Google Cloud Storage List buckets
  method: GET
  name: listbuckets
  path: /b
- description: Google Cloud Storage Create a bucket
  method: POST
  name: insertbucket
  path: /b
- description: Google Cloud Storage Get a bucket
  method: GET
  name: getbucket
  path: /b/{bucket}
- description: Google Cloud Storage Update a bucket
  method: PUT
  name: updatebucket
  path: /b/{bucket}
- description: Google Cloud Storage Delete a bucket
  method: DELETE
  name: deletebucket
  path: /b/{bucket}
- description: Google Cloud Storage List objects
  method: GET
  name: listobjects
  path: /b/{bucket}/o
- description: Google Cloud Storage Insert an object
  method: POST
  name: insertobject
  path: /b/{bucket}/o
- description: Google Cloud Storage Get an object
  method: GET
  name: getobject
  path: /b/{bucket}/o/{object}
- description: Google Cloud Storage Update an object
  method: PUT
  name: updateobject
  path: /b/{bucket}/o/{object}
- description: Google Cloud Storage Delete an object
  method: DELETE
  name: deleteobject
  path: /b/{bucket}/o/{object}
personas: []
provider_name: Google Cloud Storage
provider_slug: google-cloud-storage
search_terms:
- google cloud storage delete a bucket
- buckets
- storage
- google cloud storage list objects
- listobjects
- google cloud storage get an object
- cloud
- google
- deletebucket
- listbuckets
- google cloud storage create a bucket
- insertobject
- updateobject
- api
- google cloud storage get a bucket
- google cloud storage list buckets
- google cloud storage insert an object
- getobject
- getbucket
- insertbucket
- updatebucket
- google cloud storage update a bucket
- google cloud storage delete an object
- google cloud storage update an object
- deleteobject
- google cloud
- objects
slug: google-cloud-storage-capability
source_filename: google-cloud-storage-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Storage JSON API\n  description: The Google Cloud Storage JSON API allows applications to store and retrieve data on Google's infrastructure.\n    It provides RESTful access to Cloud Storage buckets and objects, supporting upload, download, metadata management, and\n    access control operations.\n  tags:\n  - Google\n  - Cloud\n  - Storage\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-storage\n    baseUri: https://storage.googleapis.com/storage/v1\n    description: Google Cloud Storage JSON API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_STORAGE_TOKEN}}'\n    resources:\n    - name: b\n      path: /b\n      operations:\n      - name: listbuckets\n        method: GET\n        description: Google Cloud Storage List buckets\n        inputParameters:\n        - name: project\n          in: query\n        \
  \  type: string\n          required: true\n          description: A valid API project identifier.\n        - name: maxResults\n          in: query\n          type: integer\n          description: Maximum number of buckets to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: A previously-returned page token for pagination.\n        - name: prefix\n          in: query\n          type: string\n          description: Filter results to buckets whose names begin with this prefix.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertbucket\n        method: POST\n        description: Google Cloud Storage Create a bucket\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          required: true\n          description: A valid API project identifier.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: b-bucket\n      path: /b/{bucket}\n      operations:\n      - name: getbucket\n        method: GET\n        description: Google Cloud Storage Get a bucket\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Name of the bucket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebucket\n        method: PUT\n        description: Google Cloud Storage Update a bucket\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Name of the bucket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebucket\n        method: DELETE\n        description:\
  \ Google Cloud Storage Delete a bucket\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Name of the bucket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: b-bucket-o\n      path: /b/{bucket}/o\n      operations:\n      - name: listobjects\n        method: GET\n        description: Google Cloud Storage List objects\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Name of the bucket.\n        - name: prefix\n          in: query\n          type: string\n          description: Filter results to objects whose names begin with this prefix.\n        - name: delimiter\n          in: query\n          type: string\n          description: Returns results in a directory-like mode.\n        - name: maxResults\n         \
  \ in: query\n          type: integer\n          description: Maximum number of objects to return.\n        - name: pageToken\n          in: query\n          type: string\n          description: A previously-returned page token for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertobject\n        method: POST\n        description: Google Cloud Storage Insert an object\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Name of the bucket.\n        - name: name\n          in: query\n          type: string\n          description: Name of the object.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: b-bucket-o-object\n      path: /b/{bucket}/o/{object}\n      operations:\n      - name: getobject\n     \
  \   method: GET\n        description: Google Cloud Storage Get an object\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n          description: Name of the bucket.\n        - name: object\n          in: path\n          type: string\n          required: true\n          description: Name of the object.\n        - name: alt\n          in: query\n          type: string\n          description: Set to media to download object data. Default is json for metadata.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateobject\n        method: PUT\n        description: Google Cloud Storage Update an object\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n        - name: object\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteobject\n        method: DELETE\n        description: Google Cloud Storage Delete an object\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n        - name: object\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-storage-rest\n    description: REST adapter for Google Cloud Storage JSON API.\n    resources:\n    - path: /b\n      name: listbuckets\n      operations:\n      - method: GET\n        name: listbuckets\n        description: Google Cloud Storage List buckets\n        call: google-cloud-storage.listbuckets\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /b\n      name: insertbucket\n      operations:\n      - method: POST\n        name: insertbucket\n        description: Google Cloud Storage Create a bucket\n        call: google-cloud-storage.insertbucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /b/{bucket}\n      name: getbucket\n      operations:\n      - method: GET\n        name: getbucket\n        description: Google Cloud Storage Get a bucket\n        call: google-cloud-storage.getbucket\n        with:\n          bucket: rest.bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /b/{bucket}\n      name: updatebucket\n      operations:\n      - method: PUT\n        name: updatebucket\n        description: Google Cloud Storage Update a bucket\n        call: google-cloud-storage.updatebucket\n        with:\n          bucket: rest.bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /b/{bucket}\n\
  \      name: deletebucket\n      operations:\n      - method: DELETE\n        name: deletebucket\n        description: Google Cloud Storage Delete a bucket\n        call: google-cloud-storage.deletebucket\n        with:\n          bucket: rest.bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /b/{bucket}/o\n      name: listobjects\n      operations:\n      - method: GET\n        name: listobjects\n        description: Google Cloud Storage List objects\n        call: google-cloud-storage.listobjects\n        with:\n          bucket: rest.bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /b/{bucket}/o\n      name: insertobject\n      operations:\n      - method: POST\n        name: insertobject\n        description: Google Cloud Storage Insert an object\n        call: google-cloud-storage.insertobject\n        with:\n          bucket: rest.bucket\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /b/{bucket}/o/{object}\n      name: getobject\n      operations:\n      - method: GET\n        name: getobject\n        description: Google Cloud Storage Get an object\n        call: google-cloud-storage.getobject\n        with:\n          bucket: rest.bucket\n          object: rest.object\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /b/{bucket}/o/{object}\n      name: updateobject\n      operations:\n      - method: PUT\n        name: updateobject\n        description: Google Cloud Storage Update an object\n        call: google-cloud-storage.updateobject\n        with:\n          bucket: rest.bucket\n          object: rest.object\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /b/{bucket}/o/{object}\n      name: deleteobject\n      operations:\n      - method: DELETE\n        name: deleteobject\n        description: Google Cloud Storage Delete an object\n        call: google-cloud-storage.deleteobject\n\
  \        with:\n          bucket: rest.bucket\n          object: rest.object\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-storage-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Storage JSON API for AI agent use.\n    tools:\n    - name: listbuckets\n      description: Google Cloud Storage List buckets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-storage.listbuckets\n      with:\n        project: tools.project\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n        prefix: tools.prefix\n      inputParameters:\n      - name: project\n        type: string\n        description: A valid API project identifier.\n        required: true\n      - name: maxResults\n        type: integer\n        description: Maximum number of buckets to return.\n      - name: pageToken\n        type: string\n\
  \        description: A previously-returned page token for pagination.\n      - name: prefix\n        type: string\n        description: Filter results to buckets whose names begin with this prefix.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertbucket\n      description: Google Cloud Storage Create a bucket\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-storage.insertbucket\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: A valid API project identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbucket\n      description: Google Cloud Storage Get a bucket\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-storage.getbucket\n      with:\n        bucket: tools.bucket\n\
  \      inputParameters:\n      - name: bucket\n        type: string\n        description: Name of the bucket.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatebucket\n      description: Google Cloud Storage Update a bucket\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-cloud-storage.updatebucket\n      with:\n        bucket: tools.bucket\n      inputParameters:\n      - name: bucket\n        type: string\n        description: Name of the bucket.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebucket\n      description: Google Cloud Storage Delete a bucket\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-storage.deletebucket\n      with:\n        bucket: tools.bucket\n      inputParameters:\n      - name: bucket\n        type: string\n\
  \        description: Name of the bucket.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listobjects\n      description: Google Cloud Storage List objects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-storage.listobjects\n      with:\n        bucket: tools.bucket\n        prefix: tools.prefix\n        delimiter: tools.delimiter\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: bucket\n        type: string\n        description: Name of the bucket.\n        required: true\n      - name: prefix\n        type: string\n        description: Filter results to objects whose names begin with this prefix.\n      - name: delimiter\n        type: string\n        description: Returns results in a directory-like mode.\n      - name: maxResults\n        type: integer\n        description: Maximum number of objects\
  \ to return.\n      - name: pageToken\n        type: string\n        description: A previously-returned page token for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertobject\n      description: Google Cloud Storage Insert an object\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-storage.insertobject\n      with:\n        bucket: tools.bucket\n        name: tools.name\n      inputParameters:\n      - name: bucket\n        type: string\n        description: Name of the bucket.\n        required: true\n      - name: name\n        type: string\n        description: Name of the object.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getobject\n      description: Google Cloud Storage Get an object\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-storage.getobject\n     \
  \ with:\n        bucket: tools.bucket\n        object: tools.object\n        alt: tools.alt\n      inputParameters:\n      - name: bucket\n        type: string\n        description: Name of the bucket.\n        required: true\n      - name: object\n        type: string\n        description: Name of the object.\n        required: true\n      - name: alt\n        type: string\n        description: Set to media to download object data. Default is json for metadata.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateobject\n      description: Google Cloud Storage Update an object\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-cloud-storage.updateobject\n      with:\n        bucket: tools.bucket\n        object: tools.object\n      inputParameters:\n      - name: bucket\n        type: string\n        description: bucket\n        required: true\n      - name: object\n        type: string\n \
  \       description: object\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteobject\n      description: Google Cloud Storage Delete an object\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-storage.deleteobject\n      with:\n        bucket: tools.bucket\n        object: tools.object\n      inputParameters:\n      - name: bucket\n        type: string\n        description: bucket\n        required: true\n      - name: object\n        type: string\n        description: object\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_STORAGE_TOKEN: GOOGLE_CLOUD_STORAGE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-storage/refs/heads/main/capabilities/google-cloud-storage-capability.yaml
tags:
- Google
- Cloud
- Storage
- API
tools:
- description: Google Cloud Storage List buckets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuckets
- description: Google Cloud Storage Create a bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertbucket
- description: Google Cloud Storage Get a bucket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucket
- description: Google Cloud Storage Update a bucket
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebucket
- description: Google Cloud Storage Delete a bucket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucket
- description: Google Cloud Storage List objects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listobjects
- description: Google Cloud Storage Insert an object
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertobject
- description: Google Cloud Storage Get an object
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getobject
- description: Google Cloud Storage Update an object
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateobject
- description: Google Cloud Storage Delete an object
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteobject
---

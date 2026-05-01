---
categories:
- object-storage
consumed_apis: []
description: Workflow capability for managing object storage using Apache Ozone's S3-compatible API.
layout: capability
name: Apache Ozone Object Storage Workflow
operations:
- description: List all buckets
  method: GET
  name: list-buckets
  path: /v1/buckets
- description: List objects
  method: GET
  name: list-objects
  path: /v1/buckets/{bucket}/objects
personas: []
provider_name: Apache Ozone
provider_slug: apache-ozone
search_terms:
- delete an object from a bucket
- get metadata for an object
- get object
- s3 compatible
- list all buckets
- list objects in a bucket
- create a new storage bucket
- put object
- s3-compatible
- list buckets
- Application Developer
- object storage
- uses s3-compatible api for application storage
- hadoop
- delete object
- delete bucket
- Data Engineer
- cloud native
- distributed storage
- head object
- list objects
- apache ozone
- apache
- upload an object to a bucket
- download an object from a bucket
- open source
- create bucket
- delete an empty bucket
- manages data lake storage with ozone
- list all object storage buckets
slug: ozone-workflow
source_filename: ozone-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Apache Ozone Object Storage Workflow\"\n  description: \"Workflow capability for managing object storage using Apache Ozone's S3-compatible API.\"\n  tags:\n    - Apache Ozone\n    - Object Storage\n    - Distributed Storage\n    - S3 Compatible\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      OZONE_ACCESS_KEY: OZONE_ACCESS_KEY\n      OZONE_SECRET_KEY: OZONE_SECRET_KEY\ncapability:\n  consumes:\n    - type: http\n      namespace: ozone\n      baseUri: https://localhost:9878\n      description: \"Apache Ozone S3-Compatible API\"\n      authentication:\n        type: apikey\n        key: Authorization\n        value: \"{{OZONE_ACCESS_KEY}}\"\n        placement: header\n      resources:\n        - name: buckets\n          path: /\n          description: \"Bucket management\"\n          operations:\n            - name: listBuckets\n              method: GET\n              description:\
  \ \"List all buckets\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: objects\n          path: /{bucket}\n          description: \"Object management\"\n          operations:\n            - name: listObjects\n              method: GET\n              description: \"List objects in bucket\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ozone-api\n      description: \"Unified REST API for Ozone object storage.\"\n      resources:\n        - path: /v1/buckets\n          name: buckets\n          operations:\n            - method: GET\n              name: list-buckets\n              description: \"List all buckets\"\n              call: \"ozone.listBuckets\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/buckets/{bucket}/objects\n          name: objects\n          operations:\n            - method: GET\n              name: list-objects\n              description: \"List objects\"\n              call: \"ozone.listObjects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: ozone-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Ozone object storage management.\"\n      tools:\n        - name: list-buckets\n          description: \"List all object storage buckets\"\n          hints:\n            readOnly: true\n          call: \"ozone.listBuckets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bucket\n          description: \"Create a new storage bucket\"\n          hints:\n            readOnly: false\n       \
  \   call: \"ozone.createBucket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-objects\n          description: \"List objects in a bucket\"\n          hints:\n            readOnly: true\n          call: \"ozone.listObjects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: put-object\n          description: \"Upload an object to a bucket\"\n          hints:\n            readOnly: false\n          call: \"ozone.putObject\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-object\n          description: \"Download an object from a bucket\"\n          hints:\n            readOnly: true\n          call: \"ozone.getObject\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-object\n          description: \"Delete an object from a bucket\"\n          hints:\n\
  \            readOnly: false\n            destructive: true\n          call: \"ozone.deleteObject\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-bucket\n          description: \"Delete an empty bucket\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"ozone.deleteBucket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: head-object\n          description: \"Get metadata for an object\"\n          hints:\n            readOnly: true\n          call: \"ozone.headObject\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-ozone/refs/heads/main/capabilities/ozone-workflow.yaml
tags:
- Apache Ozone
- Object Storage
- Distributed Storage
- S3 Compatible
tools:
- description: List all object storage buckets
  hints:
    readOnly: true
  name: list-buckets
- description: Create a new storage bucket
  hints:
    readOnly: false
  name: create-bucket
- description: List objects in a bucket
  hints:
    readOnly: true
  name: list-objects
- description: Upload an object to a bucket
  hints:
    readOnly: false
  name: put-object
- description: Download an object from a bucket
  hints:
    readOnly: true
  name: get-object
- description: Delete an object from a bucket
  hints:
    destructive: true
    readOnly: false
  name: delete-object
- description: Delete an empty bucket
  hints:
    destructive: true
    readOnly: false
  name: delete-bucket
- description: Get metadata for an object
  hints:
    readOnly: true
  name: head-object
---

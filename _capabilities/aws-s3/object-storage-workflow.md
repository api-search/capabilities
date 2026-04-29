---
categories:
- object-storage
consumed_apis:
- s3
description: Workflow capability for managing Amazon S3 buckets and objects for scalable object storage.
layout: capability
name: Amazon S3 Object Storage Workflow
operations: []
personas: []
provider_name: Amazon S3 API
provider_slug: aws-s3
search_terms:
- create a new s3 bucket
- object storage
- get_object
- create_bucket
- delete an s3 bucket
- list objects in an s3 bucket
- cloud storage
- aws
- upload an object to s3
- list all s3 buckets in the account
- list_buckets
- data management
- delete_object
- storage
- copy an object within or between s3 buckets
- copy_object
- upload_object
- delete_bucket
- download an object from s3
- list_objects
- delete an object from s3
slug: object-storage-workflow
source_filename: object-storage-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon S3 Object Storage Workflow\n  description: Workflow capability for managing Amazon S3 buckets and objects for scalable object storage.\n  tags:\n    - Cloud Storage\n    - Object Storage\n    - Data Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n    - import: s3\n      location: ./shared/s3.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workflow-api\n      resources:\n        - label: List Buckets\n          method: GET\n          path: /buckets\n        - label: Create Bucket\n          method: POST\n          path: /buckets\n        - label: Delete Bucket\n          method: DELETE\n          path: /buckets/{bucket}\n        - label: List Objects\n          method: GET\n          path: /buckets/{bucket}/objects\n\
  \        - label: Get Object\n          method: GET\n          path: /buckets/{bucket}/objects/{key}\n        - label: Upload Object\n          method: PUT\n          path: /buckets/{bucket}/objects/{key}\n        - label: Delete Object\n          method: DELETE\n          path: /buckets/{bucket}/objects/{key}\n        - label: Copy Object\n          method: POST\n          path: /buckets/{bucket}/objects/{key}/copy\n    - type: mcp\n      port: 9090\n      namespace: workflow-mcp\n      transport: http\n      tools:\n        - name: list_buckets\n          description: List all S3 buckets in the account\n        - name: create_bucket\n          description: Create a new S3 bucket\n        - name: delete_bucket\n          description: Delete an S3 bucket\n        - name: list_objects\n          description: List objects in an S3 bucket\n        - name: get_object\n          description: Download an object from S3\n        - name: upload_object\n          description: Upload an object to\
  \ S3\n        - name: delete_object\n          description: Delete an object from S3\n        - name: copy_object\n          description: Copy an object within or between S3 buckets\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-s3/refs/heads/main/capabilities/object-storage-workflow.yaml
tags:
- Cloud Storage
- Object Storage
- Data Management
tools:
- description: List all S3 buckets in the account
  hints: {}
  name: list_buckets
- description: Create a new S3 bucket
  hints: {}
  name: create_bucket
- description: Delete an S3 bucket
  hints: {}
  name: delete_bucket
- description: List objects in an S3 bucket
  hints: {}
  name: list_objects
- description: Download an object from S3
  hints: {}
  name: get_object
- description: Upload an object to S3
  hints: {}
  name: upload_object
- description: Delete an object from S3
  hints: {}
  name: delete_object
- description: Copy an object within or between S3 buckets
  hints: {}
  name: copy_object
---

---
consumed_apis:
- cloud-storage
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
- create a new storage bucket.
- bucket management.
- list storage buckets in a project.
- create bucket
- delete a storage bucket.
- data
- get bucket iam policy
- data management
- set bucket iam policy.
- set iam policy.
- create a bucket.
- list objects.
- get bucket
- backup
- update object
- storage
- blob storage
- get object
- delete an object.
- list buckets.
- compose objects
- list buckets
- list objects
- update object metadata.
- individual bucket management.
- get bucket iam policy.
- update bucket
- cloud storage
- file storage
- get iam policy.
- individual object management.
- google cloud
- get object metadata.
- compose multiple objects into one.
- archival
- get bucket details.
- set bucket iam policy
- delete object
- object management.
- copy an object to another location.
- update a bucket.
- delete a bucket.
- copy object
- object storage
- list objects in a bucket.
- delete bucket
- bucket iam management.
slug: cloud-storage
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

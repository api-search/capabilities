---
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
- s3 compatible
- get metadata for an object
- list all buckets
- list buckets
- s3-compatible
- Data Engineer
- delete bucket
- apache
- uses s3-compatible api for application storage
- create bucket
- hadoop
- list all object storage buckets
- Application Developer
- delete object
- apache ozone
- list objects in a bucket
- delete an object from a bucket
- create a new storage bucket
- upload an object to a bucket
- open source
- head object
- list objects
- object storage
- put object
- get object
- manages data lake storage with ozone
- download an object from a bucket
- delete an empty bucket
- distributed storage
- cloud native
slug: ozone-workflow
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

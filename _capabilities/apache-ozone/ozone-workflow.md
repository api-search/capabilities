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
- cloud native
- open source
- delete object
- list objects
- distributed storage
- apache
- upload an object to a bucket
- get object
- get metadata for an object
- put object
- list all buckets
- Data Engineer
- list objects in a bucket
- apache ozone
- s3-compatible
- manages data lake storage with ozone
- create a new storage bucket
- download an object from a bucket
- delete bucket
- s3 compatible
- list all object storage buckets
- head object
- list buckets
- Application Developer
- create bucket
- uses s3-compatible api for application storage
- hadoop
- delete an object from a bucket
- object storage
- delete an empty bucket
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

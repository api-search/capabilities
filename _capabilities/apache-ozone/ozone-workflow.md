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
- hadoop
- create bucket
- delete an empty bucket
- Data Engineer
- download an object from a bucket
- get metadata for an object
- distributed storage
- manages data lake storage with ozone
- s3-compatible
- list all object storage buckets
- get object
- apache
- list all buckets
- uses s3-compatible api for application storage
- list objects
- list buckets
- delete an object from a bucket
- Application Developer
- create a new storage bucket
- put object
- apache ozone
- object storage
- s3 compatible
- cloud native
- delete object
- open source
- head object
- upload an object to a bucket
- list objects in a bucket
- delete bucket
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

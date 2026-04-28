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
- s3 compatible
- list all buckets
- head object
- hadoop
- put object
- delete bucket
- list all object storage buckets
- list buckets
- uses s3-compatible api for application storage
- get metadata for an object
- list objects
- manages data lake storage with ozone
- apache
- create a new storage bucket
- download an object from a bucket
- delete an object from a bucket
- Data Engineer
- distributed storage
- Application Developer
- s3-compatible
- cloud native
- open source
- delete an empty bucket
- list objects in a bucket
- get object
- delete object
- object storage
- create bucket
- apache ozone
- upload an object to a bucket
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

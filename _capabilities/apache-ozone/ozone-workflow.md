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
- object storage
- upload an object to a bucket
- delete object
- uses s3-compatible api for application storage
- head object
- s3 compatible
- manages data lake storage with ozone
- apache
- distributed storage
- cloud native
- download an object from a bucket
- list objects
- open source
- list buckets
- delete an object from a bucket
- create bucket
- list all object storage buckets
- put object
- create a new storage bucket
- get metadata for an object
- delete an empty bucket
- Data Engineer
- Application Developer
- apache ozone
- get object
- list objects in a bucket
- delete bucket
- hadoop
- list all buckets
- s3-compatible
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

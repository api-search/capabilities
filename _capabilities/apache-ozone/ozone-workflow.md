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
- delete bucket
- list objects in a bucket
- download an object from a bucket
- delete an empty bucket
- object storage
- create a new storage bucket
- s3-compatible
- s3 compatible
- get object
- Data Engineer
- create bucket
- delete object
- delete an object from a bucket
- distributed storage
- upload an object to a bucket
- get metadata for an object
- put object
- list all object storage buckets
- apache
- manages data lake storage with ozone
- list objects
- open source
- Application Developer
- cloud native
- list buckets
- list all buckets
- head object
- apache ozone
- uses s3-compatible api for application storage
- hadoop
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

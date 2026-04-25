---
consumed_apis:
- ecr
description: Unified capability for managing ECR repositories, container images, and lifecycle policies for DevOps engineers.
layout: capability
name: Amazon ECR Container Registry Management
operations:
- description: Amazon ECR Create Repository
  method: POST
  name: createRepository
  path: /v1/resource
- description: Amazon ECR Describe Repositories
  method: POST
  name: describeRepositories
  path: /v1/#DescribeRepositories
- description: Amazon ECR Delete Repository
  method: POST
  name: deleteRepository
  path: /v1/#DeleteRepository
- description: Amazon ECR Put Image
  method: POST
  name: putImage
  path: /v1/#PutImage
- description: Amazon ECR Batch Get Image
  method: POST
  name: batchGetImage
  path: /v1/#BatchGetImage
- description: Amazon ECR List Images
  method: POST
  name: listImages
  path: /v1/#ListImages
personas: []
provider_name: Amazon ECR
provider_slug: amazon-ecr
search_terms:
- amazon ecr batch get image
- amazon ecr
- deleteRepository
- delete repository
- amazon ecr create repository
- amazon web services
- batchGetImage
- ecr
- amazon ecr put image
- container registry management business domain for amazon ecr.
- list images
- containers
- createRepository
- amazon ecr describe repositories
- workflow capability for container registry management.
- container images
- amazon ecr list images
- container registry
- amazon ecr delete repository
- create repository
- oci
- docker
- put image
- describeRepositories
- aws
- batch get image
- describe repositories
- engineers managing amazon ecr resources on aws.
- listImages
- putImage
slug: ecr-management
tags:
- Amazon ECR
- AWS
- Containers
- Container Registry
tools:
- description: Amazon ECR Create Repository
  hints:
    destructive: false
    readOnly: false
  name: create-repository
- description: Amazon ECR Describe Repositories
  hints:
    destructive: false
    readOnly: false
  name: describe-repositories
- description: Amazon ECR Delete Repository
  hints:
    destructive: false
    readOnly: false
  name: delete-repository
- description: Amazon ECR Put Image
  hints:
    destructive: false
    readOnly: false
  name: put-image
- description: Amazon ECR Batch Get Image
  hints:
    destructive: false
    readOnly: false
  name: batch-get-image
- description: Amazon ECR List Images
  hints:
    destructive: false
    readOnly: false
  name: list-images
---

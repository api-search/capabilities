---
categories:
- container-orchestration
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
- describeRepositories
- create repository
- amazon ecr describe repositories
- amazon ecr
- container registry
- amazon web services
- list images
- batch get image
- ecr
- delete repository
- docker
- describe repositories
- amazon ecr create repository
- putImage
- amazon ecr list images
- put image
- deleteRepository
- amazon ecr put image
- amazon ecr batch get image
- engineers managing amazon ecr resources on aws.
- oci
- batchGetImage
- containers
- container images
- container registry management business domain for amazon ecr.
- aws
- createRepository
- amazon ecr delete repository
- workflow capability for container registry management.
- listImages
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

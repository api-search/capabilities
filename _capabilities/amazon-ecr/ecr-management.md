---
categories:
- container-orchestration
consumed_apis: []
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
- workflow capability for container registry management.
- containers
- container images
- delete repository
- amazon web services
- batchGetImage
- putImage
- list images
- amazon ecr batch get image
- put image
- engineers managing amazon ecr resources on aws.
- container registry
- describeRepositories
- amazon ecr list images
- oci
- amazon ecr create repository
- createRepository
- deleteRepository
- amazon ecr delete repository
- amazon ecr put image
- amazon ecr describe repositories
- create repository
- batch get image
- amazon ecr
- aws
- ecr
- docker
- container registry management business domain for amazon ecr.
- listImages
- describe repositories
slug: ecr-management
source_filename: ecr-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon ECR Container Registry Management\n  description: Unified capability for managing ECR repositories, container images, and lifecycle policies for DevOps engineers.\n  tags:\n  - Amazon ECR\n  - AWS\n  - Containers\n  - Container Registry\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ecr\n    baseUri: https://api.ecr.us-east-1.amazonaws.com\n    description: Amazon ECR fully managed container registry.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 Credential={{env.AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n    - name: root\n      path: /\n      description: Operations for root resources.\n      operations:\n      - name: createRepository\n        method: POST\n        description:\
  \ Amazon ECR Create Repository\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: The X-Amz-Target parameter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#DescribeRepositories\n      description: 'Operations for #DescribeRepositories resources.'\n      operations:\n      - name: describeRepositories\n        method: POST\n        description: Amazon ECR Describe Repositories\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: The X-Amz-Target parameter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#DeleteRepository\n      description: 'Operations for #DeleteRepository\
  \ resources.'\n      operations:\n      - name: deleteRepository\n        method: POST\n        description: Amazon ECR Delete Repository\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: The X-Amz-Target parameter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#PutImage\n      description: 'Operations for #PutImage resources.'\n      operations:\n      - name: putImage\n        method: POST\n        description: Amazon ECR Put Image\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: The X-Amz-Target parameter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#BatchGetImage\n\
  \      description: 'Operations for #BatchGetImage resources.'\n      operations:\n      - name: batchGetImage\n        method: POST\n        description: Amazon ECR Batch Get Image\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: The X-Amz-Target parameter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#ListImages\n      description: 'Operations for #ListImages resources.'\n      operations:\n      - name: listImages\n        method: POST\n        description: Amazon ECR List Images\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: The X-Amz-Target parameter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: ecr-api\n    description: Unified REST API for Container Registry Management.\n    resources:\n    - path: /v1/resource\n      name: createRepository\n      description: Amazon ECR Create Repository\n      operations:\n      - method: POST\n        name: createRepository\n        description: Amazon ECR Create Repository\n        call: ecr.createRepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#DescribeRepositories\n      name: describeRepositories\n      description: Amazon ECR Describe Repositories\n      operations:\n      - method: POST\n        name: describeRepositories\n        description: Amazon ECR Describe Repositories\n        call: ecr.describeRepositories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#DeleteRepository\n      name: deleteRepository\n      description: Amazon ECR Delete Repository\n      operations:\n\
  \      - method: POST\n        name: deleteRepository\n        description: Amazon ECR Delete Repository\n        call: ecr.deleteRepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#PutImage\n      name: putImage\n      description: Amazon ECR Put Image\n      operations:\n      - method: POST\n        name: putImage\n        description: Amazon ECR Put Image\n        call: ecr.putImage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#BatchGetImage\n      name: batchGetImage\n      description: Amazon ECR Batch Get Image\n      operations:\n      - method: POST\n        name: batchGetImage\n        description: Amazon ECR Batch Get Image\n        call: ecr.batchGetImage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#ListImages\n      name: listImages\n      description: Amazon ECR List Images\n      operations:\n      - method: POST\n        name: listImages\n\
  \        description: Amazon ECR List Images\n        call: ecr.listImages\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: ecr-mcp\n    transport: http\n    description: MCP server for AI-assisted Container Registry Management.\n    tools:\n    - name: create-repository\n      description: Amazon ECR Create Repository\n      hints:\n        readOnly: false\n        destructive: false\n      call: ecr.createRepository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-repositories\n      description: Amazon ECR Describe Repositories\n      hints:\n        readOnly: false\n        destructive: false\n      call: ecr.describeRepositories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-repository\n      description: Amazon ECR Delete Repository\n      hints:\n        readOnly: false\n        destructive: false\n      call: ecr.deleteRepository\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-image\n      description: Amazon ECR Put Image\n      hints:\n        readOnly: false\n        destructive: false\n      call: ecr.putImage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-get-image\n      description: Amazon ECR Batch Get Image\n      hints:\n        readOnly: false\n        destructive: false\n      call: ecr.batchGetImage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-images\n      description: Amazon ECR List Images\n      hints:\n        readOnly: false\n        destructive: false\n      call: ecr.listImages\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-ecr/refs/heads/main/capabilities/ecr-management.yaml
tags:
- Amazon ECR
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

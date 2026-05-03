---
categories: []
consumed_apis:
- ec2-image-builder
description: Unified capability for managing EC2 Image Builder pipelines, recipes, and components for DevOps engineers.
layout: capability
name: Amazon EC2 Image Builder Image Pipeline Management
operations:
- description: Amazon EC2 Image Builder Cancel Image Creation
  method: PUT
  name: CancelImageCreation
  path: /v1/CancelImageCreation
- description: Amazon EC2 Image Builder Create Component
  method: PUT
  name: CreateComponent
  path: /v1/CreateComponent
- description: Amazon EC2 Image Builder Create Container Recipe
  method: PUT
  name: CreateContainerRecipe
  path: /v1/CreateContainerRecipe
- description: Amazon EC2 Image Builder Create Distribution Configuration
  method: PUT
  name: CreateDistributionConfiguration
  path: /v1/CreateDistributionConfiguration
- description: Amazon EC2 Image Builder Create Image
  method: PUT
  name: CreateImage
  path: /v1/CreateImage
- description: Amazon EC2 Image Builder Create Image Pipeline
  method: PUT
  name: CreateImagePipeline
  path: /v1/CreateImagePipeline
- description: Amazon EC2 Image Builder Create Image Recipe
  method: PUT
  name: CreateImageRecipe
  path: /v1/CreateImageRecipe
- description: Amazon EC2 Image Builder Create Infrastructure Configuration
  method: PUT
  name: CreateInfrastructureConfiguration
  path: /v1/CreateInfrastructureConfiguration
- description: Amazon EC2 Image Builder Delete Component
  method: DELETE
  name: DeleteComponent
  path: /v1/DeleteComponent#componentBuildVersionArn
- description: Amazon EC2 Image Builder Delete Container Recipe
  method: DELETE
  name: DeleteContainerRecipe
  path: /v1/DeleteContainerRecipe#containerRecipeArn
personas: []
provider_name: Amazon EC2 Image Builder
provider_slug: amazon-ec2-image-builder
search_terms:
- automation
- amazon ec2 image builder create image
- CreateContainerRecipe
- create infrastructure configuration
- image pipeline management business domain.
- ec2
- cancel image creation
- create image pipeline
- amazon ec2 image builder create container recipe
- CreateImage
- create container recipe
- amazon ec2 image builder create image pipeline
- CreateInfrastructureConfiguration
- aws
- delete container recipe
- DeleteContainerRecipe
- engineers managing amazon ec2 image builder resources.
- create image
- create image recipe
- delete component
- container images
- CreateImageRecipe
- amazon ec2 image builder create distribution configuration
- CancelImageCreation
- amazon ec2 image builder create image recipe
- amazon ec2 image builder
- amazon web services
- amazon ec2 image builder cancel image creation
- image building
- amazon ec2 image builder create infrastructure configuration
- create component
- amazon ec2 image builder delete component
- CreateDistributionConfiguration
- amazon ec2 image builder delete container recipe
- CreateImagePipeline
- create distribution configuration
- CreateComponent
- workflow capability for image pipeline management.
- DeleteComponent
- amazon ec2 image builder create component
- virtual machine images
slug: ec2-image-builder-management
source_filename: ec2-image-builder-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon EC2 Image Builder Image Pipeline Management\"\n  description: \"Unified capability for managing EC2 Image Builder pipelines, recipes, and components for DevOps engineers.\"\n  tags:\n    - Amazon EC2 Image Builder\n    - AWS\n    - EC2\n    - Image Building\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: ec2-image-builder\n      location: ./shared/ec2-image-builder.yaml\n\n  exposes:\n    - type: rest\n      port: 8088\n      namespace: ec2-image-builder-api\n      description: \"Unified REST API for Image Pipeline Management.\"\n      resources:\n        - path: /v1/CancelImageCreation\n          name: CancelImageCreation\n          description: \"Amazon EC2 Image Builder Cancel Image Creation\"\n          operations:\n            - method:\
  \ PUT\n              name: CancelImageCreation\n              description: \"Amazon EC2 Image Builder Cancel Image Creation\"\n              call: \"ec2-image-builder.CancelImageCreation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/CreateComponent\n          name: CreateComponent\n          description: \"Amazon EC2 Image Builder Create Component\"\n          operations:\n            - method: PUT\n              name: CreateComponent\n              description: \"Amazon EC2 Image Builder Create Component\"\n              call: \"ec2-image-builder.CreateComponent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/CreateContainerRecipe\n          name: CreateContainerRecipe\n          description: \"Amazon EC2 Image Builder Create Container Recipe\"\n          operations:\n            - method: PUT\n              name: CreateContainerRecipe\n\
  \              description: \"Amazon EC2 Image Builder Create Container Recipe\"\n              call: \"ec2-image-builder.CreateContainerRecipe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/CreateDistributionConfiguration\n          name: CreateDistributionConfiguration\n          description: \"Amazon EC2 Image Builder Create Distribution Configuration\"\n          operations:\n            - method: PUT\n              name: CreateDistributionConfiguration\n              description: \"Amazon EC2 Image Builder Create Distribution Configuration\"\n              call: \"ec2-image-builder.CreateDistributionConfiguration\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/CreateImage\n          name: CreateImage\n          description: \"Amazon EC2 Image Builder Create Image\"\n          operations:\n            - method: PUT\n              name:\
  \ CreateImage\n              description: \"Amazon EC2 Image Builder Create Image\"\n              call: \"ec2-image-builder.CreateImage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/CreateImagePipeline\n          name: CreateImagePipeline\n          description: \"Amazon EC2 Image Builder Create Image Pipeline\"\n          operations:\n            - method: PUT\n              name: CreateImagePipeline\n              description: \"Amazon EC2 Image Builder Create Image Pipeline\"\n              call: \"ec2-image-builder.CreateImagePipeline\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/CreateImageRecipe\n          name: CreateImageRecipe\n          description: \"Amazon EC2 Image Builder Create Image Recipe\"\n          operations:\n            - method: PUT\n              name: CreateImageRecipe\n              description: \"Amazon EC2\
  \ Image Builder Create Image Recipe\"\n              call: \"ec2-image-builder.CreateImageRecipe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/CreateInfrastructureConfiguration\n          name: CreateInfrastructureConfiguration\n          description: \"Amazon EC2 Image Builder Create Infrastructure Configuration\"\n          operations:\n            - method: PUT\n              name: CreateInfrastructureConfiguration\n              description: \"Amazon EC2 Image Builder Create Infrastructure Configuration\"\n              call: \"ec2-image-builder.CreateInfrastructureConfiguration\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/DeleteComponent#componentBuildVersionArn\n          name: DeleteComponent\n          description: \"Amazon EC2 Image Builder Delete Component\"\n          operations:\n            - method: DELETE\n           \
  \   name: DeleteComponent\n              description: \"Amazon EC2 Image Builder Delete Component\"\n              call: \"ec2-image-builder.DeleteComponent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/DeleteContainerRecipe#containerRecipeArn\n          name: DeleteContainerRecipe\n          description: \"Amazon EC2 Image Builder Delete Container Recipe\"\n          operations:\n            - method: DELETE\n              name: DeleteContainerRecipe\n              description: \"Amazon EC2 Image Builder Delete Container Recipe\"\n              call: \"ec2-image-builder.DeleteContainerRecipe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9098\n      namespace: ec2-image-builder-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Image Pipeline Management.\"\n      tools:\n        - name: cancel-image-creation\n\
  \          description: \"Amazon EC2 Image Builder Cancel Image Creation\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-image-builder.CancelImageCreation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-component\n          description: \"Amazon EC2 Image Builder Create Component\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-image-builder.CreateComponent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-container-recipe\n          description: \"Amazon EC2 Image Builder Create Container Recipe\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-image-builder.CreateContainerRecipe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-distribution-configuration\n\
  \          description: \"Amazon EC2 Image Builder Create Distribution Configuration\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-image-builder.CreateDistributionConfiguration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-image\n          description: \"Amazon EC2 Image Builder Create Image\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-image-builder.CreateImage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-image-pipeline\n          description: \"Amazon EC2 Image Builder Create Image Pipeline\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-image-builder.CreateImagePipeline\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-image-recipe\n\
  \          description: \"Amazon EC2 Image Builder Create Image Recipe\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-image-builder.CreateImageRecipe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-infrastructure-configuration\n          description: \"Amazon EC2 Image Builder Create Infrastructure Configuration\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-image-builder.CreateInfrastructureConfiguration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-component\n          description: \"Amazon EC2 Image Builder Delete Component\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"ec2-image-builder.DeleteComponent\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: delete-container-recipe\n          description: \"Amazon EC2 Image Builder Delete Container Recipe\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"ec2-image-builder.DeleteContainerRecipe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-ec2-image-builder/refs/heads/main/capabilities/ec2-image-builder-management.yaml
tags:
- Amazon EC2 Image Builder
- EC2
- Image Building
tools:
- description: Amazon EC2 Image Builder Cancel Image Creation
  hints:
    destructive: false
    readOnly: false
  name: cancel-image-creation
- description: Amazon EC2 Image Builder Create Component
  hints:
    destructive: false
    readOnly: false
  name: create-component
- description: Amazon EC2 Image Builder Create Container Recipe
  hints:
    destructive: false
    readOnly: false
  name: create-container-recipe
- description: Amazon EC2 Image Builder Create Distribution Configuration
  hints:
    destructive: false
    readOnly: false
  name: create-distribution-configuration
- description: Amazon EC2 Image Builder Create Image
  hints:
    destructive: false
    readOnly: false
  name: create-image
- description: Amazon EC2 Image Builder Create Image Pipeline
  hints:
    destructive: false
    readOnly: false
  name: create-image-pipeline
- description: Amazon EC2 Image Builder Create Image Recipe
  hints:
    destructive: false
    readOnly: false
  name: create-image-recipe
- description: Amazon EC2 Image Builder Create Infrastructure Configuration
  hints:
    destructive: false
    readOnly: false
  name: create-infrastructure-configuration
- description: Amazon EC2 Image Builder Delete Component
  hints:
    destructive: true
    readOnly: false
  name: delete-component
- description: Amazon EC2 Image Builder Delete Container Recipe
  hints:
    destructive: true
    readOnly: false
  name: delete-container-recipe
---

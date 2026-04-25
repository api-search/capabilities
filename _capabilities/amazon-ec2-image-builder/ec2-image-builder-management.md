---
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
- amazon ec2 image builder cancel image creation
- image pipeline management business domain.
- amazon ec2 image builder create distribution configuration
- ec2
- CreateImagePipeline
- virtual machine images
- create container recipe
- amazon web services
- delete component
- amazon ec2 image builder delete container recipe
- CreateDistributionConfiguration
- create distribution configuration
- amazon ec2 image builder delete component
- create infrastructure configuration
- amazon ec2 image builder create image pipeline
- create image
- automation
- CreateComponent
- amazon ec2 image builder create infrastructure configuration
- aws
- CreateImage
- amazon ec2 image builder
- amazon ec2 image builder create component
- CreateImageRecipe
- amazon ec2 image builder create image
- delete container recipe
- CancelImageCreation
- CreateContainerRecipe
- cancel image creation
- DeleteContainerRecipe
- create image recipe
- workflow capability for image pipeline management.
- container images
- CreateInfrastructureConfiguration
- amazon ec2 image builder create image recipe
- DeleteComponent
- create image pipeline
- amazon ec2 image builder create container recipe
- image building
- engineers managing amazon ec2 image builder resources.
- create component
slug: ec2-image-builder-management
tags:
- Amazon EC2 Image Builder
- AWS
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

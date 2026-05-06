---
categories: []
consumed_apis: []
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
- amazon ec2 image builder create image pipeline
- aws
- create image pipeline
- amazon web services
- amazon ec2 image builder create component
- create infrastructure configuration
- amazon ec2 image builder create image
- CreateImageRecipe
- amazon ec2 image builder create image recipe
- DeleteContainerRecipe
- engineers managing amazon ec2 image builder resources.
- container images
- CreateInfrastructureConfiguration
- create component
- amazon ec2 image builder create container recipe
- CreateDistributionConfiguration
- image pipeline management business domain.
- create image recipe
- create container recipe
- amazon ec2 image builder create distribution configuration
- CreateImagePipeline
- virtual machine images
- delete container recipe
- ec2
- workflow capability for image pipeline management.
- amazon ec2 image builder create infrastructure configuration
- amazon ec2 image builder delete component
- amazon ec2 image builder delete container recipe
- DeleteComponent
- amazon ec2 image builder
- image building
- cancel image creation
- create distribution configuration
- CreateContainerRecipe
- create image
- CancelImageCreation
- amazon ec2 image builder cancel image creation
- CreateComponent
- CreateImage
- delete component
- automation
slug: ec2-image-builder-management
source_filename: ec2-image-builder-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon EC2 Image Builder Image Pipeline Management\n  description: Unified capability for managing EC2 Image Builder pipelines, recipes, and components for DevOps engineers.\n  tags:\n  - Amazon EC2 Image Builder\n  - AWS\n  - EC2\n  - Image Building\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ec2-image-builder\n    baseUri: https://imagebuilder.amazonaws.com\n    description: Amazon EC2 Image Builder automated image building service.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 Credential={{env.AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n    - name: CancelImageCreation\n      path: /CancelImageCreation\n      description: CancelImageCreation operations.\n      operations:\n  \
  \    - name: CancelImageCreation\n        method: PUT\n        description: Amazon EC2 Image Builder Cancel Image Creation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: CreateComponent\n      path: /CreateComponent\n      description: CreateComponent operations.\n      operations:\n      - name: CreateComponent\n        method: PUT\n        description: Amazon EC2 Image Builder Create Component\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: CreateContainerRecipe\n      path: /CreateContainerRecipe\n      description: CreateContainerRecipe operations.\n      operations:\n      - name: CreateContainerRecipe\n        method: PUT\n        description: Amazon EC2 Image Builder Create Container Recipe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: CreateDistributionConfiguration\n      path: /CreateDistributionConfiguration\n      description: CreateDistributionConfiguration operations.\n      operations:\n      - name: CreateDistributionConfiguration\n        method: PUT\n        description: Amazon EC2 Image Builder Create Distribution Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: CreateImage\n      path: /CreateImage\n      description: CreateImage operations.\n      operations:\n      - name: CreateImage\n        method: PUT\n        description: Amazon EC2 Image Builder Create Image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: CreateImagePipeline\n      path: /CreateImagePipeline\n      description: CreateImagePipeline operations.\n      operations:\n      - name: CreateImagePipeline\n     \
  \   method: PUT\n        description: Amazon EC2 Image Builder Create Image Pipeline\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: CreateImageRecipe\n      path: /CreateImageRecipe\n      description: CreateImageRecipe operations.\n      operations:\n      - name: CreateImageRecipe\n        method: PUT\n        description: Amazon EC2 Image Builder Create Image Recipe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: CreateInfrastructureConfiguration\n      path: /CreateInfrastructureConfiguration\n      description: CreateInfrastructureConfiguration operations.\n      operations:\n      - name: CreateInfrastructureConfiguration\n        method: PUT\n        description: Amazon EC2 Image Builder Create Infrastructure Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: DeleteComponent#componentBuildVersionArn\n      path: /DeleteComponent#componentBuildVersionArn\n      description: DeleteComponent#componentBuildVersionArn operations.\n      operations:\n      - name: DeleteComponent\n        method: DELETE\n        description: Amazon EC2 Image Builder Delete Component\n        inputParameters:\n        - name: componentBuildVersionArn\n          in: query\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the component build version to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: DeleteContainerRecipe#containerRecipeArn\n      path: /DeleteContainerRecipe#containerRecipeArn\n      description: DeleteContainerRecipe#containerRecipeArn operations.\n      operations:\n      - name: DeleteContainerRecipe\n        method: DELETE\n\
  \        description: Amazon EC2 Image Builder Delete Container Recipe\n        inputParameters:\n        - name: containerRecipeArn\n          in: query\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the container recipe to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: DeleteDistributionConfiguration#distributionConfigurationArn\n      path: /DeleteDistributionConfiguration#distributionConfigurationArn\n      description: DeleteDistributionConfiguration#distributionConfigurationArn operations.\n      operations:\n      - name: DeleteDistributionConfiguration\n        method: DELETE\n        description: Amazon EC2 Image Builder Delete Distribution Configuration\n        inputParameters:\n        - name: distributionConfigurationArn\n          in: query\n          type: string\n          required: true\n          description:\
  \ The Amazon Resource Name (ARN) of the distribution configuration to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: DeleteImage#imageBuildVersionArn\n      path: /DeleteImage#imageBuildVersionArn\n      description: DeleteImage#imageBuildVersionArn operations.\n      operations:\n      - name: DeleteImage\n        method: DELETE\n        description: Amazon EC2 Image Builder Delete Image\n        inputParameters:\n        - name: imageBuildVersionArn\n          in: query\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the Image Builder image resource to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: DeleteImagePipeline#imagePipelineArn\n      path: /DeleteImagePipeline#imagePipelineArn\n      description: DeleteImagePipeline#imagePipelineArn\
  \ operations.\n      operations:\n      - name: DeleteImagePipeline\n        method: DELETE\n        description: Amazon EC2 Image Builder Delete Image Pipeline\n        inputParameters:\n        - name: imagePipelineArn\n          in: query\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the image pipeline to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: DeleteImageRecipe#imageRecipeArn\n      path: /DeleteImageRecipe#imageRecipeArn\n      description: DeleteImageRecipe#imageRecipeArn operations.\n      operations:\n      - name: DeleteImageRecipe\n        method: DELETE\n        description: Amazon EC2 Image Builder Delete Image Recipe\n        inputParameters:\n        - name: imageRecipeArn\n          in: query\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the image\
  \ recipe to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: DeleteInfrastructureConfiguration#infrastructureConfigurationArn\n      path: /DeleteInfrastructureConfiguration#infrastructureConfigurationArn\n      description: DeleteInfrastructureConfiguration#infrastructureConfigurationArn operations.\n      operations:\n      - name: DeleteInfrastructureConfiguration\n        method: DELETE\n        description: Amazon EC2 Image Builder Delete Infrastructure Configuration\n        inputParameters:\n        - name: infrastructureConfigurationArn\n          in: query\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the infrastructure configuration to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8088\n    namespace:\
  \ ec2-image-builder-api\n    description: Unified REST API for Image Pipeline Management.\n    resources:\n    - path: /v1/CancelImageCreation\n      name: CancelImageCreation\n      description: Amazon EC2 Image Builder Cancel Image Creation\n      operations:\n      - method: PUT\n        name: CancelImageCreation\n        description: Amazon EC2 Image Builder Cancel Image Creation\n        call: ec2-image-builder.CancelImageCreation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateComponent\n      name: CreateComponent\n      description: Amazon EC2 Image Builder Create Component\n      operations:\n      - method: PUT\n        name: CreateComponent\n        description: Amazon EC2 Image Builder Create Component\n        call: ec2-image-builder.CreateComponent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateContainerRecipe\n      name: CreateContainerRecipe\n      description: Amazon EC2\
  \ Image Builder Create Container Recipe\n      operations:\n      - method: PUT\n        name: CreateContainerRecipe\n        description: Amazon EC2 Image Builder Create Container Recipe\n        call: ec2-image-builder.CreateContainerRecipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateDistributionConfiguration\n      name: CreateDistributionConfiguration\n      description: Amazon EC2 Image Builder Create Distribution Configuration\n      operations:\n      - method: PUT\n        name: CreateDistributionConfiguration\n        description: Amazon EC2 Image Builder Create Distribution Configuration\n        call: ec2-image-builder.CreateDistributionConfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateImage\n      name: CreateImage\n      description: Amazon EC2 Image Builder Create Image\n      operations:\n      - method: PUT\n        name: CreateImage\n        description: Amazon\
  \ EC2 Image Builder Create Image\n        call: ec2-image-builder.CreateImage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateImagePipeline\n      name: CreateImagePipeline\n      description: Amazon EC2 Image Builder Create Image Pipeline\n      operations:\n      - method: PUT\n        name: CreateImagePipeline\n        description: Amazon EC2 Image Builder Create Image Pipeline\n        call: ec2-image-builder.CreateImagePipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateImageRecipe\n      name: CreateImageRecipe\n      description: Amazon EC2 Image Builder Create Image Recipe\n      operations:\n      - method: PUT\n        name: CreateImageRecipe\n        description: Amazon EC2 Image Builder Create Image Recipe\n        call: ec2-image-builder.CreateImageRecipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateInfrastructureConfiguration\n\
  \      name: CreateInfrastructureConfiguration\n      description: Amazon EC2 Image Builder Create Infrastructure Configuration\n      operations:\n      - method: PUT\n        name: CreateInfrastructureConfiguration\n        description: Amazon EC2 Image Builder Create Infrastructure Configuration\n        call: ec2-image-builder.CreateInfrastructureConfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DeleteComponent#componentBuildVersionArn\n      name: DeleteComponent\n      description: Amazon EC2 Image Builder Delete Component\n      operations:\n      - method: DELETE\n        name: DeleteComponent\n        description: Amazon EC2 Image Builder Delete Component\n        call: ec2-image-builder.DeleteComponent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DeleteContainerRecipe#containerRecipeArn\n      name: DeleteContainerRecipe\n      description: Amazon EC2 Image Builder Delete Container\
  \ Recipe\n      operations:\n      - method: DELETE\n        name: DeleteContainerRecipe\n        description: Amazon EC2 Image Builder Delete Container Recipe\n        call: ec2-image-builder.DeleteContainerRecipe\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9098\n    namespace: ec2-image-builder-mcp\n    transport: http\n    description: MCP server for AI-assisted Image Pipeline Management.\n    tools:\n    - name: cancel-image-creation\n      description: Amazon EC2 Image Builder Cancel Image Creation\n      hints:\n        readOnly: false\n        destructive: false\n      call: ec2-image-builder.CancelImageCreation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-component\n      description: Amazon EC2 Image Builder Create Component\n      hints:\n        readOnly: false\n        destructive: false\n      call: ec2-image-builder.CreateComponent\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: create-container-recipe\n      description: Amazon EC2 Image Builder Create Container Recipe\n      hints:\n        readOnly: false\n        destructive: false\n      call: ec2-image-builder.CreateContainerRecipe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-distribution-configuration\n      description: Amazon EC2 Image Builder Create Distribution Configuration\n      hints:\n        readOnly: false\n        destructive: false\n      call: ec2-image-builder.CreateDistributionConfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-image\n      description: Amazon EC2 Image Builder Create Image\n      hints:\n        readOnly: false\n        destructive: false\n      call: ec2-image-builder.CreateImage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-image-pipeline\n      description: Amazon EC2 Image Builder Create Image Pipeline\n\
  \      hints:\n        readOnly: false\n        destructive: false\n      call: ec2-image-builder.CreateImagePipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-image-recipe\n      description: Amazon EC2 Image Builder Create Image Recipe\n      hints:\n        readOnly: false\n        destructive: false\n      call: ec2-image-builder.CreateImageRecipe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-infrastructure-configuration\n      description: Amazon EC2 Image Builder Create Infrastructure Configuration\n      hints:\n        readOnly: false\n        destructive: false\n      call: ec2-image-builder.CreateInfrastructureConfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-component\n      description: Amazon EC2 Image Builder Delete Component\n      hints:\n        readOnly: false\n        destructive: true\n      call: ec2-image-builder.DeleteComponent\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-container-recipe\n      description: Amazon EC2 Image Builder Delete Container Recipe\n      hints:\n        readOnly: false\n        destructive: true\n      call: ec2-image-builder.DeleteContainerRecipe\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

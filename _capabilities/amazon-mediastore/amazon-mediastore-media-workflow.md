---
categories: []
consumed_apis:
- mediastore
description: Workflow capability for Amazon MediaStore media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon MediaStore Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon MediaStore
provider_slug: amazon-mediastore
search_terms:
- developer building media processing applications
- deletecontainerpolicy
- delete cors policy
- Media Developer
- deletelifecyclepolicy
- amazon mediastore media processing workflow
- engineer managing broadcast media workflows
- describecontainer
- delete container policy
- list jobs
- aws
- create container
- deletecorspolicy
- getcontainerpolicy
- deletecontainer
- workflow
- aws media processing and delivery
- broadcasting
- describe container
- Broadcast Engineer
- deletemetricpolicy
- get container policy
- manage media processing jobs
- delete container
- createcontainer
- media processing
- delete lifecycle policy
- media
- delete metric policy
slug: amazon-mediastore-media-workflow
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon MediaStore Workflow\n  description: Workflow capability for Amazon MediaStore media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: mediastore\n    location: ./shared/mediastore.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mediastore-workflow-api\n    description: Unified REST API for Amazon MediaStore workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: mediastore.list-jobs\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mediastore-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MediaStore workflow management.\n    tools:\n    - name: create-container\n      description: CreateContainer\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.create-container\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-container\n      description: DeleteContainer\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.delete-container\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-container-policy\n      description: DeleteContainerPolicy\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.delete-container-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cors-policy\n\
  \      description: DeleteCorsPolicy\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.delete-cors-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-lifecycle-policy\n      description: DeleteLifecyclePolicy\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.delete-lifecycle-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-metric-policy\n      description: DeleteMetricPolicy\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.delete-metric-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-container\n      description: DescribeContainer\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.describe-container\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-container-policy\n\
  \      description: GetContainerPolicy\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.get-container-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mediastore/refs/heads/main/capabilities/amazon-mediastore-media-workflow.yaml
tags:
- AWS
- Media
- Broadcasting
- Workflow
tools:
- description: CreateContainer
  hints:
    openWorld: true
    readOnly: false
  name: create-container
- description: DeleteContainer
  hints:
    openWorld: true
    readOnly: false
  name: delete-container
- description: DeleteContainerPolicy
  hints:
    openWorld: true
    readOnly: false
  name: delete-container-policy
- description: DeleteCorsPolicy
  hints:
    openWorld: true
    readOnly: false
  name: delete-cors-policy
- description: DeleteLifecyclePolicy
  hints:
    openWorld: true
    readOnly: false
  name: delete-lifecycle-policy
- description: DeleteMetricPolicy
  hints:
    openWorld: true
    readOnly: false
  name: delete-metric-policy
- description: DescribeContainer
  hints:
    openWorld: true
    readOnly: false
  name: describe-container
- description: GetContainerPolicy
  hints:
    openWorld: true
    readOnly: false
  name: get-container-policy
---

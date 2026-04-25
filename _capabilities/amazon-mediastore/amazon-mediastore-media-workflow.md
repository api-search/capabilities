---
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
- media
- manage media processing jobs
- delete container
- delete container policy
- create container
- deletelifecyclepolicy
- describe container
- describecontainer
- deletecontainerpolicy
- delete cors policy
- deletecontainer
- delete metric policy
- deletemetricpolicy
- aws
- list jobs
- createcontainer
- getcontainerpolicy
- deletecorspolicy
- developer building media processing applications
- media processing
- delete lifecycle policy
- workflow
- get container policy
- Media Developer
- engineer managing broadcast media workflows
- broadcasting
- aws media processing and delivery
- amazon mediastore media processing workflow
- Broadcast Engineer
slug: amazon-mediastore-media-workflow
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

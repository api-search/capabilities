---
categories: []
consumed_apis: []
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
- amazon mediastore media processing workflow
- deletemetricpolicy
- create container
- delete container policy
- describecontainer
- developer building media processing applications
- delete lifecycle policy
- createcontainer
- delete metric policy
- get container policy
- engineer managing broadcast media workflows
- deletecontainer
- Media Developer
- workflow
- delete cors policy
- delete container
- deletecontainerpolicy
- describe container
- deletelifecyclepolicy
- aws media processing and delivery
- list jobs
- manage media processing jobs
- media
- getcontainerpolicy
- media processing
- aws
- broadcasting
- Broadcast Engineer
- deletecorspolicy
slug: amazon-mediastore-media-workflow
source_filename: amazon-mediastore-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon MediaStore Workflow\n  description: Workflow capability for Amazon MediaStore media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: mediastore\n    baseUri: http://mediastore.{region}.amazonaws.com\n    description: Amazon MediaStore REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: default\n      path: /\n      description: Amazon MediaStore resources\n      operations:\n      - name: create-container\n        method: POST\n        description: CreateContainer\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: delete-container\n        method: POST\n        description: DeleteContainer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: delete-container-policy\n        method: POST\n        description: DeleteContainerPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: delete-cors-policy\n        method: POST\n        description: DeleteCorsPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: delete-lifecycle-policy\n        method: POST\n        description: DeleteLifecyclePolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n\
  \          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: delete-metric-policy\n        method: POST\n        description: DeleteMetricPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: describe-container\n        method: POST\n        description: DescribeContainer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n     \
  \     data: {}\n      - name: get-container-policy\n        method: POST\n        description: GetContainerPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: get-cors-policy\n        method: POST\n        description: GetCorsPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: get-lifecycle-policy\n        method: POST\n        description: GetLifecyclePolicy\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: get-metric-policy\n        method: POST\n        description: GetMetricPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: list-containers\n        method: POST\n        description: ListContainers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: list-tags-for-resource\n        method: POST\n        description: ListTagsForResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: put-container-policy\n   \
  \     method: POST\n        description: PutContainerPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: put-cors-policy\n        method: POST\n        description: PutCorsPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: put-lifecycle-policy\n        method: POST\n        description: PutLifecyclePolicy\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: put-metric-policy\n        method: POST\n        description: PutMetricPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: start-access-logging\n        method: POST\n        description: StartAccessLogging\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name:\
  \ X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: stop-access-logging\n        method: POST\n        description: StopAccessLogging\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: tag-resource\n        method: POST\n        description: TagResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n\
  \        body:\n          type: json\n          data: {}\n      - name: untag-resource\n        method: POST\n        description: UntagResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mediastore-workflow-api\n    description: Unified REST API for Amazon MediaStore workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: mediastore.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n\
  \    namespace: mediastore-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MediaStore workflow management.\n    tools:\n    - name: create-container\n      description: CreateContainer\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.create-container\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-container\n      description: DeleteContainer\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.delete-container\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-container-policy\n      description: DeleteContainerPolicy\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.delete-container-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cors-policy\n      description: DeleteCorsPolicy\n      hints:\n        readOnly: false\n\
  \        openWorld: true\n      call: mediastore.delete-cors-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-lifecycle-policy\n      description: DeleteLifecyclePolicy\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.delete-lifecycle-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-metric-policy\n      description: DeleteMetricPolicy\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.delete-metric-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-container\n      description: DescribeContainer\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mediastore.describe-container\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-container-policy\n      description: GetContainerPolicy\n      hints:\n        readOnly: false\n\
  \        openWorld: true\n      call: mediastore.get-container-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mediastore/refs/heads/main/capabilities/amazon-mediastore-media-workflow.yaml
tags:
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

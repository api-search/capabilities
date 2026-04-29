---
categories: []
consumed_apis:
- eventbridge_pipes
description: Unified capability for managing Amazon EventBridge Pipes resources. Combines Amazon EventBridge Pipes APIs for Integration Engineer workflows in Event Processing.
layout: capability
name: Amazon EventBridge Pipes Management
operations:
- description: Amazon EventBridge Pipes DescribePipe
  method: GET
  name: DescribePipe
  path: /v1/DescribePipe
- description: Amazon EventBridge Pipes CreatePipe
  method: POST
  name: CreatePipe
  path: /v1/CreatePipe
- description: Amazon EventBridge Pipes UpdatePipe
  method: POST
  name: UpdatePipe
  path: /v1/UpdatePipe
- description: Amazon EventBridge Pipes DeletePipe
  method: POST
  name: DeletePipe
  path: /v1/DeletePipe
- description: Amazon EventBridge Pipes ListPipes
  method: GET
  name: ListPipes
  path: /v1/ListPipes
- description: Amazon EventBridge Pipes ListTagsForResource
  method: GET
  name: ListTagsForResource
  path: /v1/ListTagsForResource
- description: Amazon EventBridge Pipes TagResource
  method: POST
  name: TagResource
  path: /v1/TagResource
- description: Amazon EventBridge Pipes StartPipe
  method: POST
  name: StartPipe
  path: /v1/StartPipe
- description: Amazon EventBridge Pipes StopPipe
  method: POST
  name: StopPipe
  path: /v1/StopPipe
- description: Amazon EventBridge Pipes UntagResource
  method: POST
  name: UntagResource
  path: /v1/UntagResource
personas: []
provider_name: Amazon EventBridge Pipes
provider_slug: amazon-eventbridge-pipes
search_terms:
- amazon eventbridge pipes listtagsforresource
- developers building applications using amazon eventbridge pipes
- StopPipe
- amazon eventbridge pipes describepipe
- amazon eventbridge pipes tagresource
- CreatePipe
- amazon eventbridge pipes stoppipe
- messaging
- amazon eventbridge pipes updatepipe
- integration
- TagResource
- operations teams managing amazon eventbridge pipes infrastructure
- event-driven
- aws
- serverless
- UpdatePipe
- amazon eventbridge pipes deletepipe
- UntagResource
- DeletePipe
- DescribePipe
- StartPipe
- unified capability for managing amazon eventbridge pipes resources. combines amazon eventbridge pipes apis for integration engineer workflows in event processing.
- amazon web services
- amazon eventbridge pipes untagresource
- point-to-point integration between event producers and consumers
- ListPipes
- amazon eventbridge pipes startpipe
- amazon eventbridge pipes createpipe
- ListTagsForResource
- amazon eventbridge pipes listpipes
slug: amazon-eventbridge-pipes-capability
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon EventBridge Pipes Management\n  description: Unified capability for managing Amazon EventBridge Pipes resources. Combines Amazon EventBridge Pipes APIs for Integration Engineer workflows in Event Processing.\n  tags:\n  - Amazon Web Services\n  - Event-Driven\n  - Integration\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_API_KEY: AWS_API_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: eventbridge_pipes\n    location: ./shared/eventbridge-pipes.yaml\n  exposes:\n  - type: rest\n    port: 8192\n    namespace: amazon-eventbridge-pipes-workflow-api\n    description: Unified REST API for Amazon EventBridge Pipes management.\n    resources:\n    - path: /v1/DescribePipe\n      name: DescribePipe\n      description: Amazon EventBridge Pipes DescribePipe\n      operations:\n      - method: GET\n        name: DescribePipe\n        description: Amazon EventBridge Pipes\
  \ DescribePipe\n        call: api.DescribePipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreatePipe\n      name: CreatePipe\n      description: Amazon EventBridge Pipes CreatePipe\n      operations:\n      - method: POST\n        name: CreatePipe\n        description: Amazon EventBridge Pipes CreatePipe\n        call: api.CreatePipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/UpdatePipe\n      name: UpdatePipe\n      description: Amazon EventBridge Pipes UpdatePipe\n      operations:\n      - method: POST\n        name: UpdatePipe\n        description: Amazon EventBridge Pipes UpdatePipe\n        call: api.UpdatePipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DeletePipe\n      name: DeletePipe\n      description: Amazon EventBridge Pipes DeletePipe\n      operations:\n      - method: POST\n        name: DeletePipe\n        description: Amazon EventBridge\
  \ Pipes DeletePipe\n        call: api.DeletePipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListPipes\n      name: ListPipes\n      description: Amazon EventBridge Pipes ListPipes\n      operations:\n      - method: GET\n        name: ListPipes\n        description: Amazon EventBridge Pipes ListPipes\n        call: api.ListPipes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListTagsForResource\n      name: ListTagsForResource\n      description: Amazon EventBridge Pipes ListTagsForResource\n      operations:\n      - method: GET\n        name: ListTagsForResource\n        description: Amazon EventBridge Pipes ListTagsForResource\n        call: api.ListTagsForResource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/TagResource\n      name: TagResource\n      description: Amazon EventBridge Pipes TagResource\n      operations:\n      - method: POST\n   \
  \     name: TagResource\n        description: Amazon EventBridge Pipes TagResource\n        call: api.TagResource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/StartPipe\n      name: StartPipe\n      description: Amazon EventBridge Pipes StartPipe\n      operations:\n      - method: POST\n        name: StartPipe\n        description: Amazon EventBridge Pipes StartPipe\n        call: api.StartPipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/StopPipe\n      name: StopPipe\n      description: Amazon EventBridge Pipes StopPipe\n      operations:\n      - method: POST\n        name: StopPipe\n        description: Amazon EventBridge Pipes StopPipe\n        call: api.StopPipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/UntagResource\n      name: UntagResource\n      description: Amazon EventBridge Pipes UntagResource\n      operations:\n      - method: POST\n\
  \        name: UntagResource\n        description: Amazon EventBridge Pipes UntagResource\n        call: api.UntagResource\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9202\n    namespace: amazon-eventbridge-pipes-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon EventBridge Pipes management.\n    tools:\n    - name: DescribePipe\n      description: Amazon EventBridge Pipes DescribePipe\n      hints:\n        readOnly: true\n      call: api.DescribePipe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: CreatePipe\n      description: Amazon EventBridge Pipes CreatePipe\n      hints:\n        readOnly: false\n      call: api.CreatePipe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: UpdatePipe\n      description: Amazon EventBridge Pipes UpdatePipe\n      hints:\n        readOnly: false\n      call: api.UpdatePipe\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: DeletePipe\n      description: Amazon EventBridge Pipes DeletePipe\n      hints:\n        readOnly: false\n      call: api.DeletePipe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListPipes\n      description: Amazon EventBridge Pipes ListPipes\n      hints:\n        readOnly: true\n      call: api.ListPipes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListTagsForResource\n      description: Amazon EventBridge Pipes ListTagsForResource\n      hints:\n        readOnly: true\n      call: api.ListTagsForResource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: TagResource\n      description: Amazon EventBridge Pipes TagResource\n      hints:\n        readOnly: false\n      call: api.TagResource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: StartPipe\n      description: Amazon EventBridge Pipes StartPipe\n\
  \      hints:\n        readOnly: false\n      call: api.StartPipe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: StopPipe\n      description: Amazon EventBridge Pipes StopPipe\n      hints:\n        readOnly: false\n      call: api.StopPipe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: UntagResource\n      description: Amazon EventBridge Pipes UntagResource\n      hints:\n        readOnly: false\n      call: api.UntagResource\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-eventbridge-pipes/refs/heads/main/capabilities/amazon-eventbridge-pipes-capability.yaml
tags:
- Amazon Web Services
- Event-Driven
- Integration
tools:
- description: Amazon EventBridge Pipes DescribePipe
  hints:
    readOnly: true
  name: DescribePipe
- description: Amazon EventBridge Pipes CreatePipe
  hints:
    readOnly: false
  name: CreatePipe
- description: Amazon EventBridge Pipes UpdatePipe
  hints:
    readOnly: false
  name: UpdatePipe
- description: Amazon EventBridge Pipes DeletePipe
  hints:
    readOnly: false
  name: DeletePipe
- description: Amazon EventBridge Pipes ListPipes
  hints:
    readOnly: true
  name: ListPipes
- description: Amazon EventBridge Pipes ListTagsForResource
  hints:
    readOnly: true
  name: ListTagsForResource
- description: Amazon EventBridge Pipes TagResource
  hints:
    readOnly: false
  name: TagResource
- description: Amazon EventBridge Pipes StartPipe
  hints:
    readOnly: false
  name: StartPipe
- description: Amazon EventBridge Pipes StopPipe
  hints:
    readOnly: false
  name: StopPipe
- description: Amazon EventBridge Pipes UntagResource
  hints:
    readOnly: false
  name: UntagResource
---

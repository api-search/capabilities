---
categories: []
consumed_apis: []
description: Amazon EventBridge Pipes connects event sources to targets. Pipes reduces the need for specialized knowledge and integration code when developing event driven architectures. This helps ensures consistency across your company’s applications. With Pipes, the target can be any available EventBridge target. To set up a pipe, you select the event source, add optional event filtering, define optional enrichment, and select the target for the event data.
layout: capability
name: Amazon EventBridge Pipes
operations:
- description: Amazon EventBridge Pipes CreatePipe
  method: POST
  name: createpipe
  path: /v1/pipes/{Name}
- description: Amazon EventBridge Pipes DeletePipe
  method: DELETE
  name: deletepipe
  path: /v1/pipes/{Name}
- description: Amazon EventBridge Pipes DescribePipe
  method: GET
  name: describepipe
  path: /v1/pipes/{Name}
- description: Amazon EventBridge Pipes UpdatePipe
  method: PUT
  name: updatepipe
  path: /v1/pipes/{Name}
- description: Amazon EventBridge Pipes ListPipes
  method: GET
  name: listpipes
  path: /v1/pipes
- description: Amazon EventBridge Pipes ListTagsForResource
  method: GET
  name: listtagsforresource
  path: /tags/{resourceArn}
- description: Amazon EventBridge Pipes TagResource
  method: POST
  name: tagresource
  path: /tags/{resourceArn}
- description: Amazon EventBridge Pipes StartPipe
  method: POST
  name: startpipe
  path: /v1/pipes/{Name}/start
- description: Amazon EventBridge Pipes StopPipe
  method: POST
  name: stoppipe
  path: /v1/pipes/{Name}/stop
- description: Amazon EventBridge Pipes UntagResource
  method: DELETE
  name: untagresource
  path: /tags/{resourceArn}#tagKeys
personas: []
provider_name: Amazon EventBridge Pipes
provider_slug: amazon-eventbridge-pipes
search_terms:
- eventbridge
- listtagsforresource
- amazon eventbridge pipes tagresource
- event-driven
- amazon web services
- amazon eventbridge pipes describepipe
- amazon eventbridge pipes stoppipe
- startpipe
- amazon eventbridge pipes deletepipe
- api
- deletepipe
- amazon
- developers building applications using amazon eventbridge pipes
- integration
- serverless
- amazon eventbridge pipes updatepipe
- point-to-point integration between event producers and consumers
- tagresource
- describepipe
- operations teams managing amazon eventbridge pipes infrastructure
- stoppipe
- createpipe
- amazon eventbridge pipes listtagsforresource
- amazon eventbridge pipes listpipes
- untagresource
- amazon eventbridge pipes untagresource
- amazon eventbridge pipes createpipe
- listpipes
- unified capability for managing amazon eventbridge pipes resources. combines amazon eventbridge pipes apis for integration engineer workflows in event processing.
- pipes
- amazon eventbridge pipes startpipe
- messaging
- updatepipe
slug: amazon-eventbridge-pipes-capability
source_filename: amazon-eventbridge-pipes-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon EventBridge Pipes\n  description: Amazon EventBridge Pipes connects event sources to targets. Pipes reduces the need for specialized knowledge\n    and integration code when developing event driven architectures. This helps ensures consistency across your company’s\n    applications. With Pipes, the target can be any available EventBridge target. To set up a pipe, you select the event source,\n    add optional event filtering, define optional enrichment, and select the target for the event data.\n  tags:\n  - Amazon\n  - Eventbridge\n  - Pipes\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-eventbridge-pipes\n    baseUri: http://pipes.us-east-1.amazonaws.com\n    description: Amazon EventBridge Pipes HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AMAZON_EVENTBRIDGE_PIPES_TOKEN}}'\n    resources:\n\
  \    - name: v1-pipes-name\n      path: /v1/pipes/{Name}\n      operations:\n      - name: createpipe\n        method: POST\n        description: Amazon EventBridge Pipes CreatePipe\n        inputParameters:\n        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the pipe.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepipe\n        method: DELETE\n        description: Amazon EventBridge Pipes DeletePipe\n        inputParameters:\n        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the pipe.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describepipe\n        method: GET\n        description: Amazon EventBridge Pipes DescribePipe\n        inputParameters:\n\
  \        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the pipe.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepipe\n        method: PUT\n        description: Amazon EventBridge Pipes UpdatePipe\n        inputParameters:\n        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the pipe.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-pipes\n      path: /v1/pipes\n      operations:\n      - name: listpipes\n        method: GET\n        description: Amazon EventBridge Pipes ListPipes\n        inputParameters:\n        - name: CurrentState\n          in: query\n          type: string\n          description: The state the pipe is in.\n        - name: DesiredState\n\
  \          in: query\n          type: string\n          description: The state the pipe should be in.\n        - name: Limit\n          in: query\n          type: integer\n          description: The maximum number of pipes to include in the response.\n        - name: NamePrefix\n          in: query\n          type: string\n          description: 'A value that will return a subset of the pipes associated with this account. For example, <code>\"NamePrefix\":\n            \"ABC\"</code> will return all endpoints with \"ABC\" '\n        - name: NextToken\n          in: query\n          type: string\n          description: If <code>nextToken</code> is returned, there are more results available. The value of <code>nextToken</code>\n            is a unique pagination token for each page. Make th\n        - name: SourcePrefix\n          in: query\n          type: string\n          description: The prefix matching the pipe source.\n        - name: TargetPrefix\n          in: query\n          type:\
  \ string\n          description: The prefix matching the pipe target.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags-resourcearn\n      path: /tags/{resourceArn}\n      operations:\n      - name: listtagsforresource\n        method: GET\n        description: Amazon EventBridge Pipes ListTagsForResource\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the pipe for which you want to view tags.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: tagresource\n        method: POST\n        description: Amazon EventBridge Pipes TagResource\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the\
  \ pipe.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-pipes-name-start\n      path: /v1/pipes/{Name}/start\n      operations:\n      - name: startpipe\n        method: POST\n        description: Amazon EventBridge Pipes StartPipe\n        inputParameters:\n        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the pipe.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-pipes-name-stop\n      path: /v1/pipes/{Name}/stop\n      operations:\n      - name: stoppipe\n        method: POST\n        description: Amazon EventBridge Pipes StopPipe\n        inputParameters:\n        - name: Name\n          in: path\n          type: string\n          required: true\n          description: The name of the pipe.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags-resourcearn-tagkeys\n      path: /tags/{resourceArn}#tagKeys\n      operations:\n      - name: untagresource\n        method: DELETE\n        description: Amazon EventBridge Pipes UntagResource\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the pipe.\n        - name: tagKeys\n          in: query\n          type: array\n          required: true\n          description: The list of tag keys to remove from the pipe.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-eventbridge-pipes-rest\n    description: REST adapter for Amazon EventBridge Pipes.\n    resources:\n    - path: /v1/pipes/{Name}\n      name: createpipe\n      operations:\n\
  \      - method: POST\n        name: createpipe\n        description: Amazon EventBridge Pipes CreatePipe\n        call: amazon-eventbridge-pipes.createpipe\n        with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipes/{Name}\n      name: deletepipe\n      operations:\n      - method: DELETE\n        name: deletepipe\n        description: Amazon EventBridge Pipes DeletePipe\n        call: amazon-eventbridge-pipes.deletepipe\n        with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipes/{Name}\n      name: describepipe\n      operations:\n      - method: GET\n        name: describepipe\n        description: Amazon EventBridge Pipes DescribePipe\n        call: amazon-eventbridge-pipes.describepipe\n        with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipes/{Name}\n\
  \      name: updatepipe\n      operations:\n      - method: PUT\n        name: updatepipe\n        description: Amazon EventBridge Pipes UpdatePipe\n        call: amazon-eventbridge-pipes.updatepipe\n        with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipes\n      name: listpipes\n      operations:\n      - method: GET\n        name: listpipes\n        description: Amazon EventBridge Pipes ListPipes\n        call: amazon-eventbridge-pipes.listpipes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{resourceArn}\n      name: listtagsforresource\n      operations:\n      - method: GET\n        name: listtagsforresource\n        description: Amazon EventBridge Pipes ListTagsForResource\n        call: amazon-eventbridge-pipes.listtagsforresource\n        with:\n          resourceArn: rest.resourceArn\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /tags/{resourceArn}\n      name: tagresource\n      operations:\n      - method: POST\n        name: tagresource\n        description: Amazon EventBridge Pipes TagResource\n        call: amazon-eventbridge-pipes.tagresource\n        with:\n          resourceArn: rest.resourceArn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipes/{Name}/start\n      name: startpipe\n      operations:\n      - method: POST\n        name: startpipe\n        description: Amazon EventBridge Pipes StartPipe\n        call: amazon-eventbridge-pipes.startpipe\n        with:\n          Name: rest.Name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipes/{Name}/stop\n      name: stoppipe\n      operations:\n      - method: POST\n        name: stoppipe\n        description: Amazon EventBridge Pipes StopPipe\n        call: amazon-eventbridge-pipes.stoppipe\n        with:\n          Name: rest.Name\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /tags/{resourceArn}#tagKeys\n      name: untagresource\n      operations:\n      - method: DELETE\n        name: untagresource\n        description: Amazon EventBridge Pipes UntagResource\n        call: amazon-eventbridge-pipes.untagresource\n        with:\n          resourceArn: rest.resourceArn\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-eventbridge-pipes-mcp\n    transport: http\n    description: MCP adapter for Amazon EventBridge Pipes for AI agent use.\n    tools:\n    - name: createpipe\n      description: Amazon EventBridge Pipes CreatePipe\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge-pipes.createpipe\n      with:\n        Name: tools.Name\n      inputParameters:\n      - name: Name\n        type: string\n        description: The name of the pipe.\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepipe\n      description: Amazon EventBridge Pipes DeletePipe\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-eventbridge-pipes.deletepipe\n      with:\n        Name: tools.Name\n      inputParameters:\n      - name: Name\n        type: string\n        description: The name of the pipe.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describepipe\n      description: Amazon EventBridge Pipes DescribePipe\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-eventbridge-pipes.describepipe\n      with:\n        Name: tools.Name\n      inputParameters:\n      - name: Name\n        type: string\n        description: The name of the pipe.\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: updatepipe\n      description: Amazon EventBridge Pipes UpdatePipe\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amazon-eventbridge-pipes.updatepipe\n      with:\n        Name: tools.Name\n      inputParameters:\n      - name: Name\n        type: string\n        description: The name of the pipe.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpipes\n      description: Amazon EventBridge Pipes ListPipes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-eventbridge-pipes.listpipes\n      with:\n        CurrentState: tools.CurrentState\n        DesiredState: tools.DesiredState\n        Limit: tools.Limit\n        NamePrefix: tools.NamePrefix\n        NextToken: tools.NextToken\n        SourcePrefix: tools.SourcePrefix\n        TargetPrefix: tools.TargetPrefix\n      inputParameters:\n     \
  \ - name: CurrentState\n        type: string\n        description: The state the pipe is in.\n      - name: DesiredState\n        type: string\n        description: The state the pipe should be in.\n      - name: Limit\n        type: integer\n        description: The maximum number of pipes to include in the response.\n      - name: NamePrefix\n        type: string\n        description: 'A value that will return a subset of the pipes associated with this account. For example, <code>\"NamePrefix\":\n          \"ABC\"</code> will return all endpoints with \"ABC\" '\n      - name: NextToken\n        type: string\n        description: If <code>nextToken</code> is returned, there are more results available. The value of <code>nextToken</code>\n          is a unique pagination token for each page. Make th\n      - name: SourcePrefix\n        type: string\n        description: The prefix matching the pipe source.\n      - name: TargetPrefix\n        type: string\n        description: The prefix\
  \ matching the pipe target.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtagsforresource\n      description: Amazon EventBridge Pipes ListTagsForResource\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-eventbridge-pipes.listtagsforresource\n      with:\n        resourceArn: tools.resourceArn\n      inputParameters:\n      - name: resourceArn\n        type: string\n        description: The ARN of the pipe for which you want to view tags.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tagresource\n      description: Amazon EventBridge Pipes TagResource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge-pipes.tagresource\n      with:\n        resourceArn: tools.resourceArn\n      inputParameters:\n      - name: resourceArn\n        type: string\n        description:\
  \ The ARN of the pipe.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startpipe\n      description: Amazon EventBridge Pipes StartPipe\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge-pipes.startpipe\n      with:\n        Name: tools.Name\n      inputParameters:\n      - name: Name\n        type: string\n        description: The name of the pipe.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stoppipe\n      description: Amazon EventBridge Pipes StopPipe\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-eventbridge-pipes.stoppipe\n      with:\n        Name: tools.Name\n      inputParameters:\n      - name: Name\n        type: string\n        description: The name of the pipe.\n        required: true\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: untagresource\n      description: Amazon EventBridge Pipes UntagResource\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-eventbridge-pipes.untagresource\n      with:\n        resourceArn: tools.resourceArn\n        tagKeys: tools.tagKeys\n      inputParameters:\n      - name: resourceArn\n        type: string\n        description: The ARN of the pipe.\n        required: true\n      - name: tagKeys\n        type: array\n        description: The list of tag keys to remove from the pipe.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AMAZON_EVENTBRIDGE_PIPES_TOKEN: AMAZON_EVENTBRIDGE_PIPES_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-eventbridge-pipes/refs/heads/main/capabilities/amazon-eventbridge-pipes-capability.yaml
tags:
- Amazon
- Eventbridge
- Pipes
- API
tools:
- description: Amazon EventBridge Pipes CreatePipe
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpipe
- description: Amazon EventBridge Pipes DeletePipe
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepipe
- description: Amazon EventBridge Pipes DescribePipe
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describepipe
- description: Amazon EventBridge Pipes UpdatePipe
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepipe
- description: Amazon EventBridge Pipes ListPipes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipes
- description: Amazon EventBridge Pipes ListTagsForResource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtagsforresource
- description: Amazon EventBridge Pipes TagResource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: tagresource
- description: Amazon EventBridge Pipes StartPipe
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startpipe
- description: Amazon EventBridge Pipes StopPipe
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stoppipe
- description: Amazon EventBridge Pipes UntagResource
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: untagresource
---

---
categories: []
consumed_apis: []
description: Workflow capability for Amazon Resource Explorer. Enables automation of Amazon Resource Explorer resources for cloud operations teams.
layout: capability
name: Amazon Resource Explorer Operations
operations:
- description: List Amazon Resource Explorer resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Resource Explorer
provider_slug: amazon-resource-explorer
search_terms:
- list resources
- amazon resource explorer
- aws
- automation workflow for amazon resource explorer
- engineer managing amazon resource explorer resources
- aws cloud resource management
- cloud operations
- discovery
- operations
- amazon resource explorer resources
- resource management
- list amazon resource explorer resources
- inventory
slug: amazon-resource-explorer
source_filename: amazon-resource-explorer.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Resource Explorer Operations\n  description: Workflow capability for Amazon Resource Explorer. Enables automation of Amazon Resource Explorer resources\n    for cloud operations teams.\n  tags:\n  - Amazon Resource Explorer\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-resource-explorer\n    baseUri: https://resource-explorer-2.{region}.amazonaws.com\n    description: Amazon Resource Explorer API\n    authentication:\n      type: bearer\n      token: '{{AWS_ACCESS_KEY}}'\n    resources:\n    - name: Search\n      path: /Search\n      description: Search operations\n      operations:\n      - name: Search\n        method: POST\n        description: Search Resources\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n    - name: GetIndex\n      path: /GetIndex\n      description: GetIndex operations\n      operations:\n      - name: GetIndex\n        method: POST\n        description: Get Index\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: CreateIndex\n      path: /CreateIndex\n      description: CreateIndex operations\n      operations:\n      - name: CreateIndex\n        method: POST\n        description: Create Index\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: DeleteIndex\n      path: /DeleteIndex\n      description: DeleteIndex operations\n      operations:\n      - name: DeleteIndex\n        method: POST\n        description: Delete Index\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: ListIndexes\n      path: /ListIndexes\n      description: ListIndexes operations\n      operations:\n      - name: ListIndexes\n        method: POST\n        description: List Indexes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: CreateView\n      path: /CreateView\n      description: CreateView operations\n      operations:\n      - name: CreateView\n        method: POST\n        description: Create View\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: DeleteView\n      path: /DeleteView\n      description: DeleteView operations\n      operations:\n      - name: DeleteView\n        method: POST\n        description: Delete View\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: GetView\n\
  \      path: /GetView\n      description: GetView operations\n      operations:\n      - name: GetView\n        method: POST\n        description: Get View\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ListViews\n      path: /ListViews\n      description: ListViews operations\n      operations:\n      - name: ListViews\n        method: POST\n        description: List Views\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: BatchGetView\n      path: /BatchGetView\n      description: BatchGetView operations\n      operations:\n      - name: BatchGetView\n        method: POST\n        description: Batch Get View\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ListSupportedResourceTypes\n      path: /ListSupportedResourceTypes\n\
  \      description: ListSupportedResourceTypes operations\n      operations:\n      - name: ListSupportedResourceTypes\n        method: POST\n        description: List Supported Resource Types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ListTagsForResource\n      path: /ListTagsForResource/{resourceArn}\n      description: ListTagsForResource operations\n      operations:\n      - name: ListTagsForResource\n        method: GET\n        description: List Tags for Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: TagResource\n      path: /TagResource/{resourceArn}\n      description: TagResource operations\n      operations:\n      - name: TagResource\n        method: POST\n        description: Tag Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: UntagResource\n      path: /UntagResource/{resourceArn}\n      description: UntagResource operations\n      operations:\n      - name: UntagResource\n        method: DELETE\n        description: Untag Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-resource-explorer-api\n    description: Unified REST API for Amazon Resource Explorer operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Resource Explorer resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Resource Explorer resources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-resource-explorer-mcp\n    transport: http\n    description: MCP\
  \ server for AI-assisted Amazon Resource Explorer operations.\n    tools:\n    - name: list-amazon-resource-explorer-resources\n      description: List Amazon Resource Explorer resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-resource-explorer/refs/heads/main/capabilities/amazon-resource-explorer.yaml
tags:
- Amazon Resource Explorer
- Cloud Operations
tools:
- description: List Amazon Resource Explorer resources
  hints:
    readOnly: true
  name: list-amazon-resource-explorer-resources
---

---
categories: []
consumed_apis: []
description: Workflow capability for Amazon Q. Enables automation of Amazon Q resources for cloud operations teams.
layout: capability
name: Amazon Q Operations
operations:
- description: List Amazon Q resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Q
provider_slug: amazon-q
search_terms:
- list resources
- generative ai
- aws
- aws cloud resource management
- assistant
- cloud operations
- automation workflow for amazon q
- amazon q resources
- enterprise
- engineer managing amazon q resources
- amazon q
- list amazon q resources
- artificial intelligence
slug: amazon-q
source_filename: amazon-q.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Q Operations\n  description: Workflow capability for Amazon Q. Enables automation of Amazon Q resources for cloud operations teams.\n  tags:\n  - Amazon Q\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-q\n    baseUri: https://qbusiness.{region}.amazonaws.com\n    description: Amazon Q Business API\n    authentication:\n      type: bearer\n      token: '{{AWS_ACCESS_KEY}}'\n    resources:\n    - name: applications\n      path: /applications\n      description: applications operations\n      operations:\n      - name: ListApplications\n        method: GET\n        description: List Applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: CreateApplication\n        method: POST\n        description: Create Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: GetApplication\n        method: GET\n        description: Get Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DeleteApplication\n        method: DELETE\n        description: Delete Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ListConversations\n        method: GET\n        description: List Conversations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ChatSync\n        method: POST\n        description: Chat Sync\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: ListDataSources\n        method: GET\n        description: List Data Sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateDataSource\n        method: POST\n        description: Create Data Source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ListIndices\n        method: GET\n        description: List Indices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateIndex\n        method: POST\n        description: Create Index\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-q-api\n\
  \    description: Unified REST API for Amazon Q operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Q resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Q resources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-q-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Q operations.\n    tools:\n    - name: list-amazon-q-resources\n      description: List Amazon Q resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-q/refs/heads/main/capabilities/amazon-q.yaml
tags:
- Amazon Q
- Cloud Operations
tools:
- description: List Amazon Q resources
  hints:
    readOnly: true
  name: list-amazon-q-resources
---

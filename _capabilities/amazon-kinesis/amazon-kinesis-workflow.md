---
categories: []
consumed_apis: []
description: Unified workflow capability for Amazon Kinesis combining resource management and operations.
layout: capability
name: Amazon Kinesis Workflow
operations: []
personas: []
provider_name: Amazon Kinesis
provider_slug: amazon-kinesis
search_terms:
- Administrator
- aws
- real-time
- workflow
- analytics
- big data
- Developer
- provides a summarized description of the specified kinesis data stream.
- streams describe stream summary
- integrates api into applications
- lists your kinesis data streams.
- creates a kinesis data stream.
- manages resources and configurations
- streams list streams
- amazon kinesis
- streaming
- streams create stream
- unified workflow for amazon kinesis resource management
- data processing
slug: amazon-kinesis-workflow
source_filename: amazon-kinesis-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Kinesis Workflow\n  description: Unified workflow capability for Amazon Kinesis combining resource management and operations.\n  tags:\n  - Amazon Kinesis\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: kinesis\n    baseUri: https://kinesis.us-east-1.amazonaws.com\n    description: Amazon Kinesis service.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: streams\n      path: /streams\n      description: Kinesis data stream management\n      operations:\n      - name: createstream\n        method: POST\n        description: Creates a Kinesis data stream.\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n      - name: liststreams\n        method: GET\n        description: Lists your Kinesis data streams.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describestreamsummary\n        method: GET\n        description: Provides a summarized description of the specified Kinesis data stream.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kinesis-api\n    description: REST API for Amazon Kinesis workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: kinesis-mcp\n    transport: http\n    description: MCP server for Amazon Kinesis.\n    tools:\n    - name: streams-create-stream\n      description: Creates a Kinesis data stream.\n      hints:\n        readOnly: false\n        idempotent:\
  \ false\n      call: kinesis.createstream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streams-list-streams\n      description: Lists your Kinesis data streams.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis.liststreams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streams-describe-stream-summary\n      description: Provides a summarized description of the specified Kinesis data stream.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis.describestreamsummary\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-kinesis/refs/heads/main/capabilities/amazon-kinesis-workflow.yaml
tags:
- Amazon Kinesis
- Workflow
tools:
- description: Creates a Kinesis data stream.
  hints:
    idempotent: false
    readOnly: false
  name: streams-create-stream
- description: Lists your Kinesis data streams.
  hints:
    idempotent: true
    readOnly: true
  name: streams-list-streams
- description: Provides a summarized description of the specified Kinesis data stream.
  hints:
    idempotent: true
    readOnly: true
  name: streams-describe-stream-summary
---

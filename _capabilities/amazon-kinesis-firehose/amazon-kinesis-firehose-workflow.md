---
categories: []
consumed_apis:
- kinesis-firehose
description: Unified workflow capability for Amazon Kinesis Data Firehose combining resource management and operations.
layout: capability
name: Amazon Kinesis Data Firehose Workflow
operations: []
personas: []
provider_name: Amazon Kinesis Data Firehose
provider_slug: amazon-kinesis-firehose
search_terms:
- amazon kinesis data firehose
- delivery streams list delivery streams
- Developer
- lists your delivery streams in alphabetical order of their names.
- aws
- delivery streams describe delivery stream
- manages resources and configurations
- describes the specified delivery stream.
- streaming
- delivery streams create delivery stream
- workflow
- analytics
- data delivery
- Administrator
- integrates api into applications
- creates a kinesis data firehose delivery stream.
- unified workflow for amazon kinesis data firehose resource management
slug: amazon-kinesis-firehose-workflow
source_filename: amazon-kinesis-firehose-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Kinesis Data Firehose Workflow\n  description: Unified workflow capability for Amazon Kinesis Data Firehose combining resource management and operations.\n  tags:\n  - Amazon Kinesis Data Firehose\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - import: kinesis-firehose\n    location: ./shared/kinesis-firehose.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kinesis-firehose-api\n    description: REST API for Amazon Kinesis Data Firehose workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: kinesis-firehose-mcp\n    transport: http\n    description: MCP server for Amazon Kinesis Data Firehose.\n    tools:\n    - name: delivery-streams-create-delivery-stream\n      description: Creates a Kinesis Data Firehose delivery\
  \ stream.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: kinesis-firehose.createdeliverystream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delivery-streams-list-delivery-streams\n      description: Lists your delivery streams in alphabetical order of their names.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis-firehose.listdeliverystreams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delivery-streams-describe-delivery-stream\n      description: Describes the specified delivery stream.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: kinesis-firehose.describedeliverystream\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-kinesis-firehose/refs/heads/main/capabilities/amazon-kinesis-firehose-workflow.yaml
tags:
- Amazon Kinesis Data Firehose
- AWS
- Workflow
tools:
- description: Creates a Kinesis Data Firehose delivery stream.
  hints:
    idempotent: false
    readOnly: false
  name: delivery-streams-create-delivery-stream
- description: Lists your delivery streams in alphabetical order of their names.
  hints:
    idempotent: true
    readOnly: true
  name: delivery-streams-list-delivery-streams
- description: Describes the specified delivery stream.
  hints:
    idempotent: true
    readOnly: true
  name: delivery-streams-describe-delivery-stream
---

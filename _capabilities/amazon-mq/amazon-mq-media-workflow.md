---
categories: []
consumed_apis:
- mq
description: Workflow capability for Amazon MQ media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon MQ Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon MQ
provider_slug: amazon-mq
search_terms:
- aws media processing and delivery
- aws
- broadcasting
- media
- media processing
- listtags
- Broadcast Engineer
- developer building media processing applications
- listbrokers
- describe user
- create broker
- amazon mq media processing workflow
- createtags
- create tags
- Media Developer
- create user
- engineer managing broadcast media workflows
- createconfiguration
- list tags
- createuser
- createbroker
- workflow
- manage media processing jobs
- create configuration
- list jobs
- describeuser
- list configurations
- list brokers
- listconfigurations
slug: amazon-mq-media-workflow
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon MQ Workflow\n  description: Workflow capability for Amazon MQ media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: mq\n    location: ./shared/mq.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mq-workflow-api\n    description: Unified REST API for Amazon MQ workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: mq.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n\
  \    port: 9090\n    namespace: mq-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MQ workflow management.\n    tools:\n    - name: list-brokers\n      description: ListBrokers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mq.list-brokers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-broker\n      description: CreateBroker\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mq.create-broker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-configurations\n      description: ListConfigurations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mq.list-configurations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-configuration\n      description: CreateConfiguration\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mq.create-configuration\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tags\n      description: ListTags\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mq.list-tags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-tags\n      description: CreateTags\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mq.create-tags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-user\n      description: DescribeUser\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mq.describe-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: CreateUser\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mq.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mq/refs/heads/main/capabilities/amazon-mq-media-workflow.yaml
tags:
- AWS
- Media
- Broadcasting
- Workflow
tools:
- description: ListBrokers
  hints:
    openWorld: true
    readOnly: true
  name: list-brokers
- description: CreateBroker
  hints:
    openWorld: true
    readOnly: false
  name: create-broker
- description: ListConfigurations
  hints:
    openWorld: true
    readOnly: true
  name: list-configurations
- description: CreateConfiguration
  hints:
    openWorld: true
    readOnly: false
  name: create-configuration
- description: ListTags
  hints:
    openWorld: true
    readOnly: true
  name: list-tags
- description: CreateTags
  hints:
    openWorld: true
    readOnly: false
  name: create-tags
- description: DescribeUser
  hints:
    openWorld: true
    readOnly: true
  name: describe-user
- description: CreateUser
  hints:
    openWorld: true
    readOnly: false
  name: create-user
---

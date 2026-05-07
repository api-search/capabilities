---
categories: []
consumed_apis: []
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
- create configuration
- listbrokers
- createconfiguration
- list tags
- listconfigurations
- amazon mq media processing workflow
- describeuser
- createbroker
- developer building media processing applications
- describe user
- listtags
- engineer managing broadcast media workflows
- Media Developer
- workflow
- create broker
- list configurations
- aws media processing and delivery
- list jobs
- manage media processing jobs
- media
- createuser
- list brokers
- create user
- media processing
- aws
- create tags
- broadcasting
- Broadcast Engineer
- createtags
slug: amazon-mq-media-workflow
source_filename: amazon-mq-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon MQ Workflow\n  description: Workflow capability for Amazon MQ media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: mq\n    baseUri: http://mq.{region}.amazonaws.com\n    description: Amazon MQ REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: default\n      path: /\n      description: Amazon MQ resources\n      operations:\n      - name: list-brokers\n        method: GET\n        description: ListBrokers\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of brokers that Amazon MQ can return per page (20 by default). This value must be\n            an integer from 5 to 100.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: The token that specifies the next page of results Amazon MQ should return. To request the first page,\n            leave nextToken empty.\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n      - name: create-broker\n        method: POST\n        description: CreateBroker\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: list-configurations\n        method: GET\n        description: ListConfigurations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of brokers that Amazon MQ can return per page (20 by default). This value must be\n            an integer from 5 to 100.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: The token that specifies the next page of results Amazon MQ should return. To request the first page,\n            leave nextToken empty.\n      - name: create-configuration\n        method: POST\n        description:\
  \ CreateConfiguration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: list-tags\n        method: GET\n        description: ListTags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: resource-arn\n          in: path\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the resource tag.\n      - name: create-tags\n        method: POST\n        description: CreateTags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: resource-arn\n          in: path\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN)\
  \ of the resource tag.\n        body:\n          type: json\n          data: {}\n      - name: describe-user\n        method: GET\n        description: DescribeUser\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: broker-id\n          in: path\n          type: string\n          required: true\n          description: The unique ID that Amazon MQ generates for the broker.\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: The username of the ActiveMQ user. This value can contain only alphanumeric characters, dashes, periods,\n            underscores, and tildes (- . _ ~). This value must be 2-100 characters long.\n      - name: create-user\n        method: POST\n        description: CreateUser\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n        inputParameters:\n        - name: broker-id\n          in: path\n          type: string\n          required: true\n          description: The unique ID that Amazon MQ generates for the broker.\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: The username of the ActiveMQ user. This value can contain only alphanumeric characters, dashes, periods,\n            underscores, and tildes (- . _ ~). This value must be 2-100 characters long.\n        body:\n          type: json\n          data: {}\n      - name: update-user\n        method: PUT\n        description: UpdateUser\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: broker-id\n          in: path\n          type: string\n          required: true\n          description: The unique ID that Amazon MQ generates for the broker.\n\
  \        - name: username\n          in: path\n          type: string\n          required: true\n          description: The username of the ActiveMQ user. This value can contain only alphanumeric characters, dashes, periods,\n            underscores, and tildes (- . _ ~). This value must be 2-100 characters long.\n        body:\n          type: json\n          data: {}\n      - name: delete-user\n        method: DELETE\n        description: DeleteUser\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: broker-id\n          in: path\n          type: string\n          required: true\n          description: The unique ID that Amazon MQ generates for the broker.\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: The username of the ActiveMQ user. This value can contain only alphanumeric characters, dashes,\
  \ periods,\n            underscores, and tildes (- . _ ~). This value must be 2-100 characters long.\n      - name: describe-broker\n        method: GET\n        description: DescribeBroker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: broker-id\n          in: path\n          type: string\n          required: true\n          description: The unique ID that Amazon MQ generates for the broker.\n      - name: update-broker\n        method: PUT\n        description: UpdateBroker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: broker-id\n          in: path\n          type: string\n          required: true\n          description: The unique ID that Amazon MQ generates for the broker.\n        body:\n          type: json\n          data: {}\n      - name:\
  \ delete-broker\n        method: DELETE\n        description: DeleteBroker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: broker-id\n          in: path\n          type: string\n          required: true\n          description: The unique ID that Amazon MQ generates for the broker.\n      - name: delete-tags\n        method: DELETE\n        description: DeleteTags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: resource-arn\n          in: path\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the resource tag.\n        - name: tagKeys\n          in: query\n          type: array\n          required: true\n          description: An array of tag keys to delete\n      - name: describe-broker-engine-types\n\
  \        method: GET\n        description: DescribeBrokerEngineTypes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: engineType\n          in: query\n          type: string\n          required: false\n          description: Filter response by engine type.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of brokers that Amazon MQ can return per page (20 by default). This value must be\n            an integer from 5 to 100.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: The token that specifies the next page of results Amazon MQ should return. To request the first page,\n            leave nextToken empty.\n      - name: describe-broker-instance-options\n        method: GET\n        description: DescribeBrokerInstanceOptions\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: engineType\n          in: query\n          type: string\n          required: false\n          description: Filter response by engine type.\n        - name: hostInstanceType\n          in: query\n          type: string\n          required: false\n          description: Filter response by host instance type.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of brokers that Amazon MQ can return per page (20 by default). This value must be\n            an integer from 5 to 100.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: The token that specifies the next page of results Amazon MQ should return. To request the first page,\n            leave nextToken empty.\n\
  \        - name: storageType\n          in: query\n          type: string\n          required: false\n          description: Filter response by storage type.\n      - name: describe-configuration\n        method: GET\n        description: DescribeConfiguration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: configuration-id\n          in: path\n          type: string\n          required: true\n          description: The unique ID that Amazon MQ generates for the configuration.\n      - name: update-configuration\n        method: PUT\n        description: UpdateConfiguration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: configuration-id\n          in: path\n          type: string\n          required: true\n          description: The unique ID that\
  \ Amazon MQ generates for the configuration.\n        body:\n          type: json\n          data: {}\n      - name: describe-configuration-revision\n        method: GET\n        description: DescribeConfigurationRevision\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: configuration-id\n          in: path\n          type: string\n          required: true\n          description: The unique ID that Amazon MQ generates for the configuration.\n        - name: configuration-revision\n          in: path\n          type: string\n          required: true\n          description: The revision of the configuration.\n      - name: list-configuration-revisions\n        method: GET\n        description: ListConfigurationRevisions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n\
  \        - name: configuration-id\n          in: path\n          type: string\n          required: true\n          description: The unique ID that Amazon MQ generates for the configuration.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of brokers that Amazon MQ can return per page (20 by default). This value must be\n            an integer from 5 to 100.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: The token that specifies the next page of results Amazon MQ should return. To request the first page,\n            leave nextToken empty.\n      - name: list-users\n        method: GET\n        description: ListUsers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: broker-id\n          in: path\n   \
  \       type: string\n          required: true\n          description: The unique ID that Amazon MQ generates for the broker.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of brokers that Amazon MQ can return per page (20 by default). This value must be\n            an integer from 5 to 100.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: The token that specifies the next page of results Amazon MQ should return. To request the first page,\n            leave nextToken empty.\n      - name: reboot-broker\n        method: POST\n        description: RebootBroker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: broker-id\n          in: path\n          type: string\n          required: true\n          description:\
  \ The unique ID that Amazon MQ generates for the broker.\n        body:\n          type: json\n          data: {}\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mq-workflow-api\n    description: Unified REST API for Amazon MQ workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: mq.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mq-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon MQ workflow management.\n    tools:\n    - name: list-brokers\n      description: ListBrokers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mq.list-brokers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-broker\n      description:\
  \ CreateBroker\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mq.create-broker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-configurations\n      description: ListConfigurations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mq.list-configurations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-configuration\n      description: CreateConfiguration\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mq.create-configuration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tags\n      description: ListTags\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mq.list-tags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-tags\n      description: CreateTags\n      hints:\n        readOnly: false\n        openWorld: true\n      call:\
  \ mq.create-tags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-user\n      description: DescribeUser\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mq.describe-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: CreateUser\n      hints:\n        readOnly: false\n        openWorld: true\n      call: mq.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mq/refs/heads/main/capabilities/amazon-mq-media-workflow.yaml
tags:
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

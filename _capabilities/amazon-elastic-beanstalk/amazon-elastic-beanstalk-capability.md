---
categories: []
consumed_apis: []
description: AWS Elastic Beanstalk is a platform-as-a-service that makes it easy to deploy, manage, and scale web applications and services.
layout: capability
name: Amazon Elastic Beanstalk AWS Elastic Beanstalk API
operations:
- description: Amazon Elastic Beanstalk Create Application
  method: POST
  name: createapplication
  path: /
- description: Amazon Elastic Beanstalk Describe Applications
  method: GET
  name: describeapplications
  path: /
- description: Amazon Elastic Beanstalk Create Environment
  method: POST
  name: createenvironment
  path: /#CreateEnvironment
- description: Amazon Elastic Beanstalk Describe Environments
  method: GET
  name: describeenvironments
  path: /#DescribeEnvironments
- description: Amazon Elastic Beanstalk Update Environment
  method: POST
  name: updateenvironment
  path: /#UpdateEnvironment
personas: []
provider_name: Amazon Elastic Beanstalk
provider_slug: amazon-elastic-beanstalk
search_terms:
- amazon elastic beanstalk update environment
- operations teams managing amazon elastic beanstalk infrastructure
- amazon web services
- api
- amazon elastic beanstalk describe applications
- paas
- amazon elastic beanstalk create application
- amazon
- createapplication
- createenvironment
- deployment
- beanstalk
- auto scaling
- elastic
- developers building applications using amazon elastic beanstalk
- amazon elastic beanstalk describe environments
- unified capability for managing amazon elastic beanstalk resources. combines amazon elastic beanstalk apis for application developer workflows in application deployment.
- elastic beanstalk
- describeapplications
- describeenvironments
- updateenvironment
- platform-as-a-service for deploying and managing web applications
- web applications
- amazon elastic beanstalk create environment
- platform as a service
slug: amazon-elastic-beanstalk-capability
source_filename: amazon-elastic-beanstalk-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Elastic Beanstalk AWS Elastic Beanstalk API\n  description: AWS Elastic Beanstalk is a platform-as-a-service that makes it easy to deploy, manage, and scale web applications\n    and services.\n  tags:\n  - Amazon\n  - Elastic\n  - Beanstalk\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-elastic-beanstalk\n    baseUri: https://elasticbeanstalk.amazonaws.com\n    description: Amazon Elastic Beanstalk AWS Elastic Beanstalk API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AMAZON_ELASTIC_BEANSTALK_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: createapplication\n        method: POST\n        description: Amazon Elastic Beanstalk Create Application\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n\
  \          required: true\n        - name: Version\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describeapplications\n        method: GET\n        description: Amazon Elastic Beanstalk Describe Applications\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n        - name: Version\n          in: query\n          type: string\n          required: true\n        - name: ApplicationNames.member.1\n          in: query\n          type: string\n          description: The name of an application to describe.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: createenvironment\n      path: /#CreateEnvironment\n      operations:\n      - name: createenvironment\n        method:\
  \ POST\n        description: Amazon Elastic Beanstalk Create Environment\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n        - name: Version\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: describeenvironments\n      path: /#DescribeEnvironments\n      operations:\n      - name: describeenvironments\n        method: GET\n        description: Amazon Elastic Beanstalk Describe Environments\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n        - name: Version\n          in: query\n          type: string\n          required: true\n        - name: ApplicationName\n          in: query\n          type: string\n          description: The name of the application associated with the environments.\n\
  \        - name: EnvironmentIds.member.1\n          in: query\n          type: string\n          description: An environment ID to describe.\n        - name: EnvironmentNames.member.1\n          in: query\n          type: string\n          description: An environment name to describe.\n        - name: IncludeDeleted\n          in: query\n          type: boolean\n          description: Indicates whether to include deleted environments.\n        - name: MaxRecords\n          in: query\n          type: integer\n          description: The maximum number of environments to return.\n        - name: NextToken\n          in: query\n          type: string\n          description: The pagination token for the next set of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: updateenvironment\n      path: /#UpdateEnvironment\n      operations:\n      - name: updateenvironment\n        method: POST\n    \
  \    description: Amazon Elastic Beanstalk Update Environment\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n        - name: Version\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-elastic-beanstalk-rest\n    description: REST adapter for Amazon Elastic Beanstalk AWS Elastic Beanstalk API.\n    resources:\n    - path: /\n      name: createapplication\n      operations:\n      - method: POST\n        name: createapplication\n        description: Amazon Elastic Beanstalk Create Application\n        call: amazon-elastic-beanstalk.createapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /\n      name: describeapplications\n      operations:\n      - method:\
  \ GET\n        name: describeapplications\n        description: Amazon Elastic Beanstalk Describe Applications\n        call: amazon-elastic-beanstalk.describeapplications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#CreateEnvironment\n      name: createenvironment\n      operations:\n      - method: POST\n        name: createenvironment\n        description: Amazon Elastic Beanstalk Create Environment\n        call: amazon-elastic-beanstalk.createenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#DescribeEnvironments\n      name: describeenvironments\n      operations:\n      - method: GET\n        name: describeenvironments\n        description: Amazon Elastic Beanstalk Describe Environments\n        call: amazon-elastic-beanstalk.describeenvironments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#UpdateEnvironment\n      name: updateenvironment\n  \
  \    operations:\n      - method: POST\n        name: updateenvironment\n        description: Amazon Elastic Beanstalk Update Environment\n        call: amazon-elastic-beanstalk.updateenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-elastic-beanstalk-mcp\n    transport: http\n    description: MCP adapter for Amazon Elastic Beanstalk AWS Elastic Beanstalk API for AI agent use.\n    tools:\n    - name: createapplication\n      description: Amazon Elastic Beanstalk Create Application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-elastic-beanstalk.createapplication\n      with:\n        Action: tools.Action\n        Version: tools.Version\n      inputParameters:\n      - name: Action\n        type: string\n        description: Action\n        required: true\n      - name: Version\n        type: string\n        description: Version\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeapplications\n      description: Amazon Elastic Beanstalk Describe Applications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-beanstalk.describeapplications\n      with:\n        Action: tools.Action\n        Version: tools.Version\n        ApplicationNames.member.1: tools.ApplicationNames.member.1\n      inputParameters:\n      - name: Action\n        type: string\n        description: Action\n        required: true\n      - name: Version\n        type: string\n        description: Version\n        required: true\n      - name: ApplicationNames.member.1\n        type: string\n        description: The name of an application to describe.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createenvironment\n      description: Amazon Elastic Beanstalk Create Environment\n   \
  \   hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-elastic-beanstalk.createenvironment\n      with:\n        Action: tools.Action\n        Version: tools.Version\n      inputParameters:\n      - name: Action\n        type: string\n        description: Action\n        required: true\n      - name: Version\n        type: string\n        description: Version\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeenvironments\n      description: Amazon Elastic Beanstalk Describe Environments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-beanstalk.describeenvironments\n      with:\n        Action: tools.Action\n        Version: tools.Version\n        ApplicationName: tools.ApplicationName\n        EnvironmentIds.member.1: tools.EnvironmentIds.member.1\n        EnvironmentNames.member.1: tools.EnvironmentNames.member.1\n\
  \        IncludeDeleted: tools.IncludeDeleted\n        MaxRecords: tools.MaxRecords\n        NextToken: tools.NextToken\n      inputParameters:\n      - name: Action\n        type: string\n        description: Action\n        required: true\n      - name: Version\n        type: string\n        description: Version\n        required: true\n      - name: ApplicationName\n        type: string\n        description: The name of the application associated with the environments.\n      - name: EnvironmentIds.member.1\n        type: string\n        description: An environment ID to describe.\n      - name: EnvironmentNames.member.1\n        type: string\n        description: An environment name to describe.\n      - name: IncludeDeleted\n        type: boolean\n        description: Indicates whether to include deleted environments.\n      - name: MaxRecords\n        type: integer\n        description: The maximum number of environments to return.\n      - name: NextToken\n        type: string\n\
  \        description: The pagination token for the next set of results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateenvironment\n      description: Amazon Elastic Beanstalk Update Environment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-elastic-beanstalk.updateenvironment\n      with:\n        Action: tools.Action\n        Version: tools.Version\n      inputParameters:\n      - name: Action\n        type: string\n        description: Action\n        required: true\n      - name: Version\n        type: string\n        description: Version\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AMAZON_ELASTIC_BEANSTALK_TOKEN: AMAZON_ELASTIC_BEANSTALK_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-elastic-beanstalk/refs/heads/main/capabilities/amazon-elastic-beanstalk-capability.yaml
tags:
- Amazon
- Elastic
- Beanstalk
- API
tools:
- description: Amazon Elastic Beanstalk Create Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplication
- description: Amazon Elastic Beanstalk Describe Applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describeapplications
- description: Amazon Elastic Beanstalk Create Environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createenvironment
- description: Amazon Elastic Beanstalk Describe Environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describeenvironments
- description: Amazon Elastic Beanstalk Update Environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateenvironment
---

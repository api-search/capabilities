---
categories:
- serverless
consumed_apis:
- lambda
description: Unified workflow capability for Amazon Lambda combining resource management and operations.
layout: capability
name: Amazon Lambda Workflow
operations: []
personas: []
provider_name: Amazon Lambda
provider_slug: amazon-lambda
search_terms:
- compute
- returns details about an event source mapping.
- workflow
- manages resources and configurations
- event source mappings list event source mappings
- functions create function
- amazon lambda
- aws
- returns information about the function or function version.
- faas
- functions list functions
- lists event source mappings.
- returns a list of lambda functions, with the version-specific configuration of each.
- functions get function
- integrates api into applications
- event source mappings get event source mapping
- creates a lambda function.
- creates a mapping between an event source and an aws lambda function.
- Developer
- unified workflow for amazon lambda resource management
- event-driven
- serverless
- functions
- Administrator
- event source mappings create event source mapping
slug: amazon-lambda-workflow
source_filename: amazon-lambda-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Lambda Workflow\n  description: Unified workflow capability for Amazon Lambda combining resource management and operations.\n  tags:\n  - Amazon Lambda\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - import: lambda\n    location: ./shared/lambda.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lambda-api\n    description: REST API for Amazon Lambda workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: lambda-mcp\n    transport: http\n    description: MCP server for Amazon Lambda.\n    tools:\n    - name: functions-create-function\n      description: Creates a Lambda function.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: lambda.createfunction\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: functions-list-functions\n      description: Returns a list of Lambda functions, with the version-specific configuration of each.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lambda.listfunctions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: functions-get-function\n      description: Returns information about the function or function version.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lambda.getfunction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: event-source-mappings-create-event-source-mapping\n      description: Creates a mapping between an event source and an AWS Lambda function.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: lambda.createeventsourcemapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: event-source-mappings-list-event-source-mappings\n\
  \      description: Lists event source mappings.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lambda.listeventsourcemappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: event-source-mappings-get-event-source-mapping\n      description: Returns details about an event source mapping.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lambda.geteventsourcemapping\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-lambda/refs/heads/main/capabilities/amazon-lambda-workflow.yaml
tags:
- Amazon Lambda
- Workflow
tools:
- description: Creates a Lambda function.
  hints:
    idempotent: false
    readOnly: false
  name: functions-create-function
- description: Returns a list of Lambda functions, with the version-specific configuration of each.
  hints:
    idempotent: true
    readOnly: true
  name: functions-list-functions
- description: Returns information about the function or function version.
  hints:
    idempotent: true
    readOnly: true
  name: functions-get-function
- description: Creates a mapping between an event source and an AWS Lambda function.
  hints:
    idempotent: false
    readOnly: false
  name: event-source-mappings-create-event-source-mapping
- description: Lists event source mappings.
  hints:
    idempotent: true
    readOnly: true
  name: event-source-mappings-list-event-source-mappings
- description: Returns details about an event source mapping.
  hints:
    idempotent: true
    readOnly: true
  name: event-source-mappings-get-event-source-mapping
---

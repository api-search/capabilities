---
categories:
- api-management
consumed_apis:
- amazon-api-gateway
description: Workflow capability for managing API Gateway REST APIs including lifecycle management, stage deployment, and configuration.
layout: capability
name: Amazon API Gateway Management
operations:
- description: List REST APIs.
  method: GET
  name: list-rest-apis
  path: /v1/rest-apis
personas: []
provider_name: Amazon API Gateway
provider_slug: amazon-api-gateway
search_terms:
- rest api
- list all rest apis configured in amazon api gateway.
- list rest apis
- Platform Engineer
- http api
- serverless
- API Developer
- amazon
- aws
- gateway
- developer creating and managing rest apis on amazon api gateway.
- engineer managing api infrastructure and deployments across environments.
- api gateway
- websocket
- create a new rest api in amazon api gateway.
- list rest apis.
- manage api gateway rest apis, resources, stages, and deployments.
- create rest api
- api management
slug: api-gateway-management
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon API Gateway Management\n  description: Workflow capability for managing API Gateway REST APIs including lifecycle management, stage deployment, and configuration.\n  tags:\n  - Amazon\n  - API Gateway\n  - AWS\n  - API Management\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: amazon-api-gateway\n    location: ./shared/amazon-api-gateway.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: api-gateway-management-api\n    description: REST API for API Gateway management.\n    resources:\n    - path: /v1/rest-apis\n      name: rest-apis\n      operations:\n      - method: GET\n        name: list-rest-apis\n        description: List REST APIs.\n        call: amazon-api-gateway.get-rest-apis\n        with: {}\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: api-gateway-management-mcp\n    transport: http\n    description: MCP server for AI-assisted API Gateway management.\n    tools:\n    - name: list-rest-apis\n      description: List all REST APIs configured in Amazon API Gateway.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: amazon-api-gateway.get-rest-apis\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-rest-api\n      description: Create a new REST API in Amazon API Gateway.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: amazon-api-gateway.create-rest-api\n      with:\n        body: tools.body\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-api-gateway/refs/heads/main/capabilities/api-gateway-management.yaml
tags:
- Amazon
- API Gateway
- AWS
- API Management
tools:
- description: List all REST APIs configured in Amazon API Gateway.
  hints:
    openWorld: false
    readOnly: true
  name: list-rest-apis
- description: Create a new REST API in Amazon API Gateway.
  hints:
    openWorld: false
    readOnly: false
  name: create-rest-api
---

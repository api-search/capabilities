---
categories: []
consumed_apis: []
description: A capability that crawls every AWS API Gateway in an account and exports each REST API as an OpenAPI 3.0 doc, so the spec inventory updates automatically with no manual upload.
layout: capability
name: Aws Api Gateway Openapi Crawl Capability
operations:
- description: ''
  method: GET
  name: list-gateway-specs
  path: /gateway-specs
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- spec-driven integration
- openapi
- api gateway
- aws
- list rest apis
- export rest api
- ai
- list gateway specs
- capabilities
- api integration
- mcp
- naftiko
slug: aws-api-gateway-openapi-crawl-capability
source_filename: aws-api-gateway-openapi-crawl-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Aws Api Gateway Openapi Crawl Capability\n  description: A capability that crawls every AWS API Gateway in an account and exports each REST API as an OpenAPI 3.0 doc, so the spec inventory updates automatically with no manual upload.\n  tags: [Naftiko, AWS, API Gateway, OpenAPI]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: aws-env\n  description: AWS credentials with API Gateway describe/export permissions.\n  keys: {AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY, AWS_REGION: AWS_REGION}\ncapability:\n  consumes:\n  - namespace: apigateway\n    type: http\n    baseUri: https://apigateway.{{AWS_REGION}}.amazonaws.com\n    authentication: {type: aws-sig-v4, accessKeyId: '{{AWS_ACCESS_KEY_ID}}', secretKey: '{{AWS_SECRET_ACCESS_KEY}}', region: '{{AWS_REGION}}', service: apigateway}\n    resources:\n    - {name: rest-apis, path: /restapis, operations: [{name: list-rest-apis, method:\
  \ GET}]}\n    - name: rest-api-export\n      path: /restapis/{{rest_api_id}}/stages/{{stage_name}}/exports/oas30\n      operations:\n      - {name: export-rest-api, method: GET, inputParameters: [{name: rest_api_id, in: path}, {name: stage_name, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: aws-api-gateway-openapi-crawl-capability-rest\n    description: REST surface that lists API Gateway REST APIs and exports each as OpenAPI.\n    resources:\n    - {name: gateway-specs, path: /gateway-specs, operations: [{method: GET, name: list-gateway-specs, call: apigateway.list-rest-apis}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: aws-api-gateway-openapi-crawl-capability-mcp\n    description: MCP exposing the API Gateway crawl as agent tools.\n    tools:\n    - {name: list-rest-apis, hints: {readOnly: true}, call: apigateway.list-rest-apis}\n    - name: export-rest-api\n      hints: {readOnly: true}\n      inputParameters:\
  \ [{name: rest_api_id, type: string, required: true}, {name: stage_name, type: string, required: true}]\n      call: apigateway.export-rest-api\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: aws-api-gateway-openapi-crawl-capability-skills\n    description: Skill bundle for the API Gateway crawl.\n    skills:\n    - name: aws-api-gateway-openapi-crawl-capability\n      description: Crawl API Gateway and export OpenAPI.\n      location: file:///opt/naftiko/skills/aws-api-gateway-openapi-crawl-capability\n      allowed-tools: list-rest-apis,export-rest-api\n      tools:\n      - {name: list-rest-apis, from: {sourceNamespace: aws-api-gateway-openapi-crawl-capability-mcp, action: list-rest-apis}}\n      - {name: export-rest-api, from: {sourceNamespace: aws-api-gateway-openapi-crawl-capability-mcp, action: export-rest-api}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/aws-api-gateway-openapi-crawl-capability.yaml
tags:
- Naftiko
- API Gateway
- OpenAPI
tools:
- description: ''
  hints:
    readOnly: true
  name: list-rest-apis
- description: ''
  hints:
    readOnly: true
  name: export-rest-api
---

---
categories: []
consumed_apis: []
description: Workflow capability composing Amazon OpenSearch Service APIs for developers and operators.
layout: capability
name: Amazon OpenSearch Service API Workflow
operations:
- description: List Amazon OpenSearch Service resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon OpenSearch Service
provider_slug: amazon-opensearch-service
search_terms:
- list resources
- list and manage openapi.yml resources
- primary amazon opensearch service resources
- aws
- amazon opensearch service
- core api workflow
- full-text search
- elasticsearch
- list amazon opensearch service resources
- search
- list openapi.yml
- developer using amazon opensearch service apis
- analytics
- opensearch
- Developer
- log analytics
slug: amazon-opensearch-service-workflow
source_filename: amazon-opensearch-service-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon OpenSearch Service API Workflow\n  description: Workflow capability composing Amazon OpenSearch Service APIs for developers and operators.\n  tags:\n  - Amazon OpenSearch Service\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - type: http\n    namespace: openapi.yml\n    baseUri: https://es.{region}.amazonaws.com\n    description: The Amazon OpenSearch Service API enables programmatic management of OpenSearch domains. You can cre\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_SIGV4_AUTH}}'\n      placement: header\n    resources:\n    - name: domains\n      path: /domains\n      description: Domains operations for Amazon OpenSearch Service API\n      operations:\n      - name: CreateDomain\n        method: POST\n        description: Amazon OpenSearch Service Create an OpenSearch\
  \ Domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: DescribeDomain\n        method: GET\n        description: Amazon OpenSearch Service Describe an OpenSearch Domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: domainName\n          in: path\n          type: string\n          required: true\n          description: domainName\n      - name: DeleteDomain\n        method: DELETE\n        description: Amazon OpenSearch Service Delete an OpenSearch Domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: domainName\n          in: path\n          type: string\n          required: true\n          description:\
  \ domainName\n      - name: DescribeDomains\n        method: POST\n        description: Amazon OpenSearch Service Describe Multiple OpenSearch Domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: ListDomainNames\n        method: GET\n        description: Amazon OpenSearch Service List All OpenSearch Domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-opensearch-service-api\n    description: Unified REST API for Amazon OpenSearch Service.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon OpenSearch Service resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon OpenSearch Service resources\n\
  \        call: openapi.yml.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-opensearch-service-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon OpenSearch Service operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-opensearch-service/refs/heads/main/capabilities/amazon-opensearch-service-workflow.yaml
tags:
- Amazon OpenSearch Service
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---

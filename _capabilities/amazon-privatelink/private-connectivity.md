---
api_specs:
- filename: amazon-privatelink-openapi.yaml
  format: yaml
  label: amazon-privatelink
  slug: amazon-privatelink
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-privatelink/refs/heads/main/openapi/amazon-privatelink-openapi.yaml
categories: []
consumed_apis:
- amazon-privatelink
description: Workflow capability for establishing and managing private connectivity between VPCs and AWS services using Amazon PrivateLink. Covers endpoint service creation, VPC endpoint management, and connection lifecycle for network engineers and platform teams.
layout: capability
name: Amazon PrivateLink Private Connectivity
operations:
- description: List VPC endpoint services
  method: GET
  name: list-endpoint-services
  path: /v1/endpoint-services
- description: Create a VPC endpoint service
  method: POST
  name: create-endpoint-service
  path: /v1/endpoint-services
- description: List VPC endpoints
  method: GET
  name: list-endpoints
  path: /v1/endpoints
- description: Create a VPC endpoint
  method: POST
  name: create-endpoint
  path: /v1/endpoints
- description: List endpoint connections
  method: GET
  name: list-connections
  path: /v1/connections
- description: Accept endpoint connections
  method: POST
  name: accept-connections
  path: /v1/connections
personas: []
provider_name: Amazon PrivateLink
provider_slug: amazon-privatelink
search_terms:
- accept connections
- Platform Engineer
- security
- list endpoint services
- accept pending vpc endpoint connection requests
- list connections
- consumes endpoint services and manages vpc endpoints for internal services
- create a vpc endpoint
- create a vpc endpoint service backed by a load balancer
- create endpoint service
- endpoint services
- zero trust
- create a private vpc endpoint for an aws service or endpoint service
- reject endpoint connections
- aws
- list vpc endpoints in the account
- accept endpoint connections
- reject vpc endpoint connection requests
- vpc
- amazon
- list vpc endpoint services
- networking
- Network Engineer
- private vpc connectivity workflow
- list endpoint connections
- list available vpc endpoint services for private connectivity
- manages vpc endpoint services and private connectivity architecture
- create vpc endpoint
- list endpoints
- list vpc endpoints
- list pending and active connections to endpoint services
- create endpoint
- vpc endpoint service provider management
- endpoint connection management
- vpc endpoint consumer management
- create a vpc endpoint service
- private connectivity
slug: private-connectivity
source_filename: private-connectivity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon PrivateLink Private Connectivity\n  description: Workflow capability for establishing and managing private connectivity between VPCs and AWS services using Amazon PrivateLink. Covers endpoint service creation, VPC endpoint management, and connection lifecycle for network engineers and platform teams.\n  tags:\n    - Amazon\n    - AWS\n    - Networking\n    - Private Connectivity\n    - VPC\n    - Security\n    - Zero Trust\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-privatelink\n      location: ./shared/amazon-privatelink.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: private-connectivity-api\n      description: Unified REST API for Amazon PrivateLink private connectivity workflows.\n\
  \      resources:\n        - path: /v1/endpoint-services\n          name: endpoint-services\n          description: VPC endpoint service provider management\n          operations:\n            - method: GET\n              name: list-endpoint-services\n              description: List VPC endpoint services\n              call: \"amazon-privatelink.describe-endpoint-services\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-endpoint-service\n              description: Create a VPC endpoint service\n              call: \"amazon-privatelink.create-endpoint-service\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/endpoints\n          name: endpoints\n          description: VPC endpoint consumer management\n          operations:\n            - method: GET\n              name: list-endpoints\n              description:\
  \ List VPC endpoints\n              call: \"amazon-privatelink.describe-endpoints\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-endpoint\n              description: Create a VPC endpoint\n              call: \"amazon-privatelink.create-endpoint\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/connections\n          name: connections\n          description: Endpoint connection management\n          operations:\n            - method: GET\n              name: list-connections\n              description: List endpoint connections\n              call: \"amazon-privatelink.describe-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: accept-connections\n              description: Accept endpoint connections\n\
  \              call: \"amazon-privatelink.accept-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: private-connectivity-mcp\n      transport: http\n      description: MCP server for AI-assisted private connectivity workflows with Amazon PrivateLink.\n      tools:\n        - name: list-endpoint-services\n          description: List available VPC endpoint services for private connectivity\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amazon-privatelink.describe-endpoint-services\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-endpoint-service\n          description: Create a VPC endpoint service backed by a load balancer\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-privatelink.create-endpoint-service\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-vpc-endpoints\n          description: List VPC endpoints in the account\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amazon-privatelink.describe-endpoints\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-vpc-endpoint\n          description: Create a private VPC endpoint for an AWS service or endpoint service\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-privatelink.create-endpoint\"\n          with:\n            vpc_id: \"tools.vpc_id\"\n            service_name: \"tools.service_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-endpoint-connections\n          description: List pending and active connections to endpoint services\n     \
  \     hints:\n            readOnly: true\n            openWorld: true\n          call: \"amazon-privatelink.describe-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: accept-endpoint-connections\n          description: Accept pending VPC endpoint connection requests\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-privatelink.accept-connections\"\n          with:\n            service_id: \"tools.service_id\"\n            endpoint_ids: \"tools.endpoint_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: reject-endpoint-connections\n          description: Reject VPC endpoint connection requests\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"amazon-privatelink.reject-connections\"\n          with:\n            service_id: \"tools.service_id\"\n          \
  \  endpoint_ids: \"tools.endpoint_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-privatelink/refs/heads/main/capabilities/private-connectivity.yaml
tags:
- Amazon
- Networking
- Private Connectivity
- VPC
- Security
- Zero Trust
tools:
- description: List available VPC endpoint services for private connectivity
  hints:
    openWorld: true
    readOnly: true
  name: list-endpoint-services
- description: Create a VPC endpoint service backed by a load balancer
  hints:
    destructive: false
    readOnly: false
  name: create-endpoint-service
- description: List VPC endpoints in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-vpc-endpoints
- description: Create a private VPC endpoint for an AWS service or endpoint service
  hints:
    destructive: false
    readOnly: false
  name: create-vpc-endpoint
- description: List pending and active connections to endpoint services
  hints:
    openWorld: true
    readOnly: true
  name: list-endpoint-connections
- description: Accept pending VPC endpoint connection requests
  hints:
    destructive: false
    readOnly: false
  name: accept-endpoint-connections
- description: Reject VPC endpoint connection requests
  hints:
    destructive: true
    readOnly: false
  name: reject-endpoint-connections
---

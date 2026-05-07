---
categories: []
consumed_apis: []
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
- manages vpc endpoint services and private connectivity architecture
- networking
- list available vpc endpoint services for private connectivity
- create a vpc endpoint
- list connections
- create a vpc endpoint service backed by a load balancer
- list endpoint connections
- endpoint services
- vpc
- amazon
- list endpoint services
- reject vpc endpoint connection requests
- create endpoint service
- list pending and active connections to endpoint services
- private vpc connectivity workflow
- create a vpc endpoint service
- Platform Engineer
- vpc endpoint service provider management
- list vpc endpoint services
- private connectivity
- accept connections
- vpc endpoint consumer management
- create a private vpc endpoint for an aws service or endpoint service
- reject endpoint connections
- accept endpoint connections
- zero trust
- create vpc endpoint
- aws
- Network Engineer
- create endpoint
- accept pending vpc endpoint connection requests
- list vpc endpoints
- endpoint connection management
- list endpoints
- consumes endpoint services and manages vpc endpoints for internal services
- security
- list vpc endpoints in the account
slug: private-connectivity
source_filename: private-connectivity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon PrivateLink Private Connectivity\n  description: Workflow capability for establishing and managing private connectivity between VPCs and AWS services using\n    Amazon PrivateLink. Covers endpoint service creation, VPC endpoint management, and connection lifecycle for network engineers\n    and platform teams.\n  tags:\n  - Amazon\n  - AWS\n  - Networking\n  - Private Connectivity\n  - VPC\n  - Security\n  - Zero Trust\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-privatelink\n    baseUri: https://ec2.{region}.amazonaws.com\n    description: Amazon PrivateLink (EC2 API) private connectivity endpoints\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n  \
  \    placement: header\n    resources:\n    - name: endpoint-services\n      path: /?Action=DescribeVpcEndpointServices\n      description: VPC endpoint services\n      operations:\n      - name: describe-endpoint-services\n        method: GET\n        description: List available VPC endpoint services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-endpoint-service\n        method: POST\n        description: Create a VPC endpoint service configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            NetworkLoadBalancerArn: '{{tools.nlb_arn}}'\n            AcceptanceRequired: '{{tools.acceptance_required}}'\n    - name: endpoints\n      path: /?Action=DescribeVpcEndpoints\n      description: VPC endpoints\n      operations:\n      - name: describe-endpoints\n\
  \        method: GET\n        description: List VPC endpoints in the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-endpoint\n        method: POST\n        description: Create a VPC endpoint for a service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            VpcId: '{{tools.vpc_id}}'\n            ServiceName: '{{tools.service_name}}'\n            VpcEndpointType: '{{tools.endpoint_type}}'\n    - name: endpoint-connections\n      path: /?Action=DescribeVpcEndpointConnections\n      description: VPC endpoint connections\n      operations:\n      - name: describe-connections\n        method: GET\n        description: List connections to endpoint services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: accept-connections\n        method: POST\n        description: Accept VPC endpoint connections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ServiceId: '{{tools.service_id}}'\n            VpcEndpointId: '{{tools.endpoint_ids}}'\n      - name: reject-connections\n        method: POST\n        description: Reject VPC endpoint connections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ServiceId: '{{tools.service_id}}'\n            VpcEndpointId: '{{tools.endpoint_ids}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: private-connectivity-api\n    description: Unified REST API for Amazon PrivateLink private connectivity workflows.\n  \
  \  resources:\n    - path: /v1/endpoint-services\n      name: endpoint-services\n      description: VPC endpoint service provider management\n      operations:\n      - method: GET\n        name: list-endpoint-services\n        description: List VPC endpoint services\n        call: amazon-privatelink.describe-endpoint-services\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-endpoint-service\n        description: Create a VPC endpoint service\n        call: amazon-privatelink.create-endpoint-service\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/endpoints\n      name: endpoints\n      description: VPC endpoint consumer management\n      operations:\n      - method: GET\n        name: list-endpoints\n        description: List VPC endpoints\n        call: amazon-privatelink.describe-endpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ POST\n        name: create-endpoint\n        description: Create a VPC endpoint\n        call: amazon-privatelink.create-endpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections\n      name: connections\n      description: Endpoint connection management\n      operations:\n      - method: GET\n        name: list-connections\n        description: List endpoint connections\n        call: amazon-privatelink.describe-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: accept-connections\n        description: Accept endpoint connections\n        call: amazon-privatelink.accept-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: private-connectivity-mcp\n    transport: http\n    description: MCP server for AI-assisted private connectivity workflows with Amazon PrivateLink.\n    tools:\n\
  \    - name: list-endpoint-services\n      description: List available VPC endpoint services for private connectivity\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-privatelink.describe-endpoint-services\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-endpoint-service\n      description: Create a VPC endpoint service backed by a load balancer\n      hints:\n        readOnly: false\n        destructive: false\n      call: amazon-privatelink.create-endpoint-service\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vpc-endpoints\n      description: List VPC endpoints in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-privatelink.describe-endpoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-vpc-endpoint\n      description: Create a private VPC endpoint for an AWS service or endpoint service\n\
  \      hints:\n        readOnly: false\n        destructive: false\n      call: amazon-privatelink.create-endpoint\n      with:\n        vpc_id: tools.vpc_id\n        service_name: tools.service_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-endpoint-connections\n      description: List pending and active connections to endpoint services\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-privatelink.describe-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: accept-endpoint-connections\n      description: Accept pending VPC endpoint connection requests\n      hints:\n        readOnly: false\n        destructive: false\n      call: amazon-privatelink.accept-connections\n      with:\n        service_id: tools.service_id\n        endpoint_ids: tools.endpoint_ids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reject-endpoint-connections\n \
  \     description: Reject VPC endpoint connection requests\n      hints:\n        readOnly: false\n        destructive: true\n      call: amazon-privatelink.reject-connections\n      with:\n        service_id: tools.service_id\n        endpoint_ids: tools.endpoint_ids\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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

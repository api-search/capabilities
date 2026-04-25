---
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
- create a vpc endpoint service backed by a load balancer
- networking
- reject endpoint connections
- zero trust
- reject vpc endpoint connection requests
- list endpoint connections
- create endpoint
- private vpc connectivity workflow
- vpc endpoint service provider management
- security
- accept connections
- list available vpc endpoint services for private connectivity
- create a vpc endpoint
- list vpc endpoints in the account
- vpc
- accept endpoint connections
- Platform Engineer
- accept pending vpc endpoint connection requests
- manages vpc endpoint services and private connectivity architecture
- create endpoint service
- endpoint services
- create vpc endpoint
- list endpoints
- list pending and active connections to endpoint services
- private connectivity
- amazon
- create a private vpc endpoint for an aws service or endpoint service
- Network Engineer
- list vpc endpoint services
- consumes endpoint services and manages vpc endpoints for internal services
- aws
- list endpoint services
- list connections
- list vpc endpoints
- vpc endpoint consumer management
- endpoint connection management
- create a vpc endpoint service
slug: private-connectivity
tags:
- Amazon
- AWS
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

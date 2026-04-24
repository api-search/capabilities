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
- vpc
- list endpoint services
- Platform Engineer
- create vpc endpoint
- private connectivity
- endpoint connection management
- reject endpoint connections
- Network Engineer
- accept connections
- create a vpc endpoint service backed by a load balancer
- create a vpc endpoint service
- networking
- create a vpc endpoint
- endpoint services
- vpc endpoint consumer management
- list vpc endpoints in the account
- list pending and active connections to endpoint services
- create a private vpc endpoint for an aws service or endpoint service
- vpc endpoint service provider management
- accept endpoint connections
- reject vpc endpoint connection requests
- list available vpc endpoint services for private connectivity
- list endpoint connections
- aws
- create endpoint service
- list endpoints
- list vpc endpoints
- amazon
- list vpc endpoint services
- security
- consumes endpoint services and manages vpc endpoints for internal services
- zero trust
- private vpc connectivity workflow
- manages vpc endpoint services and private connectivity architecture
- list connections
- create endpoint
- accept pending vpc endpoint connection requests
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

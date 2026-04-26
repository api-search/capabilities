---
consumed_apis:
- apiida-control-plane
- apiida-gateway-manager
description: Unified workflow for federated API management across multiple API gateways using APIIDA - validating specs, deploying APIs, monitoring gateways, and managing API lifecycle from a central control plane.
layout: capability
name: APIIDA Federated API Management
operations:
- description: List all managed APIs.
  method: GET
  name: list-apis
  path: /v1/apis
- description: List all managed gateways.
  method: GET
  name: list-gateways
  path: /v1/gateways
personas: []
provider_name: APIIDA
provider_slug: apiida
search_terms:
- API Platform Engineer
- Enterprise Architect
- federated
- gateway
- list gateways
- engineer managing apis across multiple gateways using apiida's federated control plane.
- list all managed gateways.
- api management
- deploy a validated api to one or more gateway environments.
- governance
- deploy api to gateways
- architect overseeing multi-gateway api strategy and governance.
- api gateway
- list all apis managed across the apiida federated control plane.
- list all managed apis.
- validate an openapi proxy specification before deployment.
- get monitoring and performance metrics for a specific gateway.
- get gateway metrics
- validate api specification
- enterprise
- list managed apis
- list managed gateways
- federated api management
- list apis
- apiida
- layer7
- list all broadcom layer7 gateways registered in the gateway manager.
slug: federated-api-management
tags:
- APIIDA
- API Management
- Federated
- Gateway
- Enterprise
tools:
- description: List all APIs managed across the APIIDA federated control plane.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-managed-apis
- description: Validate an OpenAPI proxy specification before deployment.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: validate-api-specification
- description: Deploy a validated API to one or more gateway environments.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-api-to-gateways
- description: List all Broadcom Layer7 gateways registered in the gateway manager.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-managed-gateways
- description: Get monitoring and performance metrics for a specific gateway.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-gateway-metrics
---

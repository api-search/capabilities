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
- enterprise
- layer7
- list apis
- get gateway metrics
- api management
- validate api specification
- governance
- federated api management
- list all managed apis.
- deploy a validated api to one or more gateway environments.
- list all broadcom layer7 gateways registered in the gateway manager.
- API Platform Engineer
- architect overseeing multi-gateway api strategy and governance.
- apiida
- list managed gateways
- deploy api to gateways
- Enterprise Architect
- engineer managing apis across multiple gateways using apiida's federated control plane.
- list managed apis
- federated
- list gateways
- api gateway
- gateway
- get monitoring and performance metrics for a specific gateway.
- list all apis managed across the apiida federated control plane.
- validate an openapi proxy specification before deployment.
- list all managed gateways.
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

---
categories:
- api-management
- platform
consumed_apis:
- apigee-management
description: Workflow capability for API platform engineers publishing managed proxies from OpenAPI specs through Apigee — the gate every Ford API has to pass through before it reaches consumers, agents, or partners. Combines spec import, proxy creation, environment deployment, and product attachment into a single governed publishing pipeline so AI-era integrations inherit the same controls as every other Ford API.
layout: capability
name: Apigee OpenAPI Proxy Publishing
operations:
- description: Import an OpenAPI specification into the Apigee organization as a reusable artifact
  method: POST
  name: import-openapi-spec
  path: /v1/organizations/{org}/specs
- description: Create a new API proxy bundle generated from an imported OpenAPI spec
  method: POST
  name: create-proxy-from-spec
  path: /v1/organizations/{org}/apis
- description: Deploy a specific proxy revision to a target Apigee environment
  method: POST
  name: deploy-proxy-to-environment
  path: /v1/organizations/{org}/environments/{env}/apis/{api}/revisions/{rev}/deployments
- description: List the deployment status of a proxy across all environments
  method: GET
  name: list-deployment-status
  path: /v1/organizations/{org}/apis/{api}/deployments
- description: Attach the deployed proxy to an API product so it can be entitled to consumers and agents
  method: POST
  name: attach-api-product
  path: /v1/organizations/{org}/apiproducts
- description: List the published API products available in the organization
  method: GET
  name: list-api-products
  path: /v1/organizations/{org}/apiproducts
personas:
- API Platform Engineer
- Head of AI
provider_name: Apigee
provider_slug: apigee
search_terms:
- publish a new managed proxy from an openapi spec
- the gate every ford api has to pass through
- import openapi spec to apigee
- create proxy from spec
- deploy proxy to environment
- list deployment status
- attach api product
- ford api governance pipeline
- openapi to apigee proxy
- governed ai-era integration
- api platform engineer
- head of ai
- apigee management api
- api publishing pipeline
- openapi spec import
- proxy revision deployment
- api product entitlement
- managed proxy publishing
- ford api governance
- agent-ready api publishing
- openapi gate
- api management
- platform
slug: openapi-proxy-publishing
tags:
- API Management
- Apigee
- OpenAPI
- API Governance
- Proxy Publishing
tools:
- description: Import an OpenAPI specification into the Apigee organization as a reusable artifact for proxy generation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: import-openapi-spec
- description: Create a new API proxy bundle generated from an imported OpenAPI spec, producing a deployable revision
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-proxy-from-spec
- description: Deploy a specific proxy revision to a target Apigee environment so it begins serving traffic
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: deploy-proxy-to-environment
- description: List the deployment status of a proxy across all environments to verify rollout
  hints:
    openWorld: false
    readOnly: true
  name: list-deployment-status
- description: Attach the deployed proxy to an API product so it can be entitled to consumers, partners, and agents
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: attach-api-product
- description: List the published API products available in the organization for entitlement and discovery
  hints:
    openWorld: false
    readOnly: true
  name: list-api-products
---

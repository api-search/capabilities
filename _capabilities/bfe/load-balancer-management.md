---
consumed_apis:
- bfe-management
description: Workflow capability for managing BFE load balancer operations including runtime metrics collection, configuration hot reload, and observability for infrastructure and platform engineering teams.
layout: capability
name: BFE Load Balancer Management
operations:
- description: Get BFE runtime metrics and performance counters
  method: GET
  name: get-metrics
  path: /v1/metrics
- description: Get available monitoring metric categories
  method: GET
  name: get-categories
  path: /v1/categories
- description: Trigger hot reload of BFE routing rules and configuration
  method: POST
  name: reload-config
  path: /v1/reload
personas: []
provider_name: BFE
provider_slug: bfe
search_terms:
- dynamic configuration management and reload
- retrieve bfe runtime monitoring metrics
- hot reload bfe configuration
- trigger hot reload of bfe routing rules and configuration
- networking
- get bfe runtime metrics and performance counters
- retrieve available metric categories
- get metrics
- load balancer
- open source
- reload config
- reload bfe config
- management
- bfe
- get categories
- list available bfe metric categories for targeted monitoring
- monitoring
- metrics, logging, and distributed tracing
- retrieve bfe load balancer runtime metrics and performance counters for monitoring
- layer 7 load balancing and traffic routing
- traffic management
- baidu
- get available monitoring metric categories
- trigger a hot reload of bfe routing and load balancing configuration without restart
- engineer managing bfe load balancer deployments and configuration
- cncf
- get metric categories
- get bfe metrics
- configuration
slug: load-balancer-management
tags:
- BFE
- Load Balancer
- Management
- Monitoring
- Configuration
tools:
- description: Retrieve BFE load balancer runtime metrics and performance counters for monitoring
  hints:
    openWorld: false
    readOnly: true
  name: get-bfe-metrics
- description: List available BFE metric categories for targeted monitoring
  hints:
    openWorld: false
    readOnly: true
  name: get-metric-categories
- description: Trigger a hot reload of BFE routing and load balancing configuration without restart
  hints:
    openWorld: false
    readOnly: false
  name: reload-bfe-config
---

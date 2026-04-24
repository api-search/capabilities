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
- cncf
- get available monitoring metric categories
- retrieve bfe load balancer runtime metrics and performance counters for monitoring
- monitoring
- metrics, logging, and distributed tracing
- configuration
- list available bfe metric categories for targeted monitoring
- bfe
- trigger hot reload of bfe routing rules and configuration
- networking
- baidu
- trigger a hot reload of bfe routing and load balancing configuration without restart
- retrieve available metric categories
- get metrics
- open source
- engineer managing bfe load balancer deployments and configuration
- retrieve bfe runtime monitoring metrics
- dynamic configuration management and reload
- reload bfe config
- traffic management
- management
- load balancer
- get bfe runtime metrics and performance counters
- reload config
- get metric categories
- layer 7 load balancing and traffic routing
- hot reload bfe configuration
- get categories
- get bfe metrics
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

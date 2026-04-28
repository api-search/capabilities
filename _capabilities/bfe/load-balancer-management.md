---
categories:
- monitoring
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
- traffic management
- get metric categories
- management
- reload config
- hot reload bfe configuration
- retrieve bfe load balancer runtime metrics and performance counters for monitoring
- get bfe metrics
- dynamic configuration management and reload
- reload bfe config
- get metrics
- get available monitoring metric categories
- load balancer
- layer 7 load balancing and traffic routing
- open source
- retrieve available metric categories
- configuration
- networking
- baidu
- get bfe runtime metrics and performance counters
- monitoring
- bfe
- get categories
- trigger a hot reload of bfe routing and load balancing configuration without restart
- engineer managing bfe load balancer deployments and configuration
- metrics, logging, and distributed tracing
- list available bfe metric categories for targeted monitoring
- trigger hot reload of bfe routing rules and configuration
- cncf
- retrieve bfe runtime monitoring metrics
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

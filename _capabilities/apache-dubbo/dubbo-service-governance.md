---
categories: []
consumed_apis:
- dubbo-admin
description: Unified capability for governing Apache Dubbo microservices — managing services, applications, traffic rules, routing policies, and monitoring cluster health. Designed for platform engineers and SREs managing Dubbo clusters.
layout: capability
name: Apache Dubbo Service Governance
operations:
- description: List all registered Dubbo applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: List all registered Dubbo services
  method: GET
  name: list-services
  path: /v1/services
- description: List condition routing rules
  method: GET
  name: list-condition-routes
  path: /v1/traffic-rules
- description: Create a new condition routing rule
  method: POST
  name: create-condition-route
  path: /v1/traffic-rules
- description: Get Dubbo cluster health metrics
  method: GET
  name: get-cluster-metrics
  path: /v1/metrics
personas: []
provider_name: Apache Dubbo
provider_slug: apache-dubbo
search_terms:
- list dubbo services
- platform engineering
- rpc
- manage services, applications, traffic rules, and cluster monitoring
- get cluster metrics
- list dubbo applications
- cluster monitoring metrics
- list all applications registered in the dubbo cluster
- create traffic rule
- get dubbo cluster health metrics
- service mesh
- create a new condition routing rule
- manage traffic routing rules
- engineers managing the dubbo cluster infrastructure and governance policies
- service governance
- manage dubbo applications
- routing rules, load balancing, gray releases, and traffic shaping
- manage dubbo services
- traffic management
- list services
- apache
- list applications
- list traffic rules
- create condition route
- Platform Engineer
- go
- list condition routing rules
- get health and performance metrics for the dubbo cluster
- list condition routes
- apache dubbo
- SRE
- sres monitoring cluster health and responding to service incidents
- open source
- list all registered dubbo services
- microservices
- list all condition routing rules in the cluster
- cluster metrics, flow metrics, and observability
- list all services registered in the dubbo cluster
- service discovery
- java
- discovery, registration, and lifecycle of dubbo services and applications
- create a new condition routing rule for traffic management
- list all registered dubbo applications
slug: dubbo-service-governance
tags:
- Apache Dubbo
- Service Governance
- Microservices
- Traffic Management
- Platform Engineering
tools:
- description: List all applications registered in the Dubbo cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-dubbo-applications
- description: List all services registered in the Dubbo cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-dubbo-services
- description: List all condition routing rules in the cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-traffic-rules
- description: Create a new condition routing rule for traffic management
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-traffic-rule
- description: Get health and performance metrics for the Dubbo cluster
  hints:
    openWorld: true
    readOnly: true
  name: get-cluster-metrics
---

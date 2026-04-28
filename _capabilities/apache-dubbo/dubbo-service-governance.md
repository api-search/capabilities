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
- get dubbo cluster health metrics
- manage dubbo applications
- rpc
- manage traffic routing rules
- create condition route
- service discovery
- microservices
- manage services, applications, traffic rules, and cluster monitoring
- apache dubbo
- create a new condition routing rule
- engineers managing the dubbo cluster infrastructure and governance policies
- sres monitoring cluster health and responding to service incidents
- list all applications registered in the dubbo cluster
- list dubbo applications
- list all condition routing rules in the cluster
- list all services registered in the dubbo cluster
- list traffic rules
- list condition routes
- get health and performance metrics for the dubbo cluster
- java
- SRE
- platform engineering
- traffic management
- service governance
- manage dubbo services
- routing rules, load balancing, gray releases, and traffic shaping
- cluster metrics, flow metrics, and observability
- go
- Platform Engineer
- apache
- create a new condition routing rule for traffic management
- list dubbo services
- list all registered dubbo services
- list all registered dubbo applications
- list services
- service mesh
- list condition routing rules
- open source
- list applications
- discovery, registration, and lifecycle of dubbo services and applications
- cluster monitoring metrics
- create traffic rule
- get cluster metrics
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

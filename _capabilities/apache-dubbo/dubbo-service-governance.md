---
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
- Platform Engineer
- list all applications registered in the dubbo cluster
- service discovery
- routing rules, load balancing, gray releases, and traffic shaping
- go
- create a new condition routing rule
- list applications
- service mesh
- manage dubbo applications
- get dubbo cluster health metrics
- list traffic rules
- manage services, applications, traffic rules, and cluster monitoring
- list condition routing rules
- list condition routes
- list all services registered in the dubbo cluster
- java
- cluster monitoring metrics
- list all registered dubbo applications
- list dubbo services
- list dubbo applications
- engineers managing the dubbo cluster infrastructure and governance policies
- discovery, registration, and lifecycle of dubbo services and applications
- apache dubbo
- create a new condition routing rule for traffic management
- microservices
- get cluster metrics
- sres monitoring cluster health and responding to service incidents
- traffic management
- SRE
- platform engineering
- manage traffic routing rules
- cluster metrics, flow metrics, and observability
- manage dubbo services
- list services
- get health and performance metrics for the dubbo cluster
- apache
- rpc
- list all condition routing rules in the cluster
- create traffic rule
- service governance
- list all registered dubbo services
- create condition route
- open source
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

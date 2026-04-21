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
- create condition route
- list all services registered in the dubbo cluster
- get health and performance metrics for the dubbo cluster
- open source
- manage dubbo applications
- list all registered dubbo services
- java
- Platform Engineer
- list all registered dubbo applications
- apache dubbo
- list condition routing rules
- list services
- manage dubbo services
- manage traffic routing rules
- create traffic rule
- platform engineering
- cluster metrics, flow metrics, and observability
- SRE
- apache
- engineers managing the dubbo cluster infrastructure and governance policies
- routing rules, load balancing, gray releases, and traffic shaping
- cluster monitoring metrics
- rpc
- get dubbo cluster health metrics
- service governance
- list dubbo applications
- sres monitoring cluster health and responding to service incidents
- service mesh
- microservices
- list all condition routing rules in the cluster
- traffic management
- service discovery
- list dubbo services
- manage services, applications, traffic rules, and cluster monitoring
- create a new condition routing rule
- list condition routes
- go
- get cluster metrics
- create a new condition routing rule for traffic management
- list all applications registered in the dubbo cluster
- list traffic rules
- discovery, registration, and lifecycle of dubbo services and applications
- list applications
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

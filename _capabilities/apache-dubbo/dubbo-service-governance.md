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
- list traffic rules
- manage dubbo applications
- manage services, applications, traffic rules, and cluster monitoring
- list all registered dubbo services
- get dubbo cluster health metrics
- service mesh
- cluster metrics, flow metrics, and observability
- go
- java
- list condition routing rules
- apache
- create a new condition routing rule
- engineers managing the dubbo cluster infrastructure and governance policies
- get cluster metrics
- sres monitoring cluster health and responding to service incidents
- apache dubbo
- discovery, registration, and lifecycle of dubbo services and applications
- manage dubbo services
- list condition routes
- cluster monitoring metrics
- manage traffic routing rules
- list dubbo applications
- create a new condition routing rule for traffic management
- list services
- get health and performance metrics for the dubbo cluster
- SRE
- create condition route
- Platform Engineer
- list all condition routing rules in the cluster
- service governance
- rpc
- traffic management
- list applications
- list all applications registered in the dubbo cluster
- platform engineering
- create traffic rule
- list all registered dubbo applications
- list all services registered in the dubbo cluster
- routing rules, load balancing, gray releases, and traffic shaping
- open source
- list dubbo services
- microservices
- service discovery
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

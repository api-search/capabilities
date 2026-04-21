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
- manage dubbo applications
- traffic management
- create a new condition routing rule for traffic management
- list dubbo services
- Platform Engineer
- list all registered dubbo services
- create a new condition routing rule
- rpc
- go
- discovery, registration, and lifecycle of dubbo services and applications
- apache dubbo
- manage dubbo services
- sres monitoring cluster health and responding to service incidents
- list applications
- list all registered dubbo applications
- list services
- get dubbo cluster health metrics
- list condition routing rules
- list all condition routing rules in the cluster
- get cluster metrics
- manage services, applications, traffic rules, and cluster monitoring
- platform engineering
- engineers managing the dubbo cluster infrastructure and governance policies
- java
- service governance
- manage traffic routing rules
- get health and performance metrics for the dubbo cluster
- create traffic rule
- list condition routes
- cluster monitoring metrics
- create condition route
- list all applications registered in the dubbo cluster
- routing rules, load balancing, gray releases, and traffic shaping
- service discovery
- service mesh
- list traffic rules
- SRE
- list all services registered in the dubbo cluster
- cluster metrics, flow metrics, and observability
- apache
- microservices
- open source
- list dubbo applications
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

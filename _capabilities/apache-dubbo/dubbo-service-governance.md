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
- routing rules, load balancing, gray releases, and traffic shaping
- go
- service discovery
- Platform Engineer
- cluster metrics, flow metrics, and observability
- list condition routes
- manage traffic routing rules
- discovery, registration, and lifecycle of dubbo services and applications
- manage services, applications, traffic rules, and cluster monitoring
- java
- platform engineering
- manage dubbo applications
- get dubbo cluster health metrics
- create traffic rule
- SRE
- list applications
- sres monitoring cluster health and responding to service incidents
- list all applications registered in the dubbo cluster
- list all services registered in the dubbo cluster
- service mesh
- list condition routing rules
- apache
- list dubbo applications
- create condition route
- create a new condition routing rule
- list traffic rules
- open source
- create a new condition routing rule for traffic management
- traffic management
- list all condition routing rules in the cluster
- list dubbo services
- rpc
- get health and performance metrics for the dubbo cluster
- apache dubbo
- list all registered dubbo services
- service governance
- list services
- get cluster metrics
- list all registered dubbo applications
- manage dubbo services
- engineers managing the dubbo cluster infrastructure and governance policies
- microservices
- cluster monitoring metrics
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

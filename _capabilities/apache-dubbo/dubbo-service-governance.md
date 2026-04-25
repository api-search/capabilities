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
- list services
- list all condition routing rules in the cluster
- create traffic rule
- create a new condition routing rule for traffic management
- java
- list applications
- create a new condition routing rule
- list all registered dubbo applications
- microservices
- sres monitoring cluster health and responding to service incidents
- list all registered dubbo services
- list dubbo services
- open source
- engineers managing the dubbo cluster infrastructure and governance policies
- list dubbo applications
- rpc
- SRE
- service discovery
- list condition routing rules
- apache dubbo
- manage dubbo applications
- manage dubbo services
- apache
- get dubbo cluster health metrics
- list traffic rules
- Platform Engineer
- list all applications registered in the dubbo cluster
- cluster monitoring metrics
- traffic management
- list condition routes
- manage services, applications, traffic rules, and cluster monitoring
- get health and performance metrics for the dubbo cluster
- get cluster metrics
- discovery, registration, and lifecycle of dubbo services and applications
- service governance
- list all services registered in the dubbo cluster
- routing rules, load balancing, gray releases, and traffic shaping
- cluster metrics, flow metrics, and observability
- manage traffic routing rules
- create condition route
- platform engineering
- go
- service mesh
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

---
consumed_apis:
- akka-management
description: Workflow for monitoring and managing Akka cluster operations including health checks, member management, and cluster bootstrap. For platform engineers and SREs operating distributed Akka systems.
layout: capability
name: Akka Cluster Operations
operations:
- description: Node liveness check
  method: GET
  name: check-alive
  path: /v1/health
- description: Node readiness check
  method: GET
  name: check-ready
  path: /v1/health
- description: List cluster members
  method: GET
  name: list-members
  path: /v1/cluster/members
- description: Join a cluster member
  method: POST
  name: join-member
  path: /v1/cluster/members
personas: []
provider_name: Akka
provider_slug: akka
search_terms:
- join a cluster member
- SRE
- check if akka cluster nodes are ready to serve traffic
- scala
- node readiness check
- cluster health checks
- cluster member management
- join cluster member
- Platform Engineer
- akka cluster membership and node lifecycle management
- java
- reactive
- health monitoring
- check ready
- check cluster health
- akka
- monitors cluster health and responds to incidents
- monitor and manage akka cluster health and membership
- cluster management
- node liveness check
- join member
- liveness and readiness health check monitoring
- actor model
- list members
- check liveness and readiness of akka cluster nodes
- add a new node to the akka cluster
- list all current members of the akka cluster
- distributed systems
- check cluster readiness
- frameworks
- microservices
- operations
- check alive
- list cluster members
- manages akka cluster deployments and configurations
slug: cluster-operations
tags:
- Akka
- Cluster Management
- Distributed Systems
- Operations
- Health Monitoring
tools:
- description: Check liveness and readiness of Akka cluster nodes
  hints:
    openWorld: false
    readOnly: true
  name: check-cluster-health
- description: Check if Akka cluster nodes are ready to serve traffic
  hints:
    openWorld: false
    readOnly: true
  name: check-cluster-readiness
- description: List all current members of the Akka cluster
  hints:
    openWorld: false
    readOnly: true
  name: list-cluster-members
- description: Add a new node to the Akka cluster
  hints:
    destructive: false
    readOnly: false
  name: join-cluster-member
---

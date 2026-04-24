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
- list members
- node readiness check
- monitor and manage akka cluster health and membership
- microservices
- join member
- monitors cluster health and responds to incidents
- Platform Engineer
- check liveness and readiness of akka cluster nodes
- java
- distributed systems
- SRE
- scala
- check cluster readiness
- akka cluster membership and node lifecycle management
- health monitoring
- add a new node to the akka cluster
- list cluster members
- check ready
- frameworks
- check cluster health
- actor model
- check if akka cluster nodes are ready to serve traffic
- join a cluster member
- node liveness check
- liveness and readiness health check monitoring
- reactive
- list all current members of the akka cluster
- cluster member management
- join cluster member
- operations
- cluster management
- check alive
- akka
- cluster health checks
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

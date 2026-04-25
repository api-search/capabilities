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
- cluster health checks
- liveness and readiness health check monitoring
- list all current members of the akka cluster
- check if akka cluster nodes are ready to serve traffic
- akka
- cluster member management
- check alive
- Platform Engineer
- microservices
- operations
- check ready
- list cluster members
- node readiness check
- manages akka cluster deployments and configurations
- check liveness and readiness of akka cluster nodes
- health monitoring
- akka cluster membership and node lifecycle management
- frameworks
- add a new node to the akka cluster
- monitors cluster health and responds to incidents
- distributed systems
- join cluster member
- actor model
- join a cluster member
- join member
- monitor and manage akka cluster health and membership
- scala
- check cluster health
- reactive
- list members
- SRE
- java
- node liveness check
- check cluster readiness
- cluster management
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

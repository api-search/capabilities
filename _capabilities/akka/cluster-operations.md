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
- health monitoring
- list members
- cluster health checks
- cluster member management
- check cluster readiness
- Platform Engineer
- check alive
- list all current members of the akka cluster
- cluster management
- node liveness check
- reactive
- actor model
- operations
- add a new node to the akka cluster
- node readiness check
- java
- monitor and manage akka cluster health and membership
- join cluster member
- frameworks
- monitors cluster health and responds to incidents
- list cluster members
- akka
- check if akka cluster nodes are ready to serve traffic
- liveness and readiness health check monitoring
- manages akka cluster deployments and configurations
- scala
- check cluster health
- check ready
- distributed systems
- join member
- check liveness and readiness of akka cluster nodes
- SRE
- microservices
- akka cluster membership and node lifecycle management
- join a cluster member
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

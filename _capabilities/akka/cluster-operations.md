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
- actor model
- list members
- distributed systems
- check alive
- frameworks
- liveness and readiness health check monitoring
- check liveness and readiness of akka cluster nodes
- list cluster members
- join member
- monitors cluster health and responds to incidents
- join cluster member
- java
- operations
- node liveness check
- add a new node to the akka cluster
- node readiness check
- monitor and manage akka cluster health and membership
- check if akka cluster nodes are ready to serve traffic
- cluster member management
- scala
- reactive
- list all current members of the akka cluster
- check ready
- akka cluster membership and node lifecycle management
- join a cluster member
- check cluster readiness
- health monitoring
- SRE
- Platform Engineer
- check cluster health
- akka
- cluster management
- manages akka cluster deployments and configurations
- cluster health checks
- microservices
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

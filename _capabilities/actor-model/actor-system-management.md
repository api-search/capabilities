---
consumed_apis:
- actor-model
description: Workflow for managing actor lifecycle, message passing, supervision hierarchies, and cluster operations in distributed actor model systems. Used by platform engineers and distributed systems developers.
layout: capability
name: Actor System Management
operations:
- description: List all active actors
  method: GET
  name: list-actors
  path: /v1/actors
- description: Spawn a new actor
  method: POST
  name: spawn-actor
  path: /v1/actors
- description: Get system health
  method: GET
  name: get-health
  path: /v1/health
personas: []
provider_name: Actor Model
provider_slug: actor-model
search_terms:
- actor model
- distributed systems
- list all actors in the system filtered by status
- list supervisors with their strategies and child actor counts
- supervision
- concurrent computation using actors, message passing, and isolation
- list cluster members
- spawn actor
- send a typed message to an actor's mailbox for asynchronous processing
- inspect mailbox
- distributed cluster management, sharding, and fault tolerance
- system health status
- concurrency
- spawn a new actor
- Site Reliability Engineer
- get health
- builds and operates distributed platforms using actor model frameworks like akka or orleans
- send message
- inspect pending messages in an actor's mailbox for debugging
- get actor system health including throughput, error rate, and dead letter count
- Distributed Systems Developer
- designs concurrent, fault-tolerant systems using actor model patterns
- list supervisors
- get system health
- list actors
- list all active actors
- Platform Engineer
- monitors actor system health, throughput, and failure recovery
- get details of a specific actor including mailbox size and restart count
- list all cluster nodes with their status, roles, and actor counts
- get actor
- cluster management
- actor lifecycle management
- manage actor lifecycle, message passing, supervision hierarchies, and cluster operations
slug: actor-system-management
tags:
- Actor Model
- Concurrency
- Distributed Systems
- Supervision
- Cluster Management
tools:
- description: List all actors in the system filtered by status
  hints:
    openWorld: true
    readOnly: true
  name: list-actors
- description: Get details of a specific actor including mailbox size and restart count
  hints:
    openWorld: false
    readOnly: true
  name: get-actor
- description: Send a typed message to an actor's mailbox for asynchronous processing
  hints:
    openWorld: true
    readOnly: false
  name: send-message
- description: Inspect pending messages in an actor's mailbox for debugging
  hints:
    openWorld: false
    readOnly: true
  name: inspect-mailbox
- description: List supervisors with their strategies and child actor counts
  hints:
    openWorld: true
    readOnly: true
  name: list-supervisors
- description: List all cluster nodes with their status, roles, and actor counts
  hints:
    openWorld: true
    readOnly: true
  name: list-cluster-members
- description: Get actor system health including throughput, error rate, and dead letter count
  hints:
    openWorld: true
    readOnly: true
  name: get-health
---

---
consumed_apis:
- ignite-rest-api
description: Workflow capability for database administrators and platform engineers to manage Apache Ignite clusters, execute SQL queries, and configure distributed nodes.
layout: capability
name: Apache Ignite Cluster Management
operations:
- description: Get cluster state
  method: GET
  name: get-cluster-state
  path: /v1/cluster
- description: Execute SQL query
  method: POST
  name: execute-sql
  path: /v1/sql
- description: Get cluster configuration
  method: GET
  name: get-configuration
  path: /v1/configuration
personas: []
provider_name: Apache Ignite
provider_slug: apache-ignite
search_terms:
- apache ignite
- database administration
- Platform Engineer
- init cluster
- execute sql
- update apache ignite cluster configuration parameters
- dbas who manage ignite cluster health, configuration, and sql workloads
- get configuration
- retrieve the current state and health of the apache ignite cluster
- in-memory database
- Database Administrator
- update configuration
- cluster management
- distributed database
- get cluster configuration
- execute sql query
- engineers who deploy and maintain ignite clusters in production
- compute grid
- execute sql queries on the distributed ignite cluster
- sql
- caching
- retrieve the current apache ignite cluster configuration
- in-memory
- initialize a new apache ignite cluster
- open source
- database administrators and platform engineers managing ignite clusters
- get cluster state
slug: cluster-management
tags:
- Apache Ignite
- Cluster Management
- Database Administration
- In-Memory Database
tools:
- description: Retrieve the current state and health of the Apache Ignite cluster
  hints:
    openWorld: true
    readOnly: true
  name: get-cluster-state
- description: Initialize a new Apache Ignite cluster
  hints:
    readOnly: false
  name: init-cluster
- description: Execute SQL queries on the distributed Ignite cluster
  hints:
    readOnly: false
  name: execute-sql
- description: Retrieve the current Apache Ignite cluster configuration
  hints:
    openWorld: true
    readOnly: true
  name: get-configuration
- description: Update Apache Ignite cluster configuration parameters
  hints:
    idempotent: true
    readOnly: false
  name: update-configuration
---

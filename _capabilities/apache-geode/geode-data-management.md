---
categories: []
consumed_apis:
- geode-rest
description: Unified capability for managing data in Apache Geode in-memory data grid — accessing regions, executing OQL queries, and running server-side functions. Designed for application developers and platform engineers working with high-performance in-memory data.
layout: capability
name: Apache Geode Data Management
operations:
- description: List all Geode regions
  method: GET
  name: list-regions
  path: /v1/regions
- description: Execute an OQL query
  method: GET
  name: execute-query
  path: /v1/queries
- description: List available functions
  method: GET
  name: list-functions
  path: /v1/functions
personas: []
provider_name: Apache Geode
provider_slug: apache-geode
search_terms:
- list available functions
- high-performance in-memory data caching and distribution
- in-memory data grid
- get all keys stored in a geode region
- developers using geode as a fast data store for applications
- execute an oql query
- platform engineering
- data management
- list geode functions
- distributed systems
- region crud operations, oql queries, and function execution
- execute an oql query against geode regions
- server-side function execution
- list functions
- apache
- caching
- open source
- list all regions in the apache geode data grid
- execute oql query
- list all server-side functions available in the cluster
- list all geode regions
- data grid
- list geode regions
- list regions
- Application Developer
- apache geode
- manage in-memory data with regions, queries, and functions
- get region keys
- execute query
- engineers managing the geode cluster infrastructure
- in-memory
- oql query execution
- geode region management
- Platform Engineer
slug: geode-data-management
tags:
- Apache Geode
- In-Memory Data Grid
- Caching
- Data Management
- Platform Engineering
tools:
- description: List all regions in the Apache Geode data grid
  hints:
    openWorld: true
    readOnly: true
  name: list-geode-regions
- description: Get all keys stored in a Geode region
  hints:
    openWorld: true
    readOnly: true
  name: get-region-keys
- description: Execute an OQL query against Geode regions
  hints:
    openWorld: true
    readOnly: true
  name: execute-oql-query
- description: List all server-side functions available in the cluster
  hints:
    openWorld: true
    readOnly: true
  name: list-geode-functions
---

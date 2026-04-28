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
- execute an oql query
- platform engineering
- apache geode
- server-side function execution
- developers using geode as a fast data store for applications
- caching
- region crud operations, oql queries, and function execution
- list all server-side functions available in the cluster
- data grid
- manage in-memory data with regions, queries, and functions
- execute query
- list available functions
- high-performance in-memory data caching and distribution
- in-memory data grid
- list all geode regions
- apache
- execute an oql query against geode regions
- Platform Engineer
- execute oql query
- list functions
- list geode functions
- list regions
- Application Developer
- open source
- list all regions in the apache geode data grid
- in-memory
- oql query execution
- list geode regions
- get all keys stored in a geode region
- geode region management
- distributed systems
- get region keys
- data management
- engineers managing the geode cluster infrastructure
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

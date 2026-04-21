---
consumed_apis:
- iceberg-rest-catalog
description: Workflow capability for data engineers and lakehouse architects to manage namespaces, tables, and views in Apache Iceberg catalogs via the REST Catalog API.
layout: capability
name: Apache Iceberg Catalog Management
operations:
- description: Get Iceberg catalog configuration settings
  method: GET
  name: get-config
  path: /v1/config
- description: List all namespaces in the catalog
  method: GET
  name: list-namespaces
  path: /v1/namespaces
- description: Create a new namespace
  method: POST
  name: create-namespace
  path: /v1/namespaces
- description: Load namespace metadata
  method: GET
  name: load-namespace-metadata
  path: /v1/namespaces/{namespace}
- description: Drop a namespace
  method: DELETE
  name: drop-namespace
  path: /v1/namespaces/{namespace}
- description: List all tables in a namespace
  method: GET
  name: list-tables
  path: /v1/namespaces/{namespace}/tables
- description: Create a new Iceberg table
  method: POST
  name: create-table
  path: /v1/namespaces/{namespace}/tables
- description: Load a table from the catalog
  method: GET
  name: load-table
  path: /v1/namespaces/{namespace}/tables/{table}
- description: Drop a table from the catalog
  method: DELETE
  name: drop-table
  path: /v1/namespaces/{namespace}/tables/{table}
- description: List all views in a namespace
  method: GET
  name: list-views
  path: /v1/namespaces/{namespace}/views
personas: []
provider_name: Apache Iceberg
provider_slug: apache-iceberg
search_terms:
- drop a namespace
- load an iceberg table and its metadata from the catalog
- load namespace metadata
- list all view identifiers in a namespace
- object storage credential management
- open source
- list namespaces
- list all iceberg table identifiers in a namespace
- get config
- retrieve iceberg catalog configuration settings
- individual table operations
- namespace management
- list all views in a namespace
- table management within a namespace
- metrics collection and reporting
- create a new view in the iceberg catalog
- data lake
- create a new namespace
- list tables
- list all namespaces in the catalog
- create view
- acid
- create a new iceberg table in a namespace
- apache
- apache iceberg
- catalog configuration
- Data Engineer
- get iceberg catalog configuration settings
- commit table
- load a table from the catalog
- create a new iceberg table
- view management within a namespace
- catalog management
- Lakehouse Architect
- list views
- engineers who build and maintain data pipelines and manage iceberg tables and namespaces
- create table
- architects who design lakehouse schemas, partition strategies, and catalog topology
- table format
- analytics
- commit updates and schema changes to an iceberg table
- lakehouse
- drop namespace
- list all namespaces in the iceberg catalog, optionally filtered by parent namespace
- drop table
- drop a table from the catalog
- drop an empty namespace from the iceberg catalog
- data engineers and lakehouse architects managing namespaces, tables, and views
- individual namespace
- create namespace
- load metadata and properties for a specific iceberg namespace
- table and namespace discovery and management
- create a new namespace in the iceberg catalog
- get catalog config
- data engineering
- load table
- server-side scan planning for compute engine integration
- list all tables in a namespace
- drop an iceberg table from the catalog
slug: catalog-management
tags:
- Apache Iceberg
- Catalog Management
- Data Engineering
- Lakehouse
- Table Format
tools:
- description: Retrieve Iceberg catalog configuration settings
  hints:
    openWorld: true
    readOnly: true
  name: get-catalog-config
- description: List all namespaces in the Iceberg catalog, optionally filtered by parent namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-namespaces
- description: Create a new namespace in the Iceberg catalog
  hints:
    readOnly: false
  name: create-namespace
- description: Load metadata and properties for a specific Iceberg namespace
  hints:
    openWorld: true
    readOnly: true
  name: load-namespace-metadata
- description: Drop an empty namespace from the Iceberg catalog
  hints:
    destructive: true
    readOnly: false
  name: drop-namespace
- description: List all Iceberg table identifiers in a namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-tables
- description: Create a new Iceberg table in a namespace
  hints:
    readOnly: false
  name: create-table
- description: Load an Iceberg table and its metadata from the catalog
  hints:
    openWorld: true
    readOnly: true
  name: load-table
- description: Commit updates and schema changes to an Iceberg table
  hints:
    idempotent: true
    readOnly: false
  name: commit-table
- description: Drop an Iceberg table from the catalog
  hints:
    destructive: true
    readOnly: false
  name: drop-table
- description: List all view identifiers in a namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-views
- description: Create a new view in the Iceberg catalog
  hints:
    readOnly: false
  name: create-view
---

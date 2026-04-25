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
- architects who design lakehouse schemas, partition strategies, and catalog topology
- list namespaces
- acid
- analytics
- data lake
- Data Engineer
- list all tables in a namespace
- table format
- list all view identifiers in a namespace
- create a new iceberg table
- server-side scan planning for compute engine integration
- create namespace
- get iceberg catalog configuration settings
- create a new namespace in the iceberg catalog
- table and namespace discovery and management
- load table
- data engineers and lakehouse architects managing namespaces, tables, and views
- drop a table from the catalog
- create view
- drop a namespace
- load namespace metadata
- engineers who build and maintain data pipelines and manage iceberg tables and namespaces
- apache iceberg
- individual table operations
- object storage credential management
- apache
- list all views in a namespace
- list views
- load a table from the catalog
- commit updates and schema changes to an iceberg table
- data engineering
- catalog configuration
- drop namespace
- drop table
- view management within a namespace
- list tables
- commit table
- namespace management
- retrieve iceberg catalog configuration settings
- get catalog config
- Lakehouse Architect
- get config
- list all namespaces in the iceberg catalog, optionally filtered by parent namespace
- drop an empty namespace from the iceberg catalog
- list all iceberg table identifiers in a namespace
- metrics collection and reporting
- create a new namespace
- create table
- catalog management
- load an iceberg table and its metadata from the catalog
- create a new iceberg table in a namespace
- list all namespaces in the catalog
- open source
- lakehouse
- load metadata and properties for a specific iceberg namespace
- table management within a namespace
- create a new view in the iceberg catalog
- individual namespace
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

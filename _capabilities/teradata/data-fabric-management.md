---
categories: []
consumed_apis:
- querygrid-manager
- query-service
description: Workflow capability for managing Teradata's data fabric infrastructure. Combines QueryGrid Manager for fabric configuration with Query Service for validating cross-system connectivity. Used by data engineers and platform administrators.
layout: capability
name: Teradata Data Fabric Management
operations:
- description: List all data centers.
  method: GET
  name: list-data-centers
  path: /v1/data-centers
- description: List all registered systems.
  method: GET
  name: list-systems
  path: /v1/systems
- description: List all bridges.
  method: GET
  name: list-bridges
  path: /v1/bridges
- description: List all current issues.
  method: GET
  name: list-issues
  path: /v1/issues
personas: []
provider_name: Teradata
provider_slug: teradata
search_terms:
- system management.
- list systems
- issue monitoring.
- list all current issues.
- list fabrics
- list bridges
- sql
- list all configured data centers.
- list all registered systems in querygrid.
- list all bridges connecting systems.
- list data centers
- execute sql queries and analytics.
- administration
- administers querygrid systems, nodes, and software.
- enterprise
- run diagnostic check
- list all bridges.
- data fabric
- Data Analyst
- manage querygrid data fabric infrastructure.
- executes queries and analyzes data across vantage systems.
- configuration
- Data Engineer
- manages data fabric infrastructure and cross-system connectivity.
- teradata
- list connectors
- list all current issues in the querygrid environment.
- list all data centers.
- Application Developer
- machine learning
- bridge management.
- Platform Administrator
- run a diagnostic check on querygrid systems.
- analytics
- system and fabric configuration management.
- data center management.
- cloud
- list all data fabric configurations.
- data warehousing
- integrates applications with teradata via rest apis.
- database
- health monitoring and issue detection.
- data management
- list all connectors for system integration.
- sql query execution and session management.
- list all registered systems.
- list issues
slug: data-fabric-management
tags:
- Teradata
- Data Fabric
- Configuration
- Administration
tools:
- description: List all configured data centers.
  hints:
    readOnly: true
  name: list-data-centers
- description: List all registered systems in QueryGrid.
  hints:
    readOnly: true
  name: list-systems
- description: List all bridges connecting systems.
  hints:
    readOnly: true
  name: list-bridges
- description: List all connectors for system integration.
  hints:
    readOnly: true
  name: list-connectors
- description: List all data fabric configurations.
  hints:
    readOnly: true
  name: list-fabrics
- description: List all current issues in the QueryGrid environment.
  hints:
    readOnly: true
  name: list-issues
- description: Run a diagnostic check on QueryGrid systems.
  hints:
    readOnly: false
  name: run-diagnostic-check
---

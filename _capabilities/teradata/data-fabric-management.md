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
- list all registered systems.
- administers querygrid systems, nodes, and software.
- run diagnostic check
- list all bridges.
- data center management.
- list data centers
- administration
- list all current issues in the querygrid environment.
- Data Engineer
- executes queries and analyzes data across vantage systems.
- system and fabric configuration management.
- health monitoring and issue detection.
- Data Analyst
- integrates applications with teradata via rest apis.
- machine learning
- list all current issues.
- list all configured data centers.
- bridge management.
- system management.
- list bridges
- list all connectors for system integration.
- list all bridges connecting systems.
- list all data fabric configurations.
- database
- list all registered systems in querygrid.
- cloud
- run a diagnostic check on querygrid systems.
- Platform Administrator
- data warehousing
- list issues
- analytics
- sql query execution and session management.
- issue monitoring.
- data management
- Application Developer
- enterprise
- list connectors
- sql
- manage querygrid data fabric infrastructure.
- teradata
- execute sql queries and analytics.
- configuration
- data fabric
- list systems
- list fabrics
- manages data fabric infrastructure and cross-system connectivity.
- list all data centers.
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

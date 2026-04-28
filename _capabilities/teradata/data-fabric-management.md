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
- data warehousing
- list all bridges connecting systems.
- list all configured data centers.
- data center management.
- list all current issues.
- Platform Administrator
- Data Analyst
- data management
- list all bridges.
- execute sql queries and analytics.
- list issues
- database
- analytics
- list systems
- executes queries and analyzes data across vantage systems.
- issue monitoring.
- system management.
- health monitoring and issue detection.
- list all data centers.
- enterprise
- configuration
- bridge management.
- administration
- administers querygrid systems, nodes, and software.
- integrates applications with teradata via rest apis.
- list connectors
- list bridges
- list all registered systems in querygrid.
- list all connectors for system integration.
- list data centers
- list all current issues in the querygrid environment.
- list fabrics
- Data Engineer
- Application Developer
- data fabric
- manage querygrid data fabric infrastructure.
- run diagnostic check
- machine learning
- list all data fabric configurations.
- list all registered systems.
- teradata
- sql query execution and session management.
- sql
- run a diagnostic check on querygrid systems.
- manages data fabric infrastructure and cross-system connectivity.
- system and fabric configuration management.
- cloud
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

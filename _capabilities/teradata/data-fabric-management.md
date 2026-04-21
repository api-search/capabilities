---
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
- Data Analyst
- configuration
- administration
- list issues
- list all bridges.
- database
- list systems
- machine learning
- list connectors
- manages data fabric infrastructure and cross-system connectivity.
- run a diagnostic check on querygrid systems.
- data management
- enterprise
- list all configured data centers.
- list all data fabric configurations.
- executes queries and analyzes data across vantage systems.
- teradata
- health monitoring and issue detection.
- data warehousing
- integrates applications with teradata via rest apis.
- list all data centers.
- cloud
- issue monitoring.
- run diagnostic check
- execute sql queries and analytics.
- list all current issues.
- Data Engineer
- list all connectors for system integration.
- list data centers
- bridge management.
- system management.
- data center management.
- list all current issues in the querygrid environment.
- analytics
- data fabric
- list all registered systems in querygrid.
- sql query execution and session management.
- sql
- administers querygrid systems, nodes, and software.
- system and fabric configuration management.
- list bridges
- Application Developer
- list fabrics
- Platform Administrator
- list all bridges connecting systems.
- manage querygrid data fabric infrastructure.
- list all registered systems.
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

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
- run diagnostic check
- list all connectors for system integration.
- data management
- sql query execution and session management.
- execute sql queries and analytics.
- Platform Administrator
- administers querygrid systems, nodes, and software.
- system and fabric configuration management.
- manages data fabric infrastructure and cross-system connectivity.
- sql
- administration
- list all data centers.
- teradata
- list all current issues.
- data warehousing
- list all registered systems in querygrid.
- list fabrics
- analytics
- Application Developer
- list all data fabric configurations.
- enterprise
- list data centers
- health monitoring and issue detection.
- list issues
- list all bridges connecting systems.
- integrates applications with teradata via rest apis.
- cloud
- data fabric
- Data Engineer
- list all current issues in the querygrid environment.
- list all configured data centers.
- configuration
- database
- list systems
- machine learning
- list all registered systems.
- list connectors
- manage querygrid data fabric infrastructure.
- list bridges
- run a diagnostic check on querygrid systems.
- system management.
- executes queries and analyzes data across vantage systems.
- data center management.
- Data Analyst
- bridge management.
- list all bridges.
- issue monitoring.
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

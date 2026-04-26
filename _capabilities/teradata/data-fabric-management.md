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
- list all data centers.
- configuration
- machine learning
- database
- analytics
- manages data fabric infrastructure and cross-system connectivity.
- sql
- list all registered systems.
- issue monitoring.
- sql query execution and session management.
- health monitoring and issue detection.
- cloud
- Data Engineer
- list data centers
- list all registered systems in querygrid.
- manage querygrid data fabric infrastructure.
- Platform Administrator
- data management
- administration
- run a diagnostic check on querygrid systems.
- system management.
- administers querygrid systems, nodes, and software.
- system and fabric configuration management.
- list fabrics
- list systems
- teradata
- data warehousing
- list bridges
- list connectors
- enterprise
- bridge management.
- list all bridges.
- list issues
- data fabric
- list all configured data centers.
- list all connectors for system integration.
- list all bridges connecting systems.
- list all current issues.
- executes queries and analyzes data across vantage systems.
- list all data fabric configurations.
- integrates applications with teradata via rest apis.
- list all current issues in the querygrid environment.
- run diagnostic check
- Data Analyst
- data center management.
- execute sql queries and analytics.
- Application Developer
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

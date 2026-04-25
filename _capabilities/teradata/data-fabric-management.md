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
- list issues
- list all configured data centers.
- Platform Administrator
- list all bridges.
- list connectors
- analytics
- manage querygrid data fabric infrastructure.
- database
- run diagnostic check
- list all data centers.
- enterprise
- administration
- list all current issues.
- list systems
- executes queries and analyzes data across vantage systems.
- health monitoring and issue detection.
- list bridges
- machine learning
- list all current issues in the querygrid environment.
- cloud
- manages data fabric infrastructure and cross-system connectivity.
- teradata
- list fabrics
- bridge management.
- sql query execution and session management.
- list all registered systems.
- configuration
- list all registered systems in querygrid.
- execute sql queries and analytics.
- data management
- data center management.
- data fabric
- administers querygrid systems, nodes, and software.
- Data Analyst
- data warehousing
- list all data fabric configurations.
- system and fabric configuration management.
- sql
- run a diagnostic check on querygrid systems.
- list all bridges connecting systems.
- system management.
- Data Engineer
- integrates applications with teradata via rest apis.
- Application Developer
- issue monitoring.
- list all connectors for system integration.
- list data centers
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

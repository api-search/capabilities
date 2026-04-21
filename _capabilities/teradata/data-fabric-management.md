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
- execute sql queries and analytics.
- list all connectors for system integration.
- manage querygrid data fabric infrastructure.
- data warehousing
- Platform Administrator
- teradata
- list data centers
- database
- sql
- list connectors
- run a diagnostic check on querygrid systems.
- analytics
- list all data fabric configurations.
- enterprise
- list all configured data centers.
- list issues
- data management
- system and fabric configuration management.
- list all bridges.
- list all data centers.
- health monitoring and issue detection.
- machine learning
- issue monitoring.
- data fabric
- list all current issues.
- Data Analyst
- configuration
- executes queries and analyzes data across vantage systems.
- list all bridges connecting systems.
- list all current issues in the querygrid environment.
- data center management.
- list bridges
- sql query execution and session management.
- system management.
- administration
- bridge management.
- run diagnostic check
- Data Engineer
- list systems
- list all registered systems in querygrid.
- manages data fabric infrastructure and cross-system connectivity.
- Application Developer
- cloud
- list fabrics
- list all registered systems.
- integrates applications with teradata via rest apis.
- administers querygrid systems, nodes, and software.
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

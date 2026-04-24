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
- data management
- sql query execution and session management.
- system and fabric configuration management.
- sql
- manage querygrid data fabric infrastructure.
- list bridges
- list systems
- cloud
- list fabrics
- configuration
- analytics
- list issues
- administers querygrid systems, nodes, and software.
- execute sql queries and analytics.
- executes queries and analyzes data across vantage systems.
- teradata
- list all registered systems in querygrid.
- bridge management.
- list data centers
- administration
- list all current issues.
- list all configured data centers.
- run diagnostic check
- Platform Administrator
- system management.
- list all bridges.
- list connectors
- machine learning
- data fabric
- list all data centers.
- Application Developer
- Data Engineer
- list all registered systems.
- issue monitoring.
- data center management.
- list all current issues in the querygrid environment.
- manages data fabric infrastructure and cross-system connectivity.
- health monitoring and issue detection.
- list all bridges connecting systems.
- database
- list all data fabric configurations.
- data warehousing
- run a diagnostic check on querygrid systems.
- integrates applications with teradata via rest apis.
- Data Analyst
- enterprise
- list all connectors for system integration.
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

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
- list all configured data centers.
- list all data centers.
- list all current issues.
- list data centers
- list all bridges connecting systems.
- bridge management.
- run diagnostic check
- cloud
- enterprise
- Platform Administrator
- analytics
- list all connectors for system integration.
- Data Engineer
- teradata
- data fabric
- execute sql queries and analytics.
- issue monitoring.
- Data Analyst
- sql query execution and session management.
- administration
- system management.
- list connectors
- administers querygrid systems, nodes, and software.
- list all registered systems.
- database
- run a diagnostic check on querygrid systems.
- list issues
- health monitoring and issue detection.
- data center management.
- data management
- configuration
- executes queries and analyzes data across vantage systems.
- machine learning
- manage querygrid data fabric infrastructure.
- list all bridges.
- list all data fabric configurations.
- list bridges
- manages data fabric infrastructure and cross-system connectivity.
- list systems
- system and fabric configuration management.
- Application Developer
- integrates applications with teradata via rest apis.
- list fabrics
- list all registered systems in querygrid.
- list all current issues in the querygrid environment.
- sql
slug: data-fabric-management
source_filename: data-fabric-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Teradata Data Fabric Management\n  description: >-\n    Workflow capability for managing Teradata's data fabric infrastructure.\n    Combines QueryGrid Manager for fabric configuration with Query Service for\n    validating cross-system connectivity. Used by data engineers and platform\n    administrators.\n  tags:\n    - Teradata\n    - Data Fabric\n    - Configuration\n    - Administration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      QUERYGRID_USERNAME: QUERYGRID_USERNAME\n      QUERYGRID_PASSWORD: QUERYGRID_PASSWORD\n      VANTAGE_USERNAME: VANTAGE_USERNAME\n      VANTAGE_PASSWORD: VANTAGE_PASSWORD\n\ncapability:\n  consumes:\n    - import: querygrid-manager\n      location: ./shared/querygrid-manager.yaml\n    - import: query-service\n      location: ./shared/query-service.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: data-fabric-api\n      description:\
  \ \"Unified REST API for Teradata data fabric management.\"\n      resources:\n        - path: /v1/data-centers\n          name: data-centers\n          description: \"Data center management.\"\n          operations:\n            - method: GET\n              name: list-data-centers\n              description: \"List all data centers.\"\n              call: \"querygrid-manager.list-data-centers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/systems\n          name: systems\n          description: \"System management.\"\n          operations:\n            - method: GET\n              name: list-systems\n              description: \"List all registered systems.\"\n              call: \"querygrid-manager.list-systems\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bridges\n          name: bridges\n          description: \"Bridge management.\"\
  \n          operations:\n            - method: GET\n              name: list-bridges\n              description: \"List all bridges.\"\n              call: \"querygrid-manager.list-bridges\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/issues\n          name: issues\n          description: \"Issue monitoring.\"\n          operations:\n            - method: GET\n              name: list-issues\n              description: \"List all current issues.\"\n              call: \"querygrid-manager.list-issues\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: data-fabric-mcp\n      transport: http\n      description: \"MCP server for AI-assisted data fabric management.\"\n      tools:\n        - name: list-data-centers\n          description: \"List all configured data centers.\"\n          hints:\n            readOnly:\
  \ true\n          call: \"querygrid-manager.list-data-centers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-systems\n          description: \"List all registered systems in QueryGrid.\"\n          hints:\n            readOnly: true\n          call: \"querygrid-manager.list-systems\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bridges\n          description: \"List all bridges connecting systems.\"\n          hints:\n            readOnly: true\n          call: \"querygrid-manager.list-bridges\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connectors\n          description: \"List all connectors for system integration.\"\n          hints:\n            readOnly: true\n          call: \"querygrid-manager.list-connectors\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: list-fabrics\n          description: \"List all data fabric configurations.\"\n          hints:\n            readOnly: true\n          call: \"querygrid-manager.list-fabrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-issues\n          description: \"List all current issues in the QueryGrid environment.\"\n          hints:\n            readOnly: true\n          call: \"querygrid-manager.list-issues\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-diagnostic-check\n          description: \"Run a diagnostic check on QueryGrid systems.\"\n          hints:\n            readOnly: false\n          call: \"querygrid-manager.run-diagnostic-check\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/teradata/refs/heads/main/capabilities/data-fabric-management.yaml
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

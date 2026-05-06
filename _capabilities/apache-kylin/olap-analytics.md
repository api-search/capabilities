---
categories:
- analytics
consumed_apis: []
description: Workflow capability for data analysts and BI engineers to execute OLAP queries, manage projects, and monitor cube build jobs in Apache Kylin.
layout: capability
name: Apache Kylin OLAP Analytics
operations:
- description: ''
  method: POST
  name: execute-query
  path: /v1/query
- description: ''
  method: GET
  name: list-projects
  path: /v1/projects
- description: ''
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Apache Kylin
provider_slug: apache-kylin
search_terms:
- list cube build jobs and their statuses
- list jobs
- BI Engineer
- apache kylin
- analytics
- big data
- cancel a running kylin cube build job
- cancel job
- execute query
- sql
- open source
- list data models in a kylin project
- Data Analyst
- olap
- list all kylin projects and their configurations
- list models
- analysts who execute olap sql queries over large hadoop datasets
- list projects
- business intelligence
- engineers who build and manage kylin cubes for bi tool consumption
- cube
- big data analytics
- execute sql query
- execute a sql query on apache kylin to retrieve olap analytics results
slug: olap-analytics
source_filename: olap-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Kylin OLAP Analytics\n  description: Workflow capability for data analysts and BI engineers to execute OLAP queries, manage projects, and monitor\n    cube build jobs in Apache Kylin.\n  tags:\n  - Apache Kylin\n  - Big Data Analytics\n  - Business Intelligence\n  - OLAP\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    KYLIN_PASSWORD: KYLIN_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: kylin-rest-api\n    baseUri: http://localhost:7070/kylin/api\n    description: Apache Kylin REST API\n    authentication:\n      type: basic\n      username: ADMIN\n      password: '{{KYLIN_PASSWORD}}'\n    resources:\n    - name: query\n      path: /query\n      description: SQL query execution\n      operations:\n      - name: execute-query\n        method: POST\n        description: Execute SQL query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      description: Project management\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs\n      description: Job management\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List build jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kylin-olap-analytics-api\n    description: Unified REST API for Apache Kylin OLAP analytics.\n    resources:\n    - path: /v1/query\n      name: query\n      operations:\n      - method: POST\n        name: execute-query\n        call: kylin-rest-api.execute-query\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      operations:\n      - method: GET\n        name: list-projects\n        call: kylin-rest-api.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        call: kylin-rest-api.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: kylin-olap-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache Kylin OLAP analytics.\n    tools:\n    - name: execute-sql-query\n      description: Execute a SQL query on Apache Kylin to retrieve OLAP analytics results\n      hints:\n        readOnly: true\n        openWorld: true\n      call: kylin-rest-api.execute-query\n      outputParameters:\n      - type: object\n        mapping: $.\n  \
  \  - name: list-projects\n      description: List all Kylin projects and their configurations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: kylin-rest-api.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-models\n      description: List data models in a Kylin project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: kylin-rest-api.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List cube build jobs and their statuses\n      hints:\n        readOnly: true\n        openWorld: true\n      call: kylin-rest-api.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-job\n      description: Cancel a running Kylin cube build job\n      hints:\n        readOnly: false\n        destructive: false\n      call: kylin-rest-api.cancel-job\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-kylin/refs/heads/main/capabilities/olap-analytics.yaml
tags:
- Apache Kylin
- Big Data Analytics
- Business Intelligence
- OLAP
tools:
- description: Execute a SQL query on Apache Kylin to retrieve OLAP analytics results
  hints:
    openWorld: true
    readOnly: true
  name: execute-sql-query
- description: List all Kylin projects and their configurations
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: List data models in a Kylin project
  hints:
    openWorld: true
    readOnly: true
  name: list-models
- description: List cube build jobs and their statuses
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Cancel a running Kylin cube build job
  hints:
    destructive: false
    readOnly: false
  name: cancel-job
---

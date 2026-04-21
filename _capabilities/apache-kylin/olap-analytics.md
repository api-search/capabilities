---
consumed_apis:
- kylin-rest-api
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
- analysts who execute olap sql queries over large hadoop datasets
- cancel job
- list data models in a kylin project
- sql
- analytics
- list models
- cancel a running kylin cube build job
- list all kylin projects and their configurations
- execute sql query
- apache kylin
- Data Analyst
- business intelligence
- big data
- list jobs
- big data analytics
- execute query
- list projects
- cube
- engineers who build and manage kylin cubes for bi tool consumption
- olap
- execute a sql query on apache kylin to retrieve olap analytics results
- open source
- list cube build jobs and their statuses
- BI Engineer
slug: olap-analytics
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

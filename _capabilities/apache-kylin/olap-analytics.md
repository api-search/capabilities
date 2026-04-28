---
categories:
- analytics
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
- BI Engineer
- sql
- cancel job
- cancel a running kylin cube build job
- big data analytics
- list cube build jobs and their statuses
- list all kylin projects and their configurations
- list models
- execute sql query
- execute query
- list jobs
- engineers who build and manage kylin cubes for bi tool consumption
- business intelligence
- Data Analyst
- apache kylin
- list projects
- analysts who execute olap sql queries over large hadoop datasets
- open source
- olap
- big data
- analytics
- cube
- execute a sql query on apache kylin to retrieve olap analytics results
- list data models in a kylin project
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

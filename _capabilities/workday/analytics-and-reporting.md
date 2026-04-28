---
categories:
- analytics
consumed_apis:
- workday-prism
- workday-wql
- workday-raas
description: Unified analytics and reporting combining Prism Analytics, WQL, and Report-as-a-Service APIs for business analysts to query data, manage datasets, and access custom reports.
layout: capability
name: Workday Analytics and Reporting
operations:
- description: List datasets
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: Execute a WQL query
  method: POST
  name: execute-query
  path: /v1/wql-query
personas: []
provider_name: Workday
provider_slug: workday
search_terms:
- reporting
- create a new prism analytics dataset
- cloud computing
- wql execute query
- get a wql data source by id
- prism create dataset
- prism list datasets
- wql get data source fields
- financial management
- list all prism analytics datasets
- retrieve a custom workday report
- execute query
- list available wql data sources
- business intelligence
- wql get data source
- list datasets
- prism create data change task
- prism delete dataset
- wql query endpoint
- prism analytics datasets
- hcm
- delete a dataset
- prism list data change tasks
- execute a wql query
- workday
- list data change tasks
- wql list data sources
- prism get dataset
- execute a wql query against workday data
- create a data change task
- raas get report
- analytics
- prism list tables
- enterprise software
- get a dataset by id
- saas
- get fields for a wql data source
- list all prism tables
slug: analytics-and-reporting
tags:
- Workday
- Analytics
- Reporting
- Business Intelligence
tools:
- description: List all Prism Analytics datasets
  hints:
    readOnly: true
  name: prism-list-datasets
- description: Create a new Prism Analytics dataset
  hints:
    readOnly: false
  name: prism-create-dataset
- description: Get a dataset by ID
  hints:
    readOnly: true
  name: prism-get-dataset
- description: Delete a dataset
  hints:
    destructive: true
    readOnly: false
  name: prism-delete-dataset
- description: List data change tasks
  hints:
    readOnly: true
  name: prism-list-data-change-tasks
- description: Create a data change task
  hints:
    readOnly: false
  name: prism-create-data-change-task
- description: List all Prism tables
  hints:
    readOnly: true
  name: prism-list-tables
- description: Execute a WQL query against Workday data
  hints:
    readOnly: true
  name: wql-execute-query
- description: List available WQL data sources
  hints:
    readOnly: true
  name: wql-list-data-sources
- description: Get a WQL data source by ID
  hints:
    readOnly: true
  name: wql-get-data-source
- description: Get fields for a WQL data source
  hints:
    readOnly: true
  name: wql-get-data-source-fields
- description: Retrieve a custom Workday report
  hints:
    readOnly: true
  name: raas-get-report
---

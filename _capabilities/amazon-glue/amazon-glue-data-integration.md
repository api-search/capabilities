---
categories:
- data-engineering
consumed_apis:
- amazon-glue
description: Workflow capability for data engineers building ETL pipelines with Amazon Glue. Covers job management, crawler configuration, data catalog operations, workflow orchestration, and data quality for serverless data integration.
layout: capability
name: Amazon Glue Data Integration
operations:
- description: List all ETL jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Create a new ETL job
  method: POST
  name: create-job
  path: /v1/jobs
- description: Start a job run
  method: POST
  name: start-job-run
  path: /v1/jobs/{jobName}/runs
- description: List all crawlers
  method: GET
  name: list-crawlers
  path: /v1/crawlers
- description: Create a new crawler
  method: POST
  name: create-crawler
  path: /v1/crawlers
- description: List all catalog databases
  method: GET
  name: list-databases
  path: /v1/databases
- description: List all workflows
  method: GET
  name: list-workflows
  path: /v1/workflows
- description: Create a new ETL workflow
  method: POST
  name: create-workflow
  path: /v1/workflows
personas: []
provider_name: Amazon Glue
provider_slug: amazon-glue
search_terms:
- list ml transforms
- start crawler
- create a new etl workflow with triggers and jobs
- list connections
- data engineering
- create a new etl workflow
- list all workflows
- data integration
- execute an etl job run
- data pipeline
- Data Analyst
- etl job lifecycle management
- create a crawler to discover and catalog data sources
- serverless
- list all data catalog crawlers
- analytics
- list all glue ml transforms
- uses glue to access and prepare data for analytics
- create job
- list all etl workflow orchestrations
- amazon glue
- start a job run
- data catalog crawlers
- list workflows
- list tables in a data catalog database
- create connection
- list data quality results
- list all crawlers
- list etl jobs
- run a crawler to populate the data catalog
- list crawlers
- create a new amazon glue etl job
- create workflow
- etl workflow orchestration
- check the status of an etl job run
- data catalog
- builds and manages etl pipelines and data catalog resources
- create crawler
- data catalog databases
- list all catalog databases
- list tables
- list all amazon glue etl jobs with status and configuration
- Data Engineer
- create a new etl job
- list jobs
- etl
- start job run
- create a new crawler
- list all etl jobs
- list all databases in the glue data catalog
- aws
- job execution runs
- list all data source connections
- create a connection to a data source
- list databases
- list data quality evaluation results
- create etl job
- get job run status
slug: amazon-glue-data-integration
tags:
- Amazon Glue
- ETL
- Data Integration
- Data Catalog
- Data Engineering
- AWS
tools:
- description: List all Amazon Glue ETL jobs with status and configuration
  hints:
    openWorld: true
    readOnly: true
  name: list-etl-jobs
- description: Create a new Amazon Glue ETL job
  hints:
    readOnly: false
  name: create-etl-job
- description: Execute an ETL job run
  hints:
    readOnly: false
  name: start-job-run
- description: Check the status of an ETL job run
  hints:
    readOnly: true
  name: get-job-run-status
- description: List all Data Catalog crawlers
  hints:
    readOnly: true
  name: list-crawlers
- description: Create a crawler to discover and catalog data sources
  hints:
    readOnly: false
  name: create-crawler
- description: Run a crawler to populate the Data Catalog
  hints:
    readOnly: false
  name: start-crawler
- description: List all databases in the Glue Data Catalog
  hints:
    readOnly: true
  name: list-databases
- description: List tables in a Data Catalog database
  hints:
    readOnly: true
  name: list-tables
- description: List all ETL workflow orchestrations
  hints:
    readOnly: true
  name: list-workflows
- description: Create a new ETL workflow with triggers and jobs
  hints:
    readOnly: false
  name: create-workflow
- description: List all data source connections
  hints:
    readOnly: true
  name: list-connections
- description: Create a connection to a data source
  hints:
    readOnly: false
  name: create-connection
- description: List all Glue ML transforms
  hints:
    readOnly: true
  name: list-ml-transforms
- description: List data quality evaluation results
  hints:
    readOnly: true
  name: list-data-quality-results
---

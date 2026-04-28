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
- create crawler
- create etl job
- list workflows
- list all amazon glue etl jobs with status and configuration
- list connections
- list all data source connections
- builds and manages etl pipelines and data catalog resources
- create a new etl workflow with triggers and jobs
- etl
- data catalog
- data catalog crawlers
- list databases
- create a new crawler
- etl job lifecycle management
- list all catalog databases
- create workflow
- list all crawlers
- list all workflows
- aws
- list all databases in the glue data catalog
- Data Engineer
- list data quality evaluation results
- create job
- create a new amazon glue etl job
- create a crawler to discover and catalog data sources
- data integration
- create a new etl job
- uses glue to access and prepare data for analytics
- Data Analyst
- list jobs
- check the status of an etl job run
- list all glue ml transforms
- create a new etl workflow
- start a job run
- run a crawler to populate the data catalog
- data pipeline
- etl workflow orchestration
- list all etl workflow orchestrations
- list all etl jobs
- list tables in a data catalog database
- list all data catalog crawlers
- create connection
- list data quality results
- get job run status
- create a connection to a data source
- execute an etl job run
- analytics
- amazon glue
- start job run
- list ml transforms
- serverless
- job execution runs
- data catalog databases
- list crawlers
- list tables
- data engineering
- list etl jobs
- start crawler
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

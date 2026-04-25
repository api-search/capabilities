---
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
- list all databases in the glue data catalog
- execute an etl job run
- create a crawler to discover and catalog data sources
- job execution runs
- list connections
- list etl jobs
- create job
- start a job run
- create workflow
- start crawler
- list data quality results
- builds and manages etl pipelines and data catalog resources
- analytics
- serverless
- list all data catalog crawlers
- data integration
- create a new crawler
- list data quality evaluation results
- list all data source connections
- create a new etl job
- data pipeline
- create etl job
- aws
- list jobs
- list workflows
- list tables
- list all etl workflow orchestrations
- run a crawler to populate the data catalog
- etl
- list databases
- check the status of an etl job run
- list tables in a data catalog database
- create a connection to a data source
- create a new amazon glue etl job
- create a new etl workflow with triggers and jobs
- list all catalog databases
- list all etl jobs
- list all amazon glue etl jobs with status and configuration
- etl job lifecycle management
- data catalog
- list all crawlers
- list ml transforms
- Data Analyst
- data catalog crawlers
- etl workflow orchestration
- data engineering
- get job run status
- start job run
- create crawler
- data catalog databases
- list all workflows
- list all glue ml transforms
- Data Engineer
- create a new etl workflow
- uses glue to access and prepare data for analytics
- create connection
- list crawlers
- amazon glue
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

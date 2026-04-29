---
api_specs:
- filename: amazon-glue-openapi.yml
  format: yaml
  label: amazon-glue
  slug: amazon-glue
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-glue/refs/heads/main/openapi/amazon-glue-openapi.yml
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
- amazon glue
- job execution runs
- data catalog databases
- list all etl workflow orchestrations
- list etl jobs
- list all databases in the glue data catalog
- Data Engineer
- data catalog
- data pipeline
- create a new etl job
- list all workflows
- serverless
- list jobs
- builds and manages etl pipelines and data catalog resources
- uses glue to access and prepare data for analytics
- create a new crawler
- create workflow
- start crawler
- data integration
- create a connection to a data source
- etl job lifecycle management
- list connections
- create connection
- list data quality results
- check the status of an etl job run
- create a new etl workflow
- get job run status
- list tables
- aws
- list databases
- data catalog crawlers
- Data Analyst
- list all glue ml transforms
- list all crawlers
- list crawlers
- start job run
- list all data source connections
- create a new etl workflow with triggers and jobs
- create job
- execute an etl job run
- list all amazon glue etl jobs with status and configuration
- run a crawler to populate the data catalog
- list ml transforms
- analytics
- start a job run
- create a new amazon glue etl job
- create etl job
- list tables in a data catalog database
- list all catalog databases
- list all etl jobs
- list workflows
- list data quality evaluation results
- list all data catalog crawlers
- create crawler
- create a crawler to discover and catalog data sources
- etl workflow orchestration
- data engineering
- etl
slug: amazon-glue-data-integration
source_filename: amazon-glue-data-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon Glue Data Integration\n  description: >-\n    Workflow capability for data engineers building ETL pipelines with Amazon Glue.\n    Covers job management, crawler configuration, data catalog operations, workflow\n    orchestration, and data quality for serverless data integration.\n  tags:\n    - Amazon Glue\n    - ETL\n    - Data Integration\n    - Data Catalog\n    - Data Engineering\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-glue\n      location: ./shared/amazon-glue.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: glue-data-integration-api\n      description: Unified REST API for Amazon Glue data integration operations.\n      resources:\n        - path: /v1/jobs\n\
  \          name: jobs\n          description: ETL job lifecycle management\n          operations:\n            - method: GET\n              name: list-jobs\n              description: List all ETL jobs\n              call: amazon-glue.GetJobs\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-job\n              description: Create a new ETL job\n              call: amazon-glue.CreateJob\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs/{jobName}/runs\n          name: job-runs\n          description: Job execution runs\n          operations:\n            - method: POST\n              name: start-job-run\n              description: Start a job run\n              call: amazon-glue.StartJobRun\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/crawlers\n\
  \          name: crawlers\n          description: Data catalog crawlers\n          operations:\n            - method: GET\n              name: list-crawlers\n              description: List all crawlers\n              call: amazon-glue.GetCrawlers\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-crawler\n              description: Create a new crawler\n              call: amazon-glue.CreateCrawler\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/databases\n          name: databases\n          description: Data Catalog databases\n          operations:\n            - method: GET\n              name: list-databases\n              description: List all catalog databases\n              call: amazon-glue.GetDatabases\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \        - path: /v1/workflows\n          name: workflows\n          description: ETL workflow orchestration\n          operations:\n            - method: GET\n              name: list-workflows\n              description: List all workflows\n              call: amazon-glue.ListWorkflows\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workflow\n              description: Create a new ETL workflow\n              call: amazon-glue.CreateWorkflow\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: glue-data-integration-mcp\n      transport: http\n      description: MCP server for AI-assisted Amazon Glue data integration management.\n      tools:\n        - name: list-etl-jobs\n          description: List all Amazon Glue ETL jobs with status and configuration\n          hints:\n   \
  \         readOnly: true\n            openWorld: true\n          call: amazon-glue.GetJobs\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-etl-job\n          description: Create a new Amazon Glue ETL job\n          hints:\n            readOnly: false\n          call: amazon-glue.CreateJob\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-job-run\n          description: Execute an ETL job run\n          hints:\n            readOnly: false\n          call: amazon-glue.StartJobRun\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-run-status\n          description: Check the status of an ETL job run\n          hints:\n            readOnly: true\n          call: amazon-glue.GetJobRun\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-crawlers\n   \
  \       description: List all Data Catalog crawlers\n          hints:\n            readOnly: true\n          call: amazon-glue.GetCrawlers\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-crawler\n          description: Create a crawler to discover and catalog data sources\n          hints:\n            readOnly: false\n          call: amazon-glue.CreateCrawler\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-crawler\n          description: Run a crawler to populate the Data Catalog\n          hints:\n            readOnly: false\n          call: amazon-glue.StartCrawler\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-databases\n          description: List all databases in the Glue Data Catalog\n          hints:\n            readOnly: true\n          call: amazon-glue.GetDatabases\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-tables\n          description: List tables in a Data Catalog database\n          hints:\n            readOnly: true\n          call: amazon-glue.GetTables\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workflows\n          description: List all ETL workflow orchestrations\n          hints:\n            readOnly: true\n          call: amazon-glue.ListWorkflows\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workflow\n          description: Create a new ETL workflow with triggers and jobs\n          hints:\n            readOnly: false\n          call: amazon-glue.CreateWorkflow\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connections\n          description: List all data source connections\n          hints:\n          \
  \  readOnly: true\n          call: amazon-glue.GetConnections\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-connection\n          description: Create a connection to a data source\n          hints:\n            readOnly: false\n          call: amazon-glue.CreateConnection\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-ml-transforms\n          description: List all Glue ML transforms\n          hints:\n            readOnly: true\n          call: amazon-glue.GetMLTransforms\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-quality-results\n          description: List data quality evaluation results\n          hints:\n            readOnly: true\n          call: amazon-glue.ListDataQualityResults\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-glue/refs/heads/main/capabilities/amazon-glue-data-integration.yaml
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
